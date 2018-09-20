---
title: -CLR altında özel durum işleme farkları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- EXCEPTION_CONTINUE_EXECUTION macro
- set_se_translator function
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5423e7c5b607f8a38a123a1c7f52c26f305ddb64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380613"
---
# <a name="differences-in-exception-handling-behavior-under-clr"></a>/CLR Altında Özel Durum İşleme Farkları

[Yönetilen özel durumları kullanarak temel kavramları](../dotnet/basic-concepts-in-using-managed-exceptions.md) özel durum işleme yönetilen uygulamalarda açıklanır. Bu konu başlığında, özel durum işleme ve bazı kısıtlamalar standart davranışını arasındaki farklar ayrıntılı olarak ele alınmıştır. Daha fazla bilgi için [_set_se_translator işlevi](../c-runtime-library/reference/set-se-translator.md).

##  <a name="vcconjumpingoutofafinallyblock"></a> / Atlama bir Finally bloğunda

Atlama dışında bir __ yerel C/C++ kodundaki**son** bir uyarı üretir ancak yapılandırılmış özel durum işleme (SEH) kullanarak blok izin verilir.  Altında [/CLR](../build/reference/clr-common-language-runtime-compilation.md), atlama dışı bir **son** blok bir hataya neden olur:

```cpp
// clr_exception_handling_4.cpp
// compile with: /clr
int main() {
   try {}
   finally {
      return 0;   // also fails with goto, break, continue
    }
}   // C3276
```

##  <a name="vcconraisingexceptionswithinanexceptionfilter"></a> Özel Durum Filtresi içinde özel durumlarını oluşturma

Ne zaman bir özel durum oluşturulur işlenmesi sırasında bir [özel durum filtresi](../cpp/writing-an-exception-filter.md) yönetilen kod içinde özel durum yakalandı ve filtre 0 döndürür gibi değerlendirilir.

Burada bir iç içe geçmiş özel durum oluşturulur, yerel kodda aksine davranışı budur **ExceptionRecord** alanındaki **exceptıon_record** yapısı (tarafından döndürülen [ Getexceptionınformation](/windows/desktop/Debug/getexceptioninformation)) olarak ayarlanır ve **ExceptionFlags** 0x10 bit alanını ayarlar. Aşağıdaki örnek, bu davranışı farklılık gösterir:

```cpp
// clr_exception_handling_5.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

#ifndef false
#define false 0
#endif

int *p;

int filter(PEXCEPTION_POINTERS ExceptionPointers) {
   PEXCEPTION_RECORD ExceptionRecord =
                     ExceptionPointers->ExceptionRecord;

   if ((ExceptionRecord->ExceptionFlags & 0x10) == 0) {
      // not a nested exception, throw one
      *p = 0; // throw another AV
   }
   else {
      printf("Caught a nested exception\n");
      return 1;
    }

   assert(false);

   return 0;
}

void f(void) {
   __try {
      *p = 0;   // throw an AV
   }
   __except(filter(GetExceptionInformation())) {
      printf_s("We should execute this handler if "
                 "compiled to native\n");
    }
}

int main() {
   __try {
      f();
   }
   __except(1) {
      printf_s("The handler in main caught the "
               "exception\n");
    }
}
```

### <a name="output"></a>Çıkış

```Output
Caught a nested exception
We should execute this handler if compiled to native
```

##  <a name="vccondisassociatedrethrows"></a> İlişkisi kaldırılan beklerseniz

**/ CLR** dışında (rethrow ilişkilendirilmemiş bilinir) bir catch işleyicisi bir özel durum yeniden atma desteklemez. Bu tür özel durumları kabul edilir standart bir C++ rethrow olarak. Etkin bir yönetilen özel durum olduğunda ilişkilendirilmemiş rethrow karşılaşılırsa, özel durumu bir C++ özel durum kaydırılır ve döndükten sonra. Bu tür özel durumlar yalnızca yakalanan bir özel durum türü [System::SEHException](https://msdn.microsoft.com/library/system.runtime.interopservices.sehexception.aspx).

Aşağıdaki örnek, bir C++ özel durum işlenemezse yönetilen bir özel durum gösterir:

```cpp
// clr_exception_handling_6.cpp
// compile with: /clr
using namespace System;
#include <assert.h>
#include <stdio.h>

void rethrow( void ) {
   // This rethrow is a dissasociated rethrow.
   // The exception would be masked as SEHException.
   throw;
}

int main() {
   try {
      try {
         throw gcnew ApplicationException;
      }
      catch ( ApplicationException^ ) {
         rethrow();
         // If the call to rethrow() is replaced with
         // a throw statement within the catch handler,
         // the rethrow would be a managed rethrow and
         // the exception type would remain
         // System::ApplicationException
      }
   }

    catch ( ApplicationException^ ) {
      assert( false );

      // This will not be executed since the exception
      // will be masked as SEHException.
    }
   catch ( Runtime::InteropServices::SEHException^ ) {
      printf_s("caught an SEH Exception\n" );
    }
}
```

### <a name="output"></a>Çıkış

```Output
caught an SEH Exception
```

##  <a name="vcconexceptionfiltersandexception_continue_execution"></a> Özel durum filtreleri ve exceptıon_contınue_executıon

Bir filtre döndürürse `EXCEPTION_CONTINUE_EXECUTION` filtre döndürdüyse olarak yönetilen bir uygulamada, kabul edilir `EXCEPTION_CONTINUE_SEARCH`. Bu sabitleri hakkında daha fazla bilgi için bkz. [deneyin-except deyimi](../cpp/try-except-statement.md).

Aşağıdaki örnek, bu farklılık gösterir:

```cpp
// clr_exception_handling_7.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

int main() {
   int Counter = 0;
   __try {
      __try  {
         Counter -= 1;
         RaiseException (0xe0000000|'seh',
                         0, 0, 0);
         Counter -= 2;
      }
      __except (Counter) {
         // Counter is negative,
         // indicating "CONTINUE EXECUTE"
         Counter -= 1;
      }
    }
    __except(1) {
      Counter -= 100;
   }

   printf_s("Counter=%d\n", Counter);
}
```

### <a name="output"></a>Çıkış

```Output
Counter=-3
```

##  <a name="vcconthe_set_se_translatorfunction"></a> _Set_se_translator işlevi

Translator işlevi ayarlamak için bir çağrı tarafından `_set_se_translator`, yalnızca yönetilmeyen kodda Özek durumları yakalayan etkiler. Bu sınırlama aşağıdaki örnekte gösterilmiştir:

```cpp
// clr_exception_handling_8.cpp
// compile with: /clr /EHa
#include <iostream>
#include <windows.h>
#include <eh.h>
#pragma warning (disable: 4101)
using namespace std;
using namespace System;

#define MYEXCEPTION_CODE 0xe0000101

class CMyException {
public:
   unsigned int m_ErrorCode;
   EXCEPTION_POINTERS * m_pExp;

   CMyException() : m_ErrorCode( 0 ), m_pExp( NULL ) {}

   CMyException( unsigned int i, EXCEPTION_POINTERS * pExp )
         : m_ErrorCode( i ), m_pExp( pExp ) {}

   CMyException( CMyException& c ) : m_ErrorCode( c.m_ErrorCode ),
                                      m_pExp( c.m_pExp ) {}

   friend ostream& operator <<
                 ( ostream& out, const CMyException& inst ) {
      return out <<  "CMyException[\n" <<
             "Error Code: " << inst.m_ErrorCode <<  "]";
    }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS pExp ) {
   cout <<  "In my_trans_func.\n";
   throw CMyException( u, pExp );
}

#pragma managed
void managed_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE, 0, 0, 0 );
   }
   catch ( CMyException x ) {}
   catch ( ... ) {
      printf_s("This is invoked since "
               "_set_se_translator is not "
               "supported when /clr is used\n" );
    }
}

#pragma unmanaged
void unmanaged_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE,
                      0, 0, 0 );
   }
   catch ( CMyException x ) {
      printf("Caught an SEH exception with "
             "exception code: %x\n", x.m_ErrorCode );
    }
    catch ( ... ) {}
}

// #pragma managed
int main( int argc, char ** argv ) {
   _set_se_translator( my_trans_func );

   // It does not matter whether the translator function
   // is registered in managed or unmanaged code
   managed_func();
   unmanaged_func();
}
```

### <a name="output"></a>Çıkış

```Output
This is invoked since _set_se_translator is not supported when /clr is used
In my_trans_func.
Caught an SEH exception with exception code: e0000101
```

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../windows/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../windows/safe-cast-cpp-component-extensions.md)<br/>
[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)