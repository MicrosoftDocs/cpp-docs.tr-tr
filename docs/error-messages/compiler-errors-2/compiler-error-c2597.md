---
title: Derleyici hatası C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: 680268948f8642b02768bd4b3092666982e14eb7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759314"
---
# <a name="compiler-error-c2597"></a>Derleyici hatası C2597

statik olmayan ' Identifier ' üyesine başvuru geçersiz

Olası nedenler:

1. Statik üye işlevinde statik olmayan bir üye belirtilmiş. Statik olmayan üyeye erişmek için, sınıfın yerel bir örneğini geçirmeniz veya oluşturmanız ya da bir üye erişim işleci (`.` ya da `->`) kullanmanız gerekir.

1. Belirtilen tanımlayıcı bir sınıf, yapı veya birleşimin üyesi değil. Tanımlayıcı yazımını denetleyin.

1. Üye erişim işleci üye olmayan bir işleve başvurur.

1. Aşağıdaki örnek C2597 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2597.cpp
// compile with: /c
struct s1 {
   static void func();
   static void func2(s1&);
   int i;
};

void s1::func() {
   i = 1;    // C2597 - static function can't access non-static data member
}

// OK - fix by passing an instance of s1
void s1::func2(s1& a) {
   a.i = 1;
}
```
