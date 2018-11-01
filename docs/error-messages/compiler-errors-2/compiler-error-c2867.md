---
title: Derleyici Hatası C2867
ms.date: 11/04/2016
f1_keywords:
- C2867
helpviewer_keywords:
- C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
ms.openlocfilehash: 3c79fec9f52ea9451cea456dcc062af9bcbe9b3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602494"
---
# <a name="compiler-error-c2867"></a>Derleyici Hatası C2867

'identifier': bir ad alanı değil

A `using` yönergesi, bir ad alanı dışında bir şey uygulanır.

Aşağıdaki örnek, C2867 oluşturur:

```
// C2867.cpp
// compile with: /c
namespace N {
   class X {};
}
using namespace N::X;   // C2867
```