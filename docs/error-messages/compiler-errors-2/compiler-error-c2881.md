---
title: Derleyici Hatası C2881 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2881
dev_langs:
- C++
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7f74a4336af3b8ce8bfe0fa87f7f1a84746ff11
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052497"
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