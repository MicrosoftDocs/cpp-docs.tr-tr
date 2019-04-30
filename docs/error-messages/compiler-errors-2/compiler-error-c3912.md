---
title: Derleyici Hatası C3912
ms.date: 11/04/2016
f1_keywords:
- C3912
helpviewer_keywords:
- C3912
ms.assetid: 674e050c-11fb-4db1-8bdf-a3e95b41161d
ms.openlocfilehash: bd66196c35715304577b8f6785261be8bdcdafec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406684"
---
# <a name="compiler-error-c3912"></a>Derleyici Hatası C3912

'event': olayın türü bir temsilci türü olmalıdır

Bir olay olarak bildirildi, ancak doğru türde değildi.

Daha fazla bilgi için [olay](../../extensions/event-cpp-component-extensions.md).

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