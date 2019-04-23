---
title: Derleyici Uyarısı (düzey 4) C4754
ms.date: 11/04/2016
f1_keywords:
- C4754
helpviewer_keywords:
- C4754
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
ms.openlocfilehash: 203f2b97547c7ff8b1d68e3640e62d531b2600e9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779394"
---
# <a name="compiler-warning-level-4-c4754"></a>Derleyici Uyarısı (düzey 4) C4754

Bir karşılaştırma içindeki aritmetik işlemler için dönüştürme kuralları bir dalın yürütülemez anlamına gelir.

Karşılaştırmanın sonucu her zaman aynı olduğu için C4754 uyarı verilir. Bu, ilişkili tamsayı ifade hatalı olduğu bir koşulun dalların hiçbir zaman, büyük olasılıkla yerine getirildiğini gösterir. Bu kod hatası yanlış tamsayı taşması denetimlerini 64-bit mimarilerde sıklıkla oluşuyor.

Tamsayı dönüştürme kuralları karmaşıktır ve çoğu Zarif Tuzaklar vardır. Her C4754 uyarı düzeltiliyor alternatif olarak kullanmak için kodu güncelleştirebilirsiniz [SafeInt Kitaplığı](../../safeint/safeint-library.md).

## <a name="example"></a>Örnek

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

Ayrıca `a + b` sonucu bir 64-bit değere başvurmanıza önce aritmetik taşmaya neden olabilir ve 64-bit değişkene atanan `x`. Onay üzerinde buna `x` gereksizdir ve asla taşmaya catch olur. Bu durumda derleyici bu uyarıyı gösterir:

```Output
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754a.cpp (7) mean that one branch cannot be executed. Cast '(a + ...)' to 'ULONG64' (or similar type of 8 bytes).
```

Uyarıyı ortadan kaldırmak için 8-bayt değerleri işlenenlere atanacak atama ifadesi değiştirebilirsiniz:

```cpp
// Casting one operand is sufficient to force all the operands in
// the addition be upcast according to C/C++ conversion rules, but
// casting both is clearer.
unsigned long long x =
   (unsigned long long)a + (unsigned long long)b;
```

## <a name="example"></a>Örnek

Sonraki örnek, aynı zamanda C4754 oluşturur.

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

`sizeof()` İşleci döndürür bir `size_t`, boyutu mimari bağımlı. Örnek kod, 32-bit mimarilerde çalışır. burada bir `size_t` bir 32-bit türüdür. Ancak, 64-bit mimarilere üzerinde `size_t` bir 64-bit türüdür. Tamsayılar için dönüştürme kuralları anlamına `a` ifadesindeki bir 64-bit değere başvurmanıza olduğu `a + b < a` gibi yazılmışsa `(size_t)a + (size_t)b < (size_t)a`. Zaman `a` ve `b` 32 bit tam sayılar olduğundan, 64-bit toplama işlemi hiçbir zaman taşırabilir ve hiçbir zaman kısıtlaması tutar. Sonuç olarak, kodu asla 64-bit mimarilerde bir tamsayı taşma durumu algılar. Bu örnekte, derleyici bu uyarıyı yaymak neden olur:

```Output
Warning C4754: Conversion rules for arithmetic operations in the comparison at C4754b.cpp (7) mean that one branch cannot be executed. Cast '4' to 'ULONG' (or similar type of 4 bytes).
```

Uyarı iletisini açıkça yerine orijinal kaynak dize sabit değeri 4 göz önünde bulundurun — zaman uyarı çözümleme sorunlu kod karşılaştığında `sizeof(unsigned long)` zaten bir sabite dönüştürüldü. Bu nedenle, izlemek hangi kaynak ifadesinde kod uyarı iletisinde sabit değerle ilişkili çalışmıyor olabilir. En yaygın kaynaklardan C4754 uyarı iletilerini sabitlerle çözümlendi kod gibi ifadelerdir `sizeof(TYPE)` ve `strlen(szConstantString)`.

Bu durumda, sabit kod bu benzeyecektir:

```cpp
// Casting the result of sizeof() to unsigned long ensures
// that all the addition operands are 32-bit, so any overflow
// is detected by the check.
if (a + (unsigned long)sizeof(unsigned long) < a)
```

**Not** son satır deyiminin başvurulan Derleyici uyarılarını satır numarası değil. Çoklu satırlar üzerinde yayılan karmaşık bir koşullu deyim hakkında bir uyarı iletisinde bildirilen satırından önce birkaç satır kod hatası olan satırın olabilir. Örneğin:

```cpp
unsigned long a;

if (a + sizeof(unsigned long) < a || // incorrect check
    condition1() ||
    a == 0) {    // C4754 warning reported on this line
         // never executes!
         return INVALID_PARAMETER;
}
```