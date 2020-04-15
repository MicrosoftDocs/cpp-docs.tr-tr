---
title: Özel durum filtresi yazma
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [C++], filters
ms.assetid: 47fc832b-a707-4422-b60a-aaefe14189e5
ms.openlocfilehash: 05d3aa79d1293001e80a77b3171b7a4607cd81c7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369478"
---
# <a name="writing-an-exception-filter"></a>Özel durum filtresi yazma

Özel bir durumu, özel durum işleyicisinin düzeyine atlayarak veya yürütmeyi devam ettirerek işleyebilirsiniz. Özel durum işlemek ve düşme işlemek için özel durum işleyicisi kodunu kullanmak yerine, sorunu temizlemek için *filtre* kullanabilirsiniz ve sonra, -1 döndürerek, yığını temizlemeden normal akışı devam.

> [!NOTE]
> Bazı özel durumlar devam ettirilemez. *Filtre* böyle bir özel durum için -1 olarak değerlendirirse, sistem yeni bir özel durum yükseltir. [Raise Exception'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception)aradiğinizde, özel durum devam edip etmeyeceğini belirlersiniz.

Örneğin, aşağıdaki kod *filtre* ifadesinde bir işlev çağrısı kullanır: bu işlev sorunu işler ve normal denetim akışını devam ettirmek için -1 döndürür:

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

*Filtrekarmaşık* bir şey yapması gerektiğinde *filtre* ifadesinde bir işlev çağrısı kullanmak iyi bir fikirdir. İfadenin değerlendirilmesi işlevin, bu durumda `Eval_Exception`'ın yürütülmesine neden olur.

Özel durumu belirlemek için [GetExceptionCode'un](/windows/win32/Debug/getexceptioncode) kullanımına dikkat edin. Filtrenin içinde bu işlevi çağırmanız gerekir. `Eval_Exception`arayamaz, `GetExceptionCode`ancak özel durum kodunun ona geçirilmesi gerekir.

Bu işleyici, özel durum bir tamsayı veya kayan nokta taşması değilse deneyimi başka bir işleyiciye geçirir. Tamsayı veya kayan nokta taşmasıysa, işleyici bazı genel değişkenleri sıfırlamak için bir işlev çağırır (`ResetVars` yalnızca bir örnektir, API işlevi değildir). Bu örnekte boş olan *deyim-blok-2,* hiçbir `Eval_Exception` zaman yürütülemez, çünkü hiçbir zaman EXCEPTION_EXECUTE_HANDLER (1) dönmez.

Bir işlev çağrısı kullanmak, karmaşık filtre ifadeleriyle başa çıkmak için genel anlamda iyi bir yöntemdir. Yararlı olan diğer iki C dili özelliği şunlardır:

- Koşullu işleç

- Virgül işleci

Koşullu işleç, belirli bir dönüş kodunu denetlemek ve ardından iki farklı değerden birini döndürmek için kullanılabildiğinden genellikle çok yararlı olur. Örneğin, aşağıdaki koddaki filtre, yalnızca özel durum STATUS_INTEGER_OVERFLOW aşağıdakidurumlarda özel durumu tanır:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

Bu durumda koşullu işlecin amacı, temel olarak netlik sağlamaktır, çünkü aşağıdaki kod aynı sonuçları oluşturur:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

Koşullu işleç, filtrenin -1, EXCEPTION_CONTINUE_EXECUTION olarak değerlendirilmesini isteyebileceğiniz durumlarda daha kullanışlıdır.

Virgül işleci, tek bir ifade içerisinde birden fazla bağımsız işlemler gerçekleştirmenizi sağlar. Etkisi, kabaca birden fazla deyim yürütmeye ve ardından son ifadenin değerini döndürmeye benzerdir. Örneğin, aşağıdaki kod özel durum kodunu bir değişkende depolar ve ardından bunu test eder:

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
