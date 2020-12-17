---
description: Yapısal bir özel durum filtresi yazma hakkında daha fazla bilgi edinin.
title: Özel durum filtresi yazma
ms.date: 12/16/2020
helpviewer_keywords:
- exception handling [C++], filters
ms.openlocfilehash: 8b6706c7dfe0e96e26f77f1f3a452db638141803
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645065"
---
# <a name="writing-an-exception-filter"></a>Özel durum filtresi yazma

Özel bir durumu, özel durum işleyicisinin düzeyine atlayarak veya yürütmeyi devam ettirerek işleyebilirsiniz. Özel durumu işlemek ve üzerinde gezinmek için özel durum işleyici kodu kullanmak yerine, sorunu temizlemek için bir *filtre* ifadesi kullanabilirsiniz. Ardından, `EXCEPTION_CONTINUE_EXECUTION` (-1) öğesini döndürerek, yığını temizlemeden normal akışı sürdürebilirsiniz.

> [!NOTE]
> Bazı özel durumlar devam ettirilemez. Bu tür bir özel durum için *filtre* -1 olarak değerlendirilirse, sistem yeni bir özel durum oluşturur. [`RaiseException`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception)' İ çağırdığınızda, özel durumun devam edip etmediğini belirlersiniz.

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

Filtrenin karmaşık her şeyi *yapması gerektiğinde* *filtre* ifadesinde bir işlev çağrısı kullanmak iyi bir fikirdir. İfadenin değerlendirilmesi işlevin, bu durumda `Eval_Exception`'ın yürütülmesine neden olur.

[`GetExceptionCode`](/windows/win32/Debug/getexceptioncode)Özel durumu öğrenmek için kullanımını göz önünde edin. Bu işlev, deyiminin filtre ifadesinin içinde çağrılmalıdır **`__except`** . `Eval_Exception` çağrılamıyor `GetExceptionCode` , ancak kendisine geçirilen özel durum kodu olmalıdır.

Bu işleyici, özel durum bir tamsayı veya kayan nokta taşması değilse deneyimi başka bir işleyiciye geçirir. Tamsayı veya kayan nokta taşmasıysa, işleyici bazı genel değişkenleri sıfırlamak için bir işlev çağırır (`ResetVars` yalnızca bir örnektir, API işlevi değildir). **`__except`** Bu örnekte boş olan bildiri bloğu hiçbir `Eval_Exception` süre (1) döndürülmediği için hiçbir şekilde yürütülemez `EXCEPTION_EXECUTE_HANDLER` .

Bir işlev çağrısı kullanmak, karmaşık filtre ifadeleriyle başa çıkmak için genel anlamda iyi bir yöntemdir. Yararlı olan diğer iki C dili özelliği şunlardır:

- Koşullu işleç

- Virgül işleci

Koşullu operatör genellikle burada yararlı olur. Bu, belirli bir dönüş kodunu denetlemek ve sonra iki farklı değerden birini döndürmek için kullanılabilir. Örneğin, aşağıdaki koddaki filtre özel durumu yalnızca özel durum ise tanır `STATUS_INTEGER_OVERFLOW` :

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ? 1 : 0 ) {
```

Bu durumda koşullu işlecin amacı, temel olarak netlik sağlamaktır, çünkü aşağıdaki kod aynı sonuçları oluşturur:

```cpp
__except( GetExceptionCode() == STATUS_INTEGER_OVERFLOW ) {
```

Koşullu operatör, filtrenin-1 ' i değerlendirmesini isteyebileceğiniz durumlarda daha yararlıdır `EXCEPTION_CONTINUE_EXECUTION` .

Virgül işleci birden çok ifadeyi sırayla yürütmenize olanak sağlar. Ardından, son ifadenin değerini döndürür. Örneğin, aşağıdaki kod özel durum kodunu bir değişkende depolar ve ardından bunu test eder:

```cpp
__except( nCode = GetExceptionCode(), nCode == STATUS_INTEGER_OVERFLOW )
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
