---
title: Derleyici Hatası C2437 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2437
dev_langs:
- C++
helpviewer_keywords:
- C2437
ms.assetid: 2d2b3c6c-856a-4b27-ae10-64813b3e5483
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 893c037e7efd363b8d867ef181db5a8df001d3c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047947"
---
# <a name="compiler-error-c2437"></a>Derleyici Hatası C2437

'identifier': zaten başlatıldı

Bir nesne yalnızca bir kez başlatılabilir.

Aşağıdaki örnek, C2437 oluşturur:

```
// C2437.cpp
// compile with: /c
class A {
public:
   A(int i) {}
};

class B : A {
   B() : A(1), A(2) {}   // C2437
   B() : A(1) {}   // OK
};
```