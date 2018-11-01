---
title: Derleyici Hatası C2881
ms.date: 11/04/2016
f1_keywords:
- C2881
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
ms.openlocfilehash: 82a4fbe94bc7250244d57f549e52037d6a54c784
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610528"
---
# <a name="compiler-error-c2881"></a>Derleyici Hatası C2881

'namespace1': 'namespace2' için bir diğer ad olarak zaten kullanılıyor

Aynı adlı iki ad alanı için bir diğer ad olarak kullanamazsınız.

Aşağıdaki örnek, C2881 oluşturur:

```
// C2881.cpp
// compile with: /c
namespace A {
   int k;
}

namespace B {
   int i;
}

namespace C = A;
namespace C = B;   // C2881 C is already an alias for A
```