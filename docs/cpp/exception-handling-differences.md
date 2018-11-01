---
title: C++'ta yapılandırılmış özel durumları işleme
ms.date: 08/14/2018
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
ms.openlocfilehash: 2c4f1a8c3729e2b4d49a0152425e57717f7e9997
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482855"
---
# <a name="handle-structured-exceptions-in-c"></a>C++'ta yapılandırılmış özel durumları işleme

C arasındaki başlıca fark, özel durum işleme (SEH) yapılandırılmış ve C++ özel durum işleme modeli anlaşmalar türlerinde C++ özel durum işleme, yapılandırılmış özel durum işleme modeli sırasında C, bir tür özel durumlar ile ilgilenen ise; Özellikle, **işaretsiz int**. Diğer bir deyişle, C++ özel durumlarını veri türüyle tanımlanır ancak C özel durumlarını bir işaretsiz tamsayı değeri tarafından tanımlanır. C dilinde bir yapılandırılmış özel durum oluştuğunda, her olası işleyici C özel durum bağlamı inceler ve bu özel durum kabul edin, başka bir işleyiciye geçirmek ya da onu yok saymasını belirleyen bir filtre yürütür. C++'da bir özel durum oluştuğunda, bunu herhangi bir türde olabilir.

C yapılandırılmış özel durum işleme modeli olarak adlandırılır, ikinci bir fark olduğunu *zaman uyumsuz*, özel durumlar, denetiminin normal akışı için ikincil oluşur. C++ özel durum işleme mekanizmasını tam olan *zaman uyumlu*, yani yalnızca, bunlar özel özel durum oluşur.

Kullanırken [EHS veya/ehsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneği, C++ özel durum işleyicileri tanıtıcı yapılandırılmış özel durum yok. Bu özel durumların yalnızca işlenen **__catch** yapılandırılmış özel durum işleyicileri veya **__finally** yapılandırılmış sonlandırma işleyicileri. Bilgi için [yapılandırılmış özel durum işleme (C/C++)](structured-exception-handling-c-cpp.md).

Altında [/eha](../build/reference/eh-exception-handling-model.md) derleyici seçeneği, bir C++ programında C özel durum oluşturulursa, bunu bir C++ veya kendi ilişkili Filtresi ile bir yapılandırılmış özel durum işleyicisi tarafından işlenebilir **catch** hangisi işleyicisi dinamik olarak nearer to özel durum bağlamı. Örneğin, bir C özel durumu bir C++ içinde aşağıdaki C++ programı başlatan **deneyin** Bağlam:

## <a name="example---catch-a-c-exception-in-a-c-catch-block"></a>Örnek - C Catch özel durum bir C++'ta catch bloğu

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

## <a name="c-exception-wrapper-classes"></a>C özel durum sarmalayıcı sınıfları

Yukarıdaki gibi basit bir örnekte C özel durumu yalnızca üç nokta yakalanabilir (**...** ) **catch** işleyici. İşleyicinin veya özel durum doğası hakkında hiçbir bilgi iletilir. Bu yöntem çalışır, ancak bazı durumlarda, böylece her C özel durumu belirli bir sınıf ile ilişkili iki özel durum işleme modelleri arasında dönüştürme tanımlamak isteyebilirsiniz. Bunu yapmak için kullanılan veya bir C özel durumu için belirli bir sınıf türü özniteliği için türetilen bir C özel durum "sarmalayıcı" sınıfı tanımlayabilirsiniz. Bunun yapılması her C özel durum ayrı olarak belirli bir C++ tarafından işlenebilen **catch** işleyicisini, yerine tüm bunları tek bir işleyici.

Bazı üye işlevleri, özel durum değerini belirlemek ve C özel durum modeli tarafından sağlanan genişletilmiş özel durum bağlamı bilgilerini erişim oluşan bir arabirim, sarmalayıcı sınıfı olabilir. Varsayılan bir oluşturucu ve kabul eden bir kurucu tanımlamak isteyebilirsiniz bir **işaretsiz int** (temel alınan C özel durum temsili sağlamak için) bağımsız değişken ve bit düzeyinde bir kopya Oluşturucu. Olası bir uygulaması C özel durum sarmalayıcı sınıfı şöyledir:

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

Özel çeviri işlevi belirtmek için çağrı [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) tek bağımsız değişken olarak çeviri işlev uygulamanızın adıyla işlevi. Her yığında olan işlev çağrısını için yazdığınız çeviri işlevi bir kez çağrılır **deneyin** engeller. Hiçbir varsayılan çeviri işlevi yoktur; bir çağırarak belirtmezseniz **_set_se_translator**, C özel durumu yalnızca üç nokta yakalanabilir **catch** işleyici.

## <a name="example---use-a-custom-translation-function"></a>Örnek - Kullanım özel çeviri işlevi

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

[C (yapılandırılmış) ile C++ özel durumlarını karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)
