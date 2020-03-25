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
ms.openlocfilehash: cb340554bc20516175400c4d14a5d0dba934a313
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188967"
---
# <a name="__restrict"></a>__restrict

**__Declspec ( [Restrict](../cpp/restrict.md) )** değiştiricisine benzer şekilde, **__restrict** anahtar sözcüğü geçerli kapsamda bir simgenin diğer adı olmadığını gösterir. **__Restrict** anahtar sözcüğü, `__declspec ( restrict )` değiştiricisinden aşağıdaki yollarla farklılık gösterir:

- **__Restrict** anahtar sözcüğü yalnızca değişkenlerde geçerlidir ve `__declspec ( restrict )` yalnızca işlev bildirimlerinde ve tanımlarda geçerlidir.

- **__restrict** , C99 spec **kısıtlaması** ile benzerdir, ancak **__restrict** C++ veya C programlarında kullanılabilir.

- **__Restrict** kullanıldığında, derleyici bir değişkenin diğer ad olmayan özelliğini yayılmaz. Diğer bir deyişle, bir **__restrict** değişkenini **__restrict** olmayan bir değişkene atarsanız, derleyici hala __restrict olmayan değişkenin diğer ad olarak izin vermeyecektir. Bu, C99 belirtiminin **Restrict** anahtar sözcüğünün davranışından farklıdır.

Genellikle, bir işlevin tüm davranışını etkileiyorsa, anahtar sözcükten daha `__declspec ( restrict )` kullanmak daha iyidir.

Önceki sürümlerle uyumluluk için, [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, **_restrict** **__restrict** için bir eş anlamlı.

Visual Studio 2015 ve üzeri sürümlerde **__restrict** C++ başvurularda kullanılabilir.

> [!NOTE]
>  [Geçici](../cpp/volatile-cpp.md) anahtar sözcüğü de olan bir değişkende kullanıldığında, **geçici** bir öncelik alır.

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

[Anahtar Sözcükler](../cpp/keywords-cpp.md)
