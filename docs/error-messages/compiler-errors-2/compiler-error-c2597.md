---
title: Derleyici Hatası C2597
ms.date: 11/04/2016
f1_keywords:
- C2597
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
ms.openlocfilehash: b7bdd10ebd70eb61746690958532854dd98c6429
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228596"
---
# <a name="compiler-error-c2597"></a>Derleyici Hatası C2597

'identifier' statik olmayan üyeye geçersiz başvuru

Olası nedenler:

1. Statik olmayan üye bir statik üye işlevinde belirtilir. Statik olmayan üyeye erişmek için geçirin veya yerel bir sınıfın örneğini oluşturma ve üye erişimi işlecini kullanmanız gerekir (`.` veya `->`).

1. Belirtilen tanımlayıcı bir sınıf, yapı veya birleşim üyesi değil. Tanımlayıcı yazım denetimi yapar.

1. Üye erişimi işleci değiştiricilere işlevine başvuruyor.

1. Aşağıdaki örnek, C2597 oluşturur ve bu sorunun nasıl gösterir:

```
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