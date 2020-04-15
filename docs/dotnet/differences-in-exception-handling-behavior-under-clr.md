---
title: -CLR Altında İstisna İşleme Davranışındaki Farklılıklar
ms.date: 11/04/2016
helpviewer_keywords:
- EXCEPTION_CONTINUE_EXECUTION macro
- set_se_translator function
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
ms.openlocfilehash: 940d297ff77248ba9e9980f7032b5d722d95c7eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364374"
---
# <a name="differences-in-exception-handling-behavior-under-clr"></a>/CLR Altında Özel Durum İşleme Farkları

[Yönetilen Özel Durumları Kullanmadaki Temel Kavramlar,](../dotnet/basic-concepts-in-using-managed-exceptions.md) yönetilen uygulamalarda özel durum işlemeyi tartışır. Bu konuda, özel durum işlemenin standart davranışından ve bazı kısıtlamalardan farklı olarak ayrıntılı olarak ele alınmıştır. Daha fazla bilgi için [_set_se_translator Fonksiyonu'na](../c-runtime-library/reference/set-se-translator.md)bakın.

## <a name="jumping-out-of-a-finally-block"></a><a name="vcconjumpingoutofafinallyblock"></a>Sonunda Bloktan Atlama

Yerel C/C++ kodunda, bir uyarı üretse de yapılandırılmış özel durum işleme (SEH) kullanarak bir __**sonunda** bloktan atlamaya izin verilir.  [/clr](../build/reference/clr-common-language-runtime-compilation.md)altında, **son** bir blok tan atlama bir hataya neden olur:

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

## <a name="raising-exceptions-within-an-exception-filter"></a><a name="vcconraisingexceptionswithinanexceptionfilter"></a>Özel Durum Filtresi İçindeKi Özel Durumları Yükseltme

Yönetilen kod içinde bir özel [durum filtresinin](../cpp/writing-an-exception-filter.md) işlenmesi sırasında bir özel durum yükseltildiğinde, özel durum yakalanır ve filtre 0 döndürür gibi işlem yapılır.

Bu, iç içe geçen bir özel durum yükseltilir, **EXCEPTION_RECORD** yapısında **ExceptionRecord** alanı [(GetExceptionInformation](/windows/win32/Debug/getexceptioninformation)tarafından döndürülür) ayarlanır ve **ExceptionFlags** alanı 0x10 bit ayarlar yerel kod davranışı aksine. Aşağıdaki örnekdavranış bu farkı göstermektedir:

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

### <a name="output"></a>Çıktı

```Output
Caught a nested exception
We should execute this handler if compiled to native
```

## <a name="disassociated-rethrows"></a><a name="vccondisassociatedrethrows"></a>İlişkisi Kesilen Rethrows

**/clr,** catch işleyicisi dışında bir özel durum (ilgisiz yeniden atma olarak bilinir) dışında bir özel durum yeniden atma desteklemez. Bu tür özel durumlar standart bir C++ rethrow olarak kabul edilir. Etkin yönetilen bir özel durum olduğunda, ilgisiz bir yeniden atma ile karşılaşılırsa, özel durum C++ özel durumu olarak sarılır ve sonra yeniden atılır. Bu tür özel durumlar yalnızca tür <xref:System.Runtime.InteropServices.SEHException>bir istisna olarak yakalanabilir.

Aşağıdaki örnek, C++ özel durumu olarak yeniden atılan yönetilen bir özel durumu gösterir:

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

### <a name="output"></a>Çıktı

```Output
caught an SEH Exception
```

## <a name="exception-filters-and-exception_continue_execution"></a><a name="vcconexceptionfiltersandexception_continue_execution"></a>Özel Durum Filtreleri ve EXCEPTION_CONTINUE_EXECUTION

Yönetilen bir `EXCEPTION_CONTINUE_EXECUTION` uygulamada bir filtre dönerse, filtre döndürülmüş `EXCEPTION_CONTINUE_SEARCH`gibi değerlendirilir. Bu sabitler hakkında daha fazla bilgi için [try-except Bildirimi'ne](../cpp/try-except-statement.md)bakın.

Aşağıdaki örnekte bu fark gösteriş vardır:

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

### <a name="output"></a>Çıktı

```Output
Counter=-3
```

## <a name="the-_set_se_translator-function"></a><a name="vcconthe_set_se_translatorfunction"></a>_set_se_translator Fonksiyonu

Bir çağrı tarafından ayarlanan `_set_se_translator`çevirmen işlevi, yalnızca yönetilmeyen koddaki yakalamaları etkiler. Aşağıdaki örnekte bu sınırlama gösteriş:

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

### <a name="output"></a>Çıktı

```Output
This is invoked since _set_se_translator is not supported when /clr is used
In my_trans_func.
Caught an SEH exception with exception code: e0000101
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[MSVC'de Özel Durum Taşıma](../cpp/exception-handling-in-visual-cpp.md)
