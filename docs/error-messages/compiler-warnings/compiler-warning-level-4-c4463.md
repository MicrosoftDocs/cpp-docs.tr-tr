---
title: Derleyici Uyarısı (düzey 4) C4463
ms.date: 11/04/2016
f1_keywords:
- C4463
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
ms.openlocfilehash: e125a532f87533958ec43ed5580665ad4108856b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400805"
---
# <a name="compiler-warning-level-4-c4463"></a>Derleyici Uyarısı (düzey 4) C4463

> taşma; atama *değer* değerlerinden yalnızca içerebileceği bit alanına *low_value* için *high_value*

Atanan *değer* bit alanı barındırabilir değerler aralığının dışında. İmzalı bit alanı türleri kullanmak için oturum, bit üst sırası böylece *n* imzalı bit alanları için -2 bit alanı aralığı boyutudur<sup>n-1</sup> 2<sup>n-1</sup>işaretsiz sırada -1 bit alanları sahip bir aralığı 0-2<sup>n</sup>-1.

## <a name="example"></a>Örnek

Bu örnekte C4463 oluşturur ve bir bit alanı için tür 3 bir değer atamak çalışır çünkü `int` 2 boyutuna sahip 1 -2'den bir aralığa sahip.

Bu sorunu gidermek için izin verilen aralıktaki bir şey atanan değeri değiştirebilirsiniz. Bit alanı, işaretsiz değerleri 0-3 aralığında tutmak için amaçlanıyorsa, bildirim türüne değiştirebilirsiniz `unsigned`. Alan değerleri için aralığı -4 3'te tutmak için tasarlanmıştır, 3'e bit alanı boyutunu değiştirebilirsiniz.

```cpp
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S {
    int x : 2; // int type treats high-order bit as sign
};

int main() {
    S s;
    s.x = 3; // warning C4463: overflow; assigning 3
    // to bit-field that can only hold values from -2 to 1
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type
    // to unsigned.
}
```
