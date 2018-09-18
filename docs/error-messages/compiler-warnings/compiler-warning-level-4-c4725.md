---
title: Derleyici Uyarısı (düzey 4) C4725 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4725
dev_langs:
- C++
helpviewer_keywords:
- C4725
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef56a4e580e8c62db7f8c8c818a84acec0214672
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048272"
---
# <a name="compiler-warning-level-4-c4725"></a>Derleyici Uyarısı (düzey 4) C4725

yönerge bazı Pentium'larda yanlış olabilir.

Kodunuz doğru sonuçlar üzerinde bazı Pentium mikro vermeyebilir bir satır içi derleme yönergesinin içerir.

Aşağıdaki örnek, C4725 oluşturur:

```
// C4725.cpp
// compile with: /W4
// processor: x86
double m32fp = 2.0003e-17;

void f() {
   __asm
   {
      FDIV m32fp   // C4725
   }
}

int main() {
}
```