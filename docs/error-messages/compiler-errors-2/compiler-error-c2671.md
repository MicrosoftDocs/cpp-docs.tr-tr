---
title: Derleyici Hatası C2671
ms.date: 11/04/2016
f1_keywords:
- C2671
helpviewer_keywords:
- C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
ms.openlocfilehash: 92ed646b0e4c5d2bbc6556c2a7b1ef66d8192ec1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165079"
---
# <a name="compiler-error-c2671"></a>Derleyici Hatası C2671

'function': statik üye işlevlerinde 'this' işaretçileri yoktur

A `static` üye işlevi erişmeyi denedi `this`.

Aşağıdaki örnek, C2671 oluşturur:

```
// C2671.cpp
struct S {
   static S* const func() { return this; }  // C2671
};
```