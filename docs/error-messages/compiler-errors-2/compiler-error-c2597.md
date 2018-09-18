---
title: Derleyici Hatası C2597 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2597
dev_langs:
- C++
helpviewer_keywords:
- C2597
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9f8deb325ae54393518698263f3ca93ca88ca48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114455"
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