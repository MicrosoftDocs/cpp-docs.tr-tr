---
title: '`__restrict`'
description: Microsoft Visual C++ `__restrict` anahtar sözcüğünü açıklar.
ms.date: 11/6/2020
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.openlocfilehash: f23574f49712928e0095f29a3b88b0c05b185eab
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381577"
---
# `__restrict`

**`__declspec` ( [`restrict`](../cpp/restrict.md) )** Değiştiricisine benzer şekilde, **`__restrict`** anahtar sözcüğü (iki önde gelen alt çizgi ' _ '), bir simgenin geçerli kapsamda diğer ad olmadığını gösterir. **`__restrict`** Anahtar sözcüğü `__declspec (restrict)` değiştiricisinden aşağıdaki yollarla farklılık gösterir:

- **`__restrict`** Anahtar sözcüğü yalnızca değişkenlerde geçerlidir ve `__declspec (restrict)` yalnızca işlev bildirimlerinde ve tanımlarında geçerlidir.

- **`__restrict`**[`restrict`](../c-language/type-qualifiers.md#restrict), C99 ile başlayan, ancak **`__restrict`** hem C++ hem de C programlarında kullanılabilen C için benzerdir.

- Kullanıldığında **`__restrict`** , derleyici bir değişkenin diğer ad olmayan özelliğini yayılmaz. Diğer bir deyişle, değişken olmayan bir değişkeni bir değişkene atarsanız **`__restrict`** **`__restrict`** , derleyici __restrict olmayan değişkenin diğer adı da izin vermeye devam eder. Bu, C99 C Language anahtar sözcüğünün davranışından farklıdır **`restrict`** .

Genellikle, tüm işlevin davranışını etkilemek istiyorsanız **`__declspec (restrict)`** anahtar sözcüğü yerine kullanın.

Önceki sürümlerle uyumluluk için, **`_restrict`** **`__restrict`** derleyici seçeneği [ `/Za` \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) ' ın belirtildiği durumlar için bir eş anlamlı olur.

Visual Studio 2015 ve üzeri sürümlerde **`__restrict`** C++ başvurularında kullanılabilir.

> [!NOTE]
> Anahtar sözcüğü de olan bir değişkende kullanıldığında [`volatile`](../cpp/volatile-cpp.md) **`volatile`** öncelikli olur.

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
