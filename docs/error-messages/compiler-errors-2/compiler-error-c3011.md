---
title: Derleyici Hatası C3011 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3011
dev_langs:
- C++
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f25e3f9479b2555badbd079c3e2d939e91acbba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024417"
---
# <a name="compiler-error-c3011"></a>Derleyici Hatası C3011

Satır içi derleme doğrudan bir paralel bölgenin içinde izin verilmiyor

Bir `omp` paralel bölgenin, satır içi derleme yönergeleri içeremez.

Aşağıdaki örnek, C3011 oluşturur:

```
// C3011.cpp
// compile with: /openmp
// processor: /x86
int main() {
   int   n = 0;

   #pragma omp parallel
   {
      _asm mov eax, n   // Delete this line to resolve this error.
   }   // C3011
}
```