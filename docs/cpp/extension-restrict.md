---
title: __restrict
ms.date: 10/10/2018
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
ms.openlocfilehash: 6318e6d78f6c4c4bb6827a79d26bca028dfe3f3f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233749"
---
# <a name="__restrict"></a>__restrict

**__Declspec ( [Restrict](../cpp/restrict.md) )** değiştiricisine benzer şekilde, **`__restrict`** anahtar sözcüğü geçerli kapsamda bir simgenin diğer adı olmadığını gösterir. **`__restrict`** Anahtar sözcüğü `__declspec ( restrict )` değiştiricisinden aşağıdaki yollarla farklılık gösterir:

- **`__restrict`** Anahtar sözcüğü yalnızca değişkenlerde geçerlidir ve `__declspec ( restrict )` yalnızca işlev bildirimlerinde ve tanımlarında geçerlidir.

- **`__restrict`**, **`restrict`** C99 spec ile benzerdir, ancak **`__restrict`** C++ veya C programlarında de kullanılabilir.

- Kullanıldığında **`__restrict`** , derleyici bir değişkenin diğer ad olmayan özelliğini yayılmaz. Diğer bir deyişle, değişken olmayan bir değişkeni bir değişkene atarsanız **`__restrict`** **`__restrict`** , derleyici __restrict olmayan değişkenin diğer adı da izin vermeye devam eder. Bu, **`restrict`** C99 belirtiminden anahtar sözcüğünün davranışından farklıdır.

Genellikle, bir işlevin tüm davranışını etkileiyorsa, anahtar sözcükten daha iyi bir şekilde kullanılır `__declspec ( restrict )` .

Önceki sürümlerle uyumluluk için, **_restrict** **`__restrict`** [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde _restrict için bir eş anlamlı.

Visual Studio 2015 ve üzeri sürümlerde **`__restrict`** C++ başvurularında kullanılabilir.

> [!NOTE]
> [Geçici](../cpp/volatile-cpp.md) anahtar sözcüğü de olan bir değişkende kullanıldığında **`volatile`** öncelikli olur.

## <a name="example"></a>Örnek

```cpp
// __restrict_keyword.c
// compile with: /LD
// In the following function, declare a and b as disjoint arrays
// but do not have same assurance for c and d.
void sum2(int n, int * __restrict a, int * __restrict b,
          int * c, int * d) {
   int i;
   for (i = 0; i < n; i++) {
      a[i] = b[i] + c[i];
      c[i] = b[i] + d[i];
    }
}

// By marking union members as __restrict, tell compiler that
// only z.x or z.y will be accessed in any given scope.
union z {
   int * __restrict x;
   double * __restrict y;
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
