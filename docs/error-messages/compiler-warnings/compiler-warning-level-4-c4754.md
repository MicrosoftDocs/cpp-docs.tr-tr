---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4754'
title: Derleyici Uyarısı (düzey 4) C4754
ms.date: 11/04/2016
f1_keywords:
- C4754
helpviewer_keywords:
- C4754
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
ms.openlocfilehash: b997f81a7d922837ff3f1ea2e5d015e5267428dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330522"
---
# <a name="compiler-warning-level-4-c4754"></a>Derleyici Uyarısı (düzey 4) C4754

Bir karşılaştırmada aritmetik işlemler için dönüştürme kuralları bir dalın yürütülemeyeceği anlamına gelir.

Karşılaştırma sonucu her zaman aynı olduğundan C4754 uyarısı verilir. Bu, büyük olasılıkla ilişkili tamsayı ifadesi yanlış olduğu için koşulun dallarından birinin hiçbir şekilde yürütülmediğini belirtir. Bu kod hatası genellikle 64 bitlik mimarilerde yanlış tamsayı taşma denetimlerinde oluşur.

Tamsayı dönüştürme kuralları karmaşıktır ve çok sayıda hafif ekde vardır. Her C4754 uyarısını düzeltmeye alternatif olarak, kodu [SafeInt kitaplığını](../../safeint/safeint-library.md)kullanacak şekilde güncelleştirebilirsiniz.

## <a name="examples"></a>Örnekler

Bu örnek C4754 oluşturur:

```cpp
// C4754a.cpp
// Compile with: /W4 /c
#include "errno.h"

int sum_overflow(unsigned long a, unsigned long b)
{
   unsigned long long x = a + b; // C4754

   if (x > 0xFFFFFFFF)
   {
      // never executes!
      return EOVERFLOW;
   }
   return 0;
}
```

`a + b`Bunun nedeni, sonuç 64 bitlik bir değere dönüştürme ve 64 bit değişkenine atanmasından önce aritmetik taşmaya neden olabilir `x` . Bu, onay açık `x` olduğu ve hiçbir şekilde bir taşma yakalayamayacağı anlamına gelir. Bu durumda, derleyici şu uyarıyı yayar:

```Output
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754a.cpp (7) mean that one branch cannot be executed. Cast '(a + ...)' to 'ULONG64' (or similar type of 8 bytes).
```

Uyarıyı ortadan kaldırmak için, atama ifadesini, işlenenleri 8 baytlık değerlere dönüştürmek üzere değiştirebilirsiniz:

```cpp
// Casting one operand is sufficient to force all the operands in
// the addition be upcast according to C/C++ conversion rules, but
// casting both is clearer.
unsigned long long x =
   (unsigned long long)a + (unsigned long long)b;
```

Sonraki örnek ayrıca C4754 oluşturur.

```cpp
// C4754b.cpp
// Compile with: /W4 /c
#include "errno.h"

int wrap_overflow(unsigned long a)
{
   if (a + sizeof(unsigned long) < a) // C4754
   {
      // never executes!
      return EOVERFLOW;
   }
   return 0;
}
```

`sizeof()`İşleci, `size_t` boyutu mimariye bağlı olan bir döndürür. Örnek kod, bir `size_t` 32 bit tür olan 32 bitlik mimarilerde çalışmaktadır. Ancak, 64 bit mimarilerde `size_t` 64 bit bir türdür. Tamsayılar için dönüştürme kuralları, `a` yazılmış gibi ifadede 64 bitlik bir değere yukarı dönüştürme anlamına gelir `a + b < a` `(size_t)a + (size_t)b < (size_t)a` . `a`Ve `b` 32 bitlik tamsayılar olduğunda, 64 bit toplama işlemi hiçbir zaman taşmamalıdır ve kısıtlama hiçbir zaman tutmamalıdır. Sonuç olarak, kod 64-bit mimarilerinde hiçbir bir tamsayı taşma koşulunu hiçbir şekilde algılamıyor. Bu örnek, derleyicinin bu uyarıyı yaymasına neden olur:

```Output
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754b.cpp (7) mean that one branch cannot be executed. Cast '4' to 'ULONG' (or similar type of 4 bytes).
```

Uyarı iletisinin özgün kaynak dize yerine 4 sabit değerini açıkça listelediğine ve uyarı analizinin, sorunlu kodla karşılaştığı zamana göre, `sizeof(unsigned long)` zaten bir sabite dönüştürüldüğüne dikkat edin. Bu nedenle, kaynak kodundaki hangi ifadenin Uyarı iletisindeki sabit değerle ilişkili olduğunu izlemeniz gerekebilir. C4754 uyarı iletilerinde sabitlere çözümlenen en yaygın kod kaynakları, ve gibi ifadelerdir `sizeof(TYPE)` `strlen(szConstantString)` .

Bu durumda, sabit kod şuna benzer:

```cpp
// Casting the result of sizeof() to unsigned long ensures
// that all the addition operands are 32-bit, so any overflow
// is detected by the check.
if (a + (unsigned long)sizeof(unsigned long) < a)
```

**Göz önünde** Derleyici uyarılarında başvurulan satır numarası, bir deyimin son satırındır. Birden çok satıra yayılan karmaşık koşullu bir ifade hakkında uyarı iletisinde, kod hatası içeren satır, bildirilen satırdan önce birkaç satır olabilir. Örnek:

```cpp
unsigned long a;

if (a + sizeof(unsigned long) < a || // incorrect check
    condition1() ||
    a == 0) {    // C4754 warning reported on this line
         // never executes!
         return INVALID_PARAMETER;
}
```
