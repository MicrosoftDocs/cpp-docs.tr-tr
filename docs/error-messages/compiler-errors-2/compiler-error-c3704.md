---
title: Derleyici Hatası C3704 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3704
dev_langs:
- C++
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4504534e3a53f37089f0b0ba045b7afde5a8065d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054993"
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