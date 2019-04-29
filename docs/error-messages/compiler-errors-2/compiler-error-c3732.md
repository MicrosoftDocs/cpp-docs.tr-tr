---
title: Derleyici Hatası C3732
ms.date: 11/04/2016
f1_keywords:
- C3732
helpviewer_keywords:
- C3732
ms.assetid: 2d55a7e1-9c39-4379-a093-2f7beb27e2ca
ms.openlocfilehash: c71cca3643f6337060de6e4bb56ac64d8f0d6e4e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327996"
---
# <a name="compiler-error-c3732"></a>Derleyici Hatası C3732

'interface': COM olayları başlatan bir özel arabirim IDispatch'ten devralamaz

COM olayları destekleyen bir arabirim devralamaz `IDispatch`. Daha fazla bilgi için [com'da olay işleme](../../cpp/event-handling-in-com.md).

Aşağıdaki hata C3732 oluşturur:

```
// C3732.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="test")];

// to resolve this C3732, use dual instead of object
// or inherit from IUnknown
[ object ]
__interface I : IDispatch
{
};

[ event_source(com), coclass ]
struct A
{
   __event __interface I;   // C3732
};

int main()
{
}
```