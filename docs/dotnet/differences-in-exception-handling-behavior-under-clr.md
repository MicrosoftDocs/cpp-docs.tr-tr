---
title: "-CLR altında özel durum işleme farkları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- EXCEPTION_CONTINUE_EXECUTION macro
- set_se_translator function
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 16962e39533eb2ac3d698622f8bb3a27d068b0ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="differences-in-exception-handling-behavior-under-clr"></a>/CLR Altında Özel Durum İşleme Farkları
[Yönetilen özel durumlar kullanarak temel kavramlarını](../dotnet/basic-concepts-in-using-managed-exceptions.md) özel durum işleme yönetilen uygulamalarda açıklanır. Bu konuda, özel durum işleme ve bazı kısıtlamalar standart davranışını arasındaki farklar ayrıntılı olarak ele alınmıştır. Daha fazla bilgi için bkz: [_set_se_translator işlevi](../c-runtime-library/reference/set-se-translator.md).  
  
##  <a name="vcconjumpingoutofafinallyblock"></a>İşyeri dışında atlama bir son engelle  
 Atlama __ dışında yerel C/C++ kod**son** bir uyarı üretir ancak yapılandırılmış özel durum işleme (SEH) kullanarak blok izin verilir.  Altında [/CLR](../build/reference/clr-common-language-runtime-compilation.md), atlama dışında bir **son** bloğu bir hataya neden olur:  
  
```  
// clr_exception_handling_4.cpp  
// compile with: /clr  
int main() {  
   try {}  
   finally {  
      return 0;   // also fails with goto, break, continue  
    }  
}   // C3276  
```  
  
##  <a name="vcconraisingexceptionswithinanexceptionfilter"></a>Bir özel durum filtresi içinde özel durumlarını oluşturma  
 Ne zaman bir özel durum oluşturulur işlenmesi sırasında bir [özel durum filtresi](../cpp/writing-an-exception-filter.md) yönetilen kod içinde özel durum yakalandı ve filtre 0 döndürürse gibi işlem görür.  
  
 Burada iç içe geçmiş bir özel durum oluşur, yerel kodda aksine davranış budur **ExceptionRecord** alanındaki **EXCEPTION_RECORD** yapısı (tarafından döndürülen [ GetExceptionInformation](http://msdn.microsoft.com/library/windows/desktop/ms679357)) olarak ayarlanır ve **ExceptionFlags** alan 0x10 bit ayarlar. Aşağıdaki örnek, davranış bu farklılık gösterir:  
  
```  
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
  
```  
Caught a nested exception  
We should execute this handler if compiled to native  
```  
  
##  <a name="vccondisassociatedrethrows"></a>İlişkisiz yeniden oluşturur  
 **/ CLR** (bir ilişkilendirilmemiş yeniden oluşturma da bilinir) bir catch işleyicisi dışında bir özel durum yeniden atma desteklemiyor. Bu tür özel durumları kabul edilir olarak C++ standart bir yeniden oluşturma. Etkin bir yönetilen özel durum olduğunda ilişkilendirilmemiş bir yeniden oluşturulması karşılaşılırsa, özel durum C++ özel durum olarak kaydırılan ve ardından işlenemezse. Bu tür özel durumlar yalnızca bir özel durum belirledi türü [System::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx).  
  
 Aşağıdaki örnek, C++ özel durum olarak işlenemezse yönetilen bir özel durum gösterir:  
  
```  
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
  
```  
caught an SEH Exception  
```  
  
##  <a name="vcconexceptionfiltersandexception_continue_execution"></a>Özel durum filtreleri ve exceptıon_contınue_executıon  
 Bir filtre döndürürse `EXCEPTION_CONTINUE_EXECUTION` filtre döndürülürse olarak yönetilen bir uygulamada işlem görür `EXCEPTION_CONTINUE_SEARCH`. Bu sabitleri hakkında daha fazla bilgi için bkz: [deneyin-except deyimi](../cpp/try-except-statement.md).  
  
 Aşağıdaki örnekte bu farklılık gösterir:  
  
```  
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
  
```  
Counter=-3  
```  
  
##  <a name="vcconthe_set_se_translatorfunction"></a>_Set_se_translator işlevi  
 Set Çeviricisi işlevi çağrısı ile `_set_se_translator`, yalnızca yönetilmeyen kodunda önbellek etkiler. Aşağıdaki örnek, bu sınırlamaya gösterir:  
  
```  
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
  
```  
This is invoked since _set_se_translator is not supported when /clr is used  
In my_trans_func.  
Caught an SEH exception with exception code: e0000101  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme](../windows/exception-handling-cpp-component-extensions.md)   
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Özel durum işleme](../cpp/exception-handling-in-visual-cpp.md)