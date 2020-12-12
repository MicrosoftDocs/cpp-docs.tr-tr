---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4463'
title: Derleyici Uyarısı (düzey 4) C4463
ms.date: 11/04/2016
f1_keywords:
- C4463
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
ms.openlocfilehash: fe4ea13c50e16bf5b72f5753fa989970db3cadde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251329"
---
# <a name="compiler-warning-level-4-c4463"></a>Derleyici Uyarısı (düzey 4) C4463

> taşma yalnızca *low_value* *high_value* için değerler alabilen bit alanına *değer* atama

Atanan *değer* , bit alanının tutaabileceği değer aralığının dışındadır. İmzalı bit alanı türleri, oturum açma için yüksek sıra bitini kullanır. bu nedenle, *n* bit alanı boyutalıysa, işaretli bit alanları için Aralık-2 <sup>n-1</sup> ile 2 <sup>n-</sup>1-1 arasında bir aralığa sahip ve imzasız bit alanları 0 ile 2 <sup>n</sup>-1 arasında bir aralığa sahip olur.

## <a name="example"></a>Örnek

Bu örnek **`int`** ,-2 ile 1 arasında bir aralığa sahip olan ve 2 boyutunda bir bit alanına 3 değeri atamaya çalıştığı Için C4463 oluşturur.

Bu sorunu giderecek şekilde, atanan değeri izin verilen aralıktaki bir şekilde değiştirebilirsiniz. Bit alanı 0 ' dan 3 ' e kadar olan aralıkta işaretsiz değerler tutmaya amaçlanıyorsa, bildirim türünü olarak değiştirebilirsiniz **`unsigned`** . Alan,-4 ile 3 aralığında değer tutmaya amaçlanıyorsa, bit alanı boyutunu 3 olarak değiştirebilirsiniz.

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
