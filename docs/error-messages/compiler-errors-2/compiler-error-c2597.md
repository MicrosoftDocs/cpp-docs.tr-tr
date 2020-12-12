---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2597'
title: Derleyici hatası C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: b3430da85cef961b7c26b55e8dee9f1911533faf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120145"
---
# <a name="compiler-error-c2597"></a>Derleyici hatası C2597

statik olmayan ' Identifier ' üyesine başvuru geçersiz

Olası nedenler:

1. Statik üye işlevinde statik olmayan bir üye belirtilmiş. Statik olmayan üyeye erişmek için, sınıfın yerel bir örneğini geçirmeniz veya oluşturmanız ya da bir üye erişim işleci ( `.` veya) kullanmanız gerekir `->` .

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
