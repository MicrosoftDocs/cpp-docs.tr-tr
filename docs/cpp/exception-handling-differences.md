---
title: Özel durum işleme farkları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9c17c0abbd8286d05423ac52abc2e2109253f6d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404629"
---
# <a name="exception-handling-differences"></a>Özel Durum İşleme Farkları
Yapılandırılmış özel durum işleme ve C++ özel durum işleme arasındaki en önemli fark modeli anlaşmalar türlerinde C++ özel durum işleme, yapılandırılmış özel durum işleme modeli sırasında C, bir tür özel durumlar ile ilgilenen olan — özellikle  **işaretsiz int**. Diğer bir deyişle, C++ özel durumlarını veri türüyle tanımlanır ancak C özel durumlarını bir işaretsiz tamsayı değeri tarafından tanımlanır. C dilinde bir özel durum oluştuğunda, her olası işleyici C özel durum bağlamı inceler ve bu özel durum kabul edin, başka bir işleyiciye geçirmek ya da onu yok saymasını belirleyen bir filtre yürütür. C++'da bir özel durum oluştuğunda, bunu herhangi bir türde olabilir.  
  
 İkinci bir fark, özel durumlar, denetiminin normal akışı için ikincil ortaya C yapılandırılmış özel durum işleme modeli "zaman uyumsuz olarak için" olduğunu adlandırılır. C++ özel durum işleme mekanizmasını tam olarak "zaman uyumlu," yalnızca bunlar oluştuğunda özel durum ortaya anlamına gelir.  
  
 C++ programında C özel durum oluşturulursa, bunu bir C++ veya kendi ilişkili Filtresi ile bir yapılandırılmış özel durum işleyicisi tarafından işlenebilen **catch** işleyicisi, hangisi daha dinamik olarak nearer to özel durum bağlamı. Örneğin, bir C özel durumu bir C++ içinde aşağıdaki C++ programı başlatan **deneyin** Bağlam:  
  
## <a name="example"></a>Örnek  
  
```cpp 
// exceptions_Exception_Handling_Differences.cpp  
// compile with: /EHa  
#include <iostream>  
  
using namespace std;  
void SEHFunc( void );  
  
int main() {  
   try {  
      SEHFunc();  
   }  
   catch( ... ) {  
      cout << "Caught a C exception."<< endl;  
   }  
}  
  
void SEHFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
   }  
   __finally {  
      cout << "In finally." << endl;  
   }  
}  
```  
  
```Output  
In finally.  
Caught a C exception.  
```  
  
##  <a name="_core_c_exception_wrapper_class"></a> C özel durum sarmalayıcı sınıfı  
 Yukarıdaki gibi basit bir örnekte C özel durumu yalnızca üç nokta yakalanabilir (**...** ) **catch** işleyici. İşleyicinin veya özel durum doğası hakkında hiçbir bilgi iletilir. Bu yöntem çalışır, ancak bazı durumlarda, böylece her C özel durumu belirli bir sınıf ile ilişkili iki özel durum işleme modelleri arasında dönüştürme tanımlamanız gerekebilir. Bunu yapmak için kullanılan veya bir C özel durumu için belirli bir sınıf türü özniteliği için türetilen bir C özel durum "sarmalayıcı" sınıfı tanımlayabilirsiniz. Bunun yapılması her C özel durumu bir C++ tarafından işlenebilen **catch** işleyici kıyasla daha ayrı olarak önceki örnek.  
  
 Bazı üye işlevleri, özel durum değerini belirlemek ve C özel durum modeli tarafından sağlanan genişletilmiş özel durum bağlamı bilgilerini erişim oluşan bir arabirim, sarmalayıcı sınıfı olabilir. Varsayılan bir oluşturucu ve kabul eden bir kurucu tanımlamak isteyebilirsiniz bir **işaretsiz int** (temel alınan C özel durum temsili sağlamak için) bağımsız değişken ve bit düzeyinde bir kopya Oluşturucu. C özel durum sarmalayıcı sınıfı olası bir uygulaması aşağıdaki gibidir:  
  
```cpp 
// exceptions_Exception_Handling_Differences2.cpp  
// compile with: /c  
class SE_Exception {  
private:  
   SE_Exception() {}  
   SE_Exception( SE_Exception& ) {}  
   unsigned int nSE;  
public:  
   SE_Exception( unsigned int n ) : nSE( n ) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() {  
      return nSE;  
   }  
};  
```  
  
 Bu sınıf kullanmak için her zaman bir C özel durum iç özel durum işleme mekanizmasını tarafından çağrılan özel bir C özel durum çevirisi işlevi yükleyin. Çeviri işlevinizi içinde herhangi bir türü belirtilmiş özel durumu oluşturabilecek (belki de bir `SE_Exception` türü veya sınıf türü türetilen `SE_Exception`), yakalandı uygun eşleşen C++ tarafından **catch** işleyici. Çeviri işlevi yalnızca geri dönebilirsiniz özel durum işlemedi gösterir. Çeviri işlevi C özel durum harekete geçirirse [sonlandırmak](../c-runtime-library/reference/terminate-crt.md) çağrılır.  
  
 Özel çeviri işlevi belirtmek için çağrı [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) tek bağımsız değişken olarak çeviri işlev uygulamanızın adıyla işlevi. Her yığında olan işlev çağrısını için yazdığınız çeviri işlevi bir kez çağrılır **deneyin** engeller. Hiçbir varsayılan çeviri işlevi yoktur; bir çağırarak belirtmezseniz `_set_se_translator`, C özel durumu yalnızca üç nokta yakalanabilir **catch** işleyici.  
  
## <a name="example"></a>Örnek  
 Örneğin, aşağıdaki kod bir özel çeviri işlevi yükler ve ardından tarafından Sarmalanan bir C özel durumu harekete `SE_Exception` sınıfı:  
  
```cpp 
// exceptions_Exception_Handling_Differences3.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <eh.h>  
#include <windows.h>  
  
class SE_Exception {  
private:  
   SE_Exception() {}  
   unsigned int nSE;  
  
public:  
   SE_Exception( SE_Exception& e) : nSE(e.nSE) {}  
   SE_Exception(unsigned int n) : nSE(n) {}  
   ~SE_Exception() {}  
   unsigned int getSeNumber() { return nSE; }  
};  
  
void SEFunc() {  
   __try {  
      int x, y = 0;  
      x = 5 / y;  
    }  
    __finally {  
      printf_s( "In finally\n" );  
   }  
}  
  
void trans_func( unsigned int u, _EXCEPTION_POINTERS* pExp ) {  
   printf_s( "In trans_func.\n" );  
   throw SE_Exception( u );  
}  
  
int main() {  
   _set_se_translator( trans_func );  
    try {  
      SEFunc();  
    }  
    catch( SE_Exception e ) {  
      printf_s( "Caught a __try exception with SE_Exception.\n" );  
      printf_s( "nSE = 0x%x\n", e.getSeNumber() );  
    }  
}  
```  
  
```Output  
In trans_func.  
In finally  
Caught a __try exception with SE_Exception.  
nSE = 0xc0000094  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)