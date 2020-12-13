---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3919'
title: Derleyici hatası C3919
ms.date: 11/04/2016
f1_keywords:
- C3919
helpviewer_keywords:
- C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
ms.openlocfilehash: 9f09c9ca29d247162da8f107ceb2ba47ee26bacc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143903"
---
# <a name="compiler-error-c3919"></a>Derleyici hatası C3919

' event_method ': işlevin türü ' Type ' olmalıdır

Olay erişimcisi yöntemi doğru şekilde bildirilmemiş.

Olaylar hakkında daha fazla bilgi için bkz. [Event](../../extensions/event-cpp-component-extensions.md).

Aşağıdaki örnek C3919 oluşturur:

```cpp
// C3919.cpp
// compile with: /clr /c
using namespace System;
delegate void D(String^);
ref class R {
   event D^ e {
      int add(int);   // C3919
      int remove(int);   // C3919

      void add(D^);   // OK
      void remove(D^);   // OK
   }
};
```
