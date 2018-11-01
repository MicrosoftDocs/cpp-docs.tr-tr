---
title: Derleyici Hatası C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: 3f32307e519394433927d49aa92333fdff7b70f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587518"
---
# <a name="compiler-error-c2883"></a>Derleyici Hatası C2883

'name': işlev bildirimi bildirim kullanımı ile tanıtılan'identifier ' çakışıyor

Birden çok kez bir fonksiyon tanımlayın denedi. İlk tanımı bir ad alanı ile yapılan bir `using` bildirimi. İkincisi, yerel bir tanım belirtildi.

Aşağıdaki örnek, C2883 oluşturur:

```
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```