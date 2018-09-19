---
title: Derleyici Hatası C3009 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3009
dev_langs:
- C++
helpviewer_keywords:
- C3009
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dd26f94ecb97e578073f2c3991ed13ebdc592fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035247"
---
# <a name="compiler-error-c3009"></a>Derleyici Hatası C3009

'etiketi': OpenMP yapısal bloğunun izin içine atlamaya

Kod içine veya bir OpenMP bloğunun dışına atlama olamaz.

Aşağıdaki örnek, C3009 oluşturur:

```
// C3009.c
// compile with: /openmp
int main() {
   #pragma omp parallel
   {
   lbl2:;
   }
   goto lbl2;   // C3009
}
```