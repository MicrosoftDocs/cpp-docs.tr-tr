---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3910'
title: Derleyici hatası C3910
ms.date: 11/04/2016
f1_keywords:
- C3910
helpviewer_keywords:
- C3910
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
ms.openlocfilehash: 802aac0d27e230920a906b96afc78100296c75de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144150"
---
# <a name="compiler-error-c3910"></a>Derleyici hatası C3910

' Event ': ' Method ' üyesini tanımlamanız gerekir

Bir olay tanımlandı, ancak belirtilen gerekli erişimci metodunu içermiyordu.

Daha fazla bilgi için bkz. [olay](../../extensions/event-cpp-component-extensions.md).

Aşağıdaki örnek C3910 oluşturur:

```cpp
// C3910.cpp
// compile with: /clr /c
delegate void H();
ref class X {
   event H^ E {
      // uncomment the following lines
      // void add(H^) {}
      // void remove( H^ h ) {}
      // void raise( ) {}
   };   // C3910

   event H^ E2; // OK data member
};
```
