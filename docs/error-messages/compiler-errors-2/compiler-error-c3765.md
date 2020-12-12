---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3765'
title: Derleyici hatası C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 29de872030143ab33e1349f07ac3b81cb841e113
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234624"
---
# <a name="compiler-error-c3765"></a>Derleyici hatası C3765

' Event ': bir event_receiver olarak işaretlenmiş ' Type ' sınıfında/yapısına bir olay tanımlanamaz

Bir sınıf [event_receiver](../../windows/attributes/event-receiver.md) özniteliğiyle işaretlenmişse, sınıfı bir [__event](../../cpp/event.md) Bildirimi içeremez.

Aşağıdaki örnek C3765 oluşturur:

```cpp
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```
