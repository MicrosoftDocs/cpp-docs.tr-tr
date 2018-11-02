---
title: Derleyici Hatası C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: 4e26742de6c294018f81c6f49c1719fdb11d5149
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467125"
---
# <a name="compiler-error-c3704"></a>Derleyici Hatası C3704

'function': bir vararg yöntemi olay başlatamaz

Kullanmaya çalıştığınız [__event](../../cpp/event.md) vararg yöntemi. Bu hatayı düzeltmek için değiştirin `fireEvent(int i, ...)` çağıran `fireEvent(int i)` aşağıdaki kod örneğinde gösterildiği gibi çağırın.

Aşağıdaki örnek, C3704 oluşturur:

```
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