---
title: Derleyici hatası C3701
ms.date: 11/04/2016
f1_keywords:
- C3701
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
ms.openlocfilehash: c15cd9ce841d79787b3be9829c76038803b54d4d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508063"
---
# <a name="compiler-error-c3701"></a>Derleyici hatası C3701

' function ': event_source hiç olayı yok

Olay yöntemi olmayan bir sınıfta [event_source](../../windows/attributes/event-source.md) kullanmaya çalıştınız. Bu hatayı onarmak için, sınıfa bir veya daha fazla olay ekleyin.

Aşağıdaki örnek C3701 oluşturur:

```cpp
// C3701.cpp
[ event_source(native) ]
class CEventSrc {
public:
   // uncomment the following line to resolve this C3701
   // __event void fireEvent(int i);
};   // C3701

int main() {
}
```
