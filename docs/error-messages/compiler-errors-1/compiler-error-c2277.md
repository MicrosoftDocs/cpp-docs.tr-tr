---
title: Derleyici Hatası C2277 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2277
dev_langs:
- C++
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 212ae84917e664116c83df3135577e00cda19446
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101955"
---
# <a name="compiler-error-c2277"></a>Derleyici Hatası C2277

'identifier': Bu üye işlevin adresi alınamaz

Bir üye işlevin adresi alınamaz.

Aşağıdaki örnek, C2277 oluşturur:

```
// C2277.cpp
class A {
public:
   A();
};
(*pctor)() = &A::A;   // C2277
```