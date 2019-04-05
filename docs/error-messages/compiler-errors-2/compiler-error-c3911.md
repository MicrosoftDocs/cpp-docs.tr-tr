---
title: Derleyici Hatası C3911
ms.date: 11/04/2016
f1_keywords:
- C3911
helpviewer_keywords:
- C3911
ms.assetid: b786da59-0e99-479d-bc0d-551126e940f2
ms.openlocfilehash: 25bf8def4e0a8085e20dc6ba9a04dc7f27cee651
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58775991"
---
# <a name="compiler-error-c3911"></a>Derleyici Hatası C3911

'event_accessor_method': işlevin türü 'imza' olmalıdır

Olay erişimci yöntemi düzgün olarak bildirilmedi.

Daha fazla bilgi için [olay](../../extensions/event-cpp-component-extensions.md).

Aşağıdaki örnek, C3911 oluşturur:

```
// C3911.cpp
// compile with: /clr
using namespace System;
delegate void H(String^, int);

ref class X {
   event H^ E1 {
      void add() {}   // C3911
      // try the following line instead
      // void add(H ^ h) {}

      void remove(){}
      // try the following line instead
      // void remove(H ^ h) {}

      void raise(){}
      // try the following line instead
      // void raise(String ^ s, int i) {}
   };
};
```