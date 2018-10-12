---
title: __restrict | Microsoft Docs
ms.custom: ''
ms.date: 10/10/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
dev_langs:
- C++
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9245571e21be04cc250347f30ce8ddb464ff9b55
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163458"
---
# <a name="restrict"></a>__restrict

Gibi **__declspec ( [kısıtlama](../cpp/restrict.md) )** değiştiricisi **__restrict** anahtar sözcüğü gösteren bir simge geçerli kapsamda diğer adı değil. **__Restrict** anahtar sözcüğünden farklıdır `__declspec ( restrict )` aşağıdaki yollarla değiştiricisi:

- **__Restrict** anahtar sözcüğü yalnızca değişkenler üzerinde geçerlidir ve `__declspec ( restrict )` yalnızca işlev bildirimleri ve tanımları üzerinde geçerlidir.

- **__restrict** benzer **kısıtlama** C99 belirtimi gelen ancak **__restrict** C ya da C++ programlarında kullanılabilir.

- Zaman **__restrict** olan kullanıldığında, derleyici değişkenin diğer ad olmayan özelliğini yaymayacaktır. Diğer bir deyişle, atarsanız bir **__restrict** olmayan bir değişken **__restrict** değişken, derleyici hala sağlayacak __restrict olmayan değişkenine diğer adı olması. Bu davranışından farklıdır **kısıtlama** C99 belirtimindeki from anahtar sözcüğü.

Tüm işlevin davranışını etkilerseniz, genellikle bunu kullanmak en iyisidir `__declspec ( restrict )` daha anahtar sözcüğü.

Önceki sürümlerle uyumluluk için **_restrict** eşanlamlıdır **__restrict** sürece derleyici seçeneği [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) olduğu Belirtilen.

Visual Studio 2015 ve sonraki sürümlerinde, **__restrict** C++ başvuruları üzerinde kullanılabilir.

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