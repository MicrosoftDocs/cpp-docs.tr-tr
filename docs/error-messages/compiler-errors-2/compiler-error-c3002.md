---
title: Derleyici Hatası C3002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3002
dev_langs:
- C++
helpviewer_keywords:
- C3002
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc346c349ba57906e1645b7e3535ae6b11bd36d7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086310"
---
# <a name="compiler-error-c3002"></a>Derleyici Hatası C3002

'name1 name2': birden fazla OpenMP yönergesi adı

Birden çok yönerge adlarına izin verilmemektedir.

Aşağıdaki örnek, C3002 oluşturur:

```
// C3002.c
// compile with: /openmp
int main()
{
   #pragma omp parallel single   // C3002
}
```