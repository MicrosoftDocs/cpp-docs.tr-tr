---
title: Derleyici hatası C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: 11e5792344b6f8fba6183f4ab87e1799db803b46
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757950"
---
# <a name="compiler-error-c3704"></a>Derleyici hatası C3704

' function ': bir vararg yöntemi olayları tetiklemez

Bir vararg yönteminde [__event](../../cpp/event.md) kullanmaya çalıştınız. Bu hatayı onarmak için, aşağıdaki kod örneğinde gösterildiği gibi `fireEvent(int i, ...)` çağrısını `fireEvent(int i)` çağrısıyla değiştirin.

Aşağıdaki örnek C3704 oluşturur:

```cpp
// C3704.cpp
[ event_source(native) ]
class CEventSrc {
   public:
      __event void fireEvent(int i, ...);   // C3704
      // try the following line instead:
      // __event void fireEvent(int i);
};

int main() {
}
```
