---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3704'
title: Derleyici hatası C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: aae489b2d8657a1e62adc654d148be6cd0403af1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278187"
---
# <a name="compiler-error-c3704"></a>Derleyici hatası C3704

' function ': bir vararg yöntemi olayları tetiklemez

Bir vararg yönteminde [__event](../../cpp/event.md) kullanmaya çalıştınız. Bu hatayı düzeltemedi, çağrıyı `fireEvent(int i, ...)` `fireEvent(int i)` Aşağıdaki kod örneğinde gösterildiği gibi çağrı ile değiştirin.

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
