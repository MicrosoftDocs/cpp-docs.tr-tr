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
ms.openlocfilehash: 27ac76251456d9a0bf5908ad6d1fc2bee7534e9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360811"
---
# <a name="__restrict"></a>__restrict

__declspec ** [(kısıt)](../cpp/restrict.md) ** değiştirici gibi, **__restrict** anahtar kelimesi de bir sembolün geçerli kapsamda başka bir deyişle kullanılmadığını gösterir. anahtar kelime **__restrict** aşağıdaki `__declspec ( restrict )` şekillerde değiştirici farklıdır:

- **__restrict** anahtar kelimesi yalnızca değişkenler üzerinde `__declspec ( restrict )` geçerlidir ve yalnızca işlev bildirimleri ve tanımları için geçerlidir.

- **__restrict** C99 **spec'i kısıtlamaya** benzer, ancak **c++** veya C programlarında __restrict kullanılabilir.

- **__restrict** kullanıldığında, derleyici bir değişkenin diğer ad olmayan özelliğini yaymaz. Diğer bir de,**__restrict** olmayan bir değişkene **__restrict** bir değişken atarsanız, derleyici yine de __restrict olmayan değişkenin diğer adı verilmesine izin verir. Bu, c99 belirtiminden **kısıtlayan** anahtar kelimenin davranışından farklıdır.

Genellikle, tüm işlevin davranışını etkilerseniz, anahtar kelimeden daha iyi kullanılır. `__declspec ( restrict )`

Önceki sürümlerle uyumluluk için **_restrict,** derleyici seçeneği [/Za \(Dil uzantıları)](../build/reference/za-ze-disable-language-extensions.md) belirtilmedikçe **__restrict** eşanlamlıdır.

Visual Studio 2015 ve sonraki yıllarda **__restrict** C++ referanslarında kullanılabilir.

> [!NOTE]
> [Geçici](../cpp/volatile-cpp.md) anahtar kelimesi de olan bir değişkende kullanıldığında, **geçici** önceliğe sahip olur.

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
