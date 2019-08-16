---
title: Özel Durum Filtresi Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
ms.openlocfilehash: f0234d36fb70c646e2d97540cbfa6ce5ae1e0ba9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498456"
---
# <a name="writing-an-exception-filter"></a>Özel Durum Filtresi Yazma

Özel bir durumu, özel durum işleyicisinin düzeyine atlayarak veya yürütmeyi devam ettirerek işleyebilirsiniz. Özel durumu işlemek ve üzerinde gezinmek için özel durum işleyici kodu kullanmak yerine, sorunu temizlemek için *filtreyi* kullanabilir ve sonra-1 ' i döndürerek, yığını temizlemeden normal akışı sürdürebilirsiniz.

> [!NOTE]
>  Bazı özel durumlar devam ettirilemez. Bu tür bir özel durum için *filtre* -1 olarak değerlendirilirse, sistem yeni bir özel durum oluşturur. [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception)çağırdığınızda, özel durumun devam edip etmediğini belirlersiniz.

Örneğin, aşağıdaki kod *filtre* ifadesinde bir işlev çağrısı kullanır: Bu işlev sorunu işler ve normal denetim akışını sürdürmeye yönelik-1 döndürür:

```cpp
// exceptions_Writing_an_Exception_Filter.cpp
#include <windows.h>
int main() {
   int Eval_Exception( int );

   __try {}

   __except ( Eval_Exception( GetExceptionCode( ))) {
      ;
   }

}
void ResetVars( int ) {}
int Eval_Exception ( int n_except ) {
   if ( n_except != STATUS_INTEGER_OVERFLOW &&
      n_except != STATUS_FLOAT_OVERFLOW )   // Pass on most exceptions
   return EXCEPTION_CONTINUE_SEARCH;

   // Execute some code to clean up problem
   ResetVars( 0 );   // initializes data to 0
   return EXCEPTION_CONTINUE_EXECUTION;
}
```

Filtrenin karmaşık her şeyi yapması gerektiğinde *filtre* ifadesinde bir işlev çağrısı kullanmak iyi bir fikirdir . İfadenin değerlendirilmesi işlevin, bu durumda `Eval_Exception`'ın yürütülmesine neden olur.

Özel durumu belirleyebilmek için [GetExceptionCode](/windows/win32/Debug/getexceptioncode) kullanımını göz önünde atın. Filtrenin içinde bu işlevi çağırmanız gerekir. `Eval_Exception`çağrılamıyor `GetExceptionCode`, ancak kendisine geçirilen özel durum kodu olmalıdır.

Bu işleyici, özel durum bir tamsayı veya kayan nokta taşması değilse deneyimi başka bir işleyiciye geçirir. Tamsayı veya kayan nokta taşmasıysa, işleyici bazı genel değişkenleri sıfırlamak için bir işlev çağırır (`ResetVars` yalnızca bir örnektir, API işlevi değildir). Bu örnekte boş olan *deyimin blok-2*' i hiçbir şekilde EXCEPTION_EXECUTE_HANDLER (1) döndürmediği `Eval_Exception` için hiçbir şekilde yürütülemez.

Bir işlev çağrısı kullanmak, karmaşık filtre ifadeleriyle başa çıkmak için genel anlamda iyi bir yöntemdir. Yararlı olan diğer iki C dili özelliği şunlardır:

- Koşullu işleç

- Virgül işleci

Koşullu işleç, belirli bir dönüş kodunu denetlemek ve ardından iki farklı değerden birini döndürmek için kullanılabildiğinden genellikle çok yararlı olur. Örneğin, aşağıdaki koddaki filtre özel durumu yalnızca özel durum STATUS_INTEGER_OVERFLOW ise tanır:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

Bu durumda koşullu işlecin amacı, temel olarak netlik sağlamaktır, çünkü aşağıdaki kod aynı sonuçları oluşturur:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

Koşullu operatör, filtrenin-1, EXCEPTION_CONTINUE_EXECUTION değerlendirmesini isteyebileceğiniz durumlarda daha yararlıdır.

Virgül işleci, tek bir ifade içerisinde birden fazla bağımsız işlemler gerçekleştirmenizi sağlar. Etkisi, kabaca birden fazla deyim yürütmeye ve ardından son ifadenin değerini döndürmeye benzerdir. Örneğin, aşağıdaki kod özel durum kodunu bir değişkende depolar ve ardından bunu test eder:

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)