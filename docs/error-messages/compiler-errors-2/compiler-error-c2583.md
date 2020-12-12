---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2583'
title: Derleyici hatası C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: 067e65f6085d033ca8d7372ee5e4d169e1b411dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177698"
---
# <a name="compiler-error-c2583"></a>Derleyici hatası C2583

' tanımlayıcı ': ' const/volatile ' ' this ' işaretçisi oluşturucular/yok ediciler için geçersizdir

Bir Oluşturucu veya yıkıcı, veya olarak bildirilmiştir **`const`** **`volatile`** . Buna izin verilmez.

Aşağıdaki örnek C2583 oluşturur:

```cpp
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
