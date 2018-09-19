---
title: Derleyici Hatası C3003 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3003
dev_langs:
- C++
helpviewer_keywords:
- C3003
ms.assetid: 22e74f99-bb7f-4518-ab0d-934d5d49bcc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 749199401e399a21b4b8c2c98532aa5449f2cce1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027888"
---
# <a name="compiler-error-c3003"></a>Derleyici Hatası C3003

'yönergesi': OpenMP yönergesi adına yönerge yan tümcelerinden sonra izin verilmiyor

Bir OpenMP yönergesi adı OpenMP yönergesi yan tümcesini izleyemez.

Aşağıdaki örnek, C3003 oluşturur:

```
// C3003.c
// compile with: /openmp
int main()
{
   int x, y, z;
   #pragma omp parallel shared(x, y, z) for   // C3003
}
```