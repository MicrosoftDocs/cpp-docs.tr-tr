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
ms.openlocfilehash: 76cdf9424e6eab33a3a92b3f98d9c2b0b04ff667
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183758"
---
# <a name="restrict"></a>__restrict

Gibi **__declspec ( [kısıtlama](../cpp/restrict.md) )** değiştiricisi **__restrict** anahtar sözcüğü gösteren bir simge geçerli kapsamda diğer adı değil. **__Restrict** anahtar sözcüğünden farklıdır `__declspec ( restrict )` aşağıdaki yollarla değiştiricisi:

- **__Restrict** anahtar sözcüğü yalnızca değişkenler üzerinde geçerlidir ve `__declspec ( restrict )` yalnızca işlev bildirimleri ve tanımları üzerinde geçerlidir.

- **__restrict** benzer **kısıtlama** C99 belirtimi gelen ancak **__restrict** kullanılabilir C++ veya C programları.

- Zaman **__restrict** olan kullanıldığında, derleyici değişkenin diğer ad olmayan özelliğini yaymayacaktır. Diğer bir deyişle, atarsanız bir **__restrict** olmayan bir değişken **__restrict** değişken, derleyici hala sağlayacak __restrict olmayan değişkenine diğer adı olması. Bu davranışından farklıdır **kısıtlama** C99 belirtimindeki from anahtar sözcüğü.

Tüm işlevin davranışını etkilerseniz, genellikle bunu kullanmak en iyisidir `__declspec ( restrict )` daha anahtar sözcüğü.

Önceki sürümlerle uyumluluk için **_restrict** eşanlamlıdır **__restrict** sürece derleyici seçeneği [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) olduğu Belirtilen.

Visual Studio 2015 ve sonraki sürümlerinde, **__restrict** kullanılabilir C++ başvuruları.

> [!NOTE]
>  Ayrıca bir değişken üzerinde kullanıldığında [geçici](../cpp/volatile-cpp.md) anahtar sözcüğü, **geçici** öncelikli olur.

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