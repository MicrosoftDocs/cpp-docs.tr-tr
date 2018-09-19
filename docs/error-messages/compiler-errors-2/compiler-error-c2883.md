---
title: Derleyici Hatası C2883 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2883
dev_langs:
- C++
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50cc5b2abb34fae21bea78aa146e74b9aa9491c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019269"
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