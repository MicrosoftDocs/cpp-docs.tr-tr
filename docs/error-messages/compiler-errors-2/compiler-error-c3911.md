---
title: Derleyici Hatası C3911 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3911
dev_langs:
- C++
helpviewer_keywords:
- C3911
ms.assetid: b786da59-0e99-479d-bc0d-551126e940f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98b2b1b4712d71c5baa7179ce3c348ace3761bb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037391"
---
# <a name="compiler-error-c3911"></a>Derleyici Hatası C3911

'event_accessor_method': işlevin türü 'imza' olmalıdır

Olay erişimci yöntemi düzgün olarak bildirilmedi.

Daha fazla bilgi için [olay](../../windows/event-cpp-component-extensions.md).

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