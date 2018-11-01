---
title: Derleyici Hatası C3912
ms.date: 11/04/2016
f1_keywords:
- C3912
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
ms.openlocfilehash: c6eb207342f44655d54e49d4cf0cd2410f7095da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562038"
---
# <a name="compiler-error-c3912"></a>Derleyici Hatası C3912

'event': olayın türü bir temsilci türü olmalıdır

Bir olay olarak bildirildi, ancak doğru türde değildi.

Daha fazla bilgi için [olay](../../windows/event-cpp-component-extensions.md).

Aşağıdaki örnek, C3912 oluşturur:

```
// C3912.cpp
// compile with: /clr
delegate void H();
ref class X {
   event int Ev;   // C3912
   event H^ Ev2;   // OK
};
```