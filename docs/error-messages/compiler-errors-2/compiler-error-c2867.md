---
title: Derleyici hatası C2867
ms.date: 11/04/2016
f1_keywords:
- C2867
helpviewer_keywords:
- C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
ms.openlocfilehash: 42b931d208000cc35e65c7bff9c20901cef24713
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755063"
---
# <a name="compiler-error-c2867"></a>Derleyici hatası C2867

' Identifier ': bir ad alanı değil

Bir `using` yönergesi, ad alanı dışında bir şeye uygulanır.

Aşağıdaki örnek C2867 oluşturur:

```cpp
// C2867.cpp
// compile with: /c
namespace N {
   class X {};
}
using namespace N::X;   // C2867
```
