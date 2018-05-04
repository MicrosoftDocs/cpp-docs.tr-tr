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
ms.openlocfilehash: d4577739c7ef141576361e6db630eafbe432e913
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="exception-handling-differences"></a>Özel Durum İşleme Farkları
C++ özel durum türleri modeli anlaşmalar işleme yapılandırılmış özel durum işleme modeli C sırasında özel durumlar dışında bir tür ilgilenir yapılandırılmış özel durum işleme ve C++ özel durum işleme arasındaki en önemli fark olan — özellikle `unsigned int`. Diğer bir deyişle, C++ özel durumlarını veri türüne göre tanımlanır ancak C özel durumlar bir işaretsiz tamsayı değeri tarafından tanımlanır. C'de bir özel durum oluştuğunda, her olası işleyicisi C özel durum bağlamı inceler ve özel durum kabul edin, diğer bazı işleyicisine geçirmek ya da yok sayın belirleyen bir filtre yürütür. C++'da bir özel durum, herhangi bir türde olabilir.  
  
 İkinci bir fark, özel durumlar denetiminin normal akıştaki ikincil gerçekleşmesi C yapılandırılmış özel durum işleme modeli "zaman uyumsuz olarak için" denir, ' dir. C++ özel durum mekanizması işleme yalnızca zaman bunlar oluşturulan özel durumları ortaya başka bir deyişle, tam olarak "," uyumludur.  
  
 Bir C++ programı C özel durum oluşursa, C++ veya onun ilişkili filtre ile yapılandırılmış özel durum işleyici tarafından işlenebilir **catch** hangisi işleyicisidir dinamik olarak nearer to özel durum bağlamı. Örneğin, bir C özel bir C++ içinde aşağıdaki C++ programı başlatır **deneyin** bağlamı:  
  
## <a name="example"></a>Örnek  
  
```  
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
 Yukarıdaki gibi bir basit örnekte, yalnızca üç nokta C istisnası yakalanabilir (**...** ) **catch** işleyicisi. Tür veya özel durum doğası hakkında hiçbir bilgi işleyicisine iletilir. Bu yöntem çalışırken, bazı durumlarda, böylece her C özel durumu ile belirli bir sınıf ilişkilendirilen iki özel durum işleme modelleri arasında dönüştürme tanımlamak gerekebilir. Bunu yapmak için kullanılan veya bir C özel öznitelik belirli bir sınıf türü için türetilmiş bir C özel durum "sarmalayıcı" sınıfı, tanımlayabilirsiniz. Bunu yaparak, her C özel durumu C++ tarafından işlenebilir **catch** işleyici içinde daha fazla ayrı olarak önceki örnek.  
  
 Sarmalayıcı sınıfı, özel durum değeri belirlemek ve C özel durumu modeli tarafından sağlanan genişletilmiş özel durum bağlamını erişim bazı üye işlevleri oluşan bir arabirim olabilir. Varsayılan bir oluşturucu ve kabul eden bir oluşturucu tanımlamak isteyebilirsiniz bir `unsigned int` (için temel alınan C özel durumu temsil sağlamak için) bağımsız değişkeni ve bit düzeyinde kopya Oluşturucu. C özel durum sarmalayıcı sınıfı olası uyarlamasını verilmiştir:  
  
```  
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
  
 Bu sınıf kullanmak için işleme mekanizması C özel durum her zaman iç özel durum tarafından çağrılan özel bir C özel durumu çeviri işlev yükleyin. Çeviri işlevinizi içinde yazılan özel durumları atabilirsiniz (belki de bir `SE_Exception` türü ya da bir sınıf türü türetilen `SE_Exception`), yakalanan uygun eşleşen C++ tarafından **catch** işleyicisi. Çeviri işlevi yalnızca geri döndürülebilir istisnayı işlemedi gösterir. Çeviri işlevi bir C özel geçirirse [sonlandırmak](../c-runtime-library/reference/terminate-crt.md) olarak adlandırılır.  
  
 Özel çeviri işlevi belirtmek için arama [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) çeviri işlevinizi tek bağımsız değişken olarak adıyla işlevi. Her işlev çağrısını sahip yığında için yazdığınız çeviri işlevi bir kez çağrılır **deneyin** engeller. Hiçbir varsayılan çeviri işlevi yoktur; bir çağırarak belirtmezseniz, `_set_se_translator`, C özel durumu yalnızca üç nokta yakalanabilir **catch** işleyicisi.  
  
## <a name="example"></a>Örnek  
 Örneğin, aşağıdaki kod bir özel çeviri işlevi yükler ve tarafından Sarmalanan bir C özel durumu oluşturur `SE_Exception` sınıfı:  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)