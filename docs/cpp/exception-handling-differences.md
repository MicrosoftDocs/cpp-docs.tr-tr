---
title: C++ dilinde yapılandırılmış özel durumları işleme
description: C++ Özel durum işleme modelini kullanarak yapılandırılmış özel durumları işleme.
ms.date: 09/19/2019
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
ms.openlocfilehash: 0c0e458f576325034d77676d247020adedfa33e5
ms.sourcegitcommit: f907b15f50a6b945d0b87c03af0050946157d701
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71158734"
---
# <a name="handle-structured-exceptions-in-c"></a>C++ dilinde yapılandırılmış özel durumları işleme

C yapılandırılmış özel durum işleme (SEH) ve C++ özel durum işleme arasındaki önemli fark, C++ özel durum işleme modelinin türler halinde ele aldığı, ancak c yapılandırılmış özel durum işleme modelinin tek bir türden özel durumlarla ilgilenir. Özellikle, **işaretsiz int**. Diğer bir deyişle, C özel durumları işaretsiz bir tamsayı değeri tarafından tanımlanır, C++ ancak özel durumlar veri türü tarafından tanımlanır. C 'de yapılandırılmış bir özel durum oluşturulduğunda, olası her işleyici C özel durum bağlamını inceleyen bir filtre yürütür ve özel durumun kabul edilip edilmeyeceğini, başka bir işleyiciye iletmesinin veya yoksayılacağını belirler. İçinde C++bir özel durum oluştuğunda, herhangi bir türde olabilir.

İkinci bir fark, C yapılandırılmış özel durum işleme modelinin *zaman uyumsuz*olarak başvurulduğu, çünkü özel durumlar normal denetim akışına ikincil olarak gerçekleşmektedir. C++ Özel durum işleme mekanizması tamamen *zaman uyumludur*. Bu, özel durumların yalnızca oluşturulduğu zaman oluşması anlamına gelir.

[/EHS veya/EHsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullandığınızda, C++ özel durum işleyicileri yapılandırılmış özel durumları işlemez. Bu özel durumlar yalnızca **__except** yapılandırılmış özel durum işleyicileri veya **__finally** yapılandırılmış sonlandırma işleyicileri tarafından işlenir. Bilgi için bkz. [yapılandırılmış özel durum işleme (CC++/)](structured-exception-handling-c-cpp.md).

[/EHa](../build/reference/eh-exception-handling-model.md) derleyici seçeneğinin altında, bir C++ programda bir C özel durumu ortaya çıktığında, ilişkili filtresiyle veya bir C++ **catch** işleyicisiyle, özel duruma dinamik olarak yaklaştığında bu bir yapılandırılmış özel durum işleyicisi tarafından işlenebilir. bağlam. Örneğin, bu örnek C++ program bir C++ **TRY** bağlamı içinde bir C özel durumu oluşturur:

## <a name="example---catch-a-c-exception-in-a-c-catch-block"></a>Örnek-bir C++ catch bloğunda C özel durumunu yakala

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

Yukarıdaki gibi basit bir örnekte C özel durumu yalnızca üç nokta ( **...** ) ile yakalanabilir. **catch** işleyicisi. Özel durumun türü veya doğası hakkında hiçbir bilgi işleyiciye iletilir. Bu yöntem çalışırken, bazı durumlarda her C özel durumunun belirli bir sınıfla ilişkilendirilmesi için iki özel durum işleme modeli arasında bir dönüşüm tanımlamak isteyebilirsiniz. Bir tane dönüştürmek için, belirli bir sınıf türünü C özel durumuna dönüştürmek üzere ' de kullanılabilen veya türetilebilen bir C özel durum "sarmalayıcı" sınıfı tanımlayabilirsiniz. Bu şekilde, her C özel durumu tek bir işleyicide değil, belirli C++ bir **catch** işleyicisi tarafından ayrı olarak işlenebilir.

Sarmalayıcı sınıfınız, özel durumun değerini tespit eden bazı üye işlevlerinden oluşan ve C özel durum modeli tarafından sunulan genişletilmiş özel durum bağlam bilgilerine erişen bir arabirime sahip olabilir. Ayrıca, bir varsayılan Oluşturucu ve **işaretsiz bir tamsayı** bağımsız değişkeni kabul eden bir Oluşturucu (temeldeki C özel durum gösterimini sağlamak için) ve bit düzeyinde bir kopya Oluşturucu da tanımlamak isteyebilirsiniz. C özel durum sarmalayıcı sınıfının olası bir uygulamasıdır:

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

Bu sınıfı kullanmak için, bir C özel durumu oluştuğunda iç özel durum işleme mekanizması tarafından çağrılan özel bir C özel durum çevirisi işlevi yüklersiniz. Çeviri işlevinizde, uygun bir `SE_Exception` eşleşen `SE_Exception` C++ **catch** işleyicisi tarafından yakalanabileceği herhangi bir tür özel durum (Belki de bir tür veya öğesinden türetilmiş bir sınıf türü) oluşturabilirsiniz. Çeviri işlevi bunun yerine, özel durumu işlemediğini belirten döndürebilir. Çeviri işlevinin kendisi bir C özel durumu harekete geçirirse, [Terminate](../c-runtime-library/reference/terminate-crt.md) çağırılır.

Özel bir çeviri işlevi belirtmek için, [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) işlevini çeviri işlevinizin adı ile tek bağımsız değişken olarak çağırın. Yazdığınız çeviri işlevi, **TRY** blokları olan yığında her bir işlev çağrısı için bir kez çağrılır. Varsayılan çeviri işlevi yoktur; **_set_se_translator**çağırarak bir tane belirtmezseniz, C özel durumu yalnızca üç nokta **catch** işleyicisi tarafından yakalanamaz.

## <a name="example---use-a-custom-translation-function"></a>Örnek-özel bir çeviri işlevi kullanın

Örneğin, aşağıdaki kod özel bir çeviri işlevi yüklüyor ve sonra `SE_Exception` sınıfı tarafından Sarmalanan bir C özel durumu oluşturuyor:

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

[C (yapılandırılmış) ve C++ özel durumları karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)
