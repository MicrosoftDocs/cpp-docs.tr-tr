---
title: Derleyici Hatası C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: b78b9dd69b701e1a66646234d4603973657e90c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366400"
---
# <a name="compiler-error-c2583"></a>Derleyici Hatası C2583

'identifier': ' const/volatile' 'this' işaretçisi oluşturucular/yok ediciler için geçersizdir

Bir oluşturucu veya yıkıcı bildirilen `const` veya `volatile`. Buna izin verilmez.

Aşağıdaki örnek, C2583 oluşturur:

```
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```