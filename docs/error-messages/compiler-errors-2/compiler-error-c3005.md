---
title: Derleyici Hatası C3005 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3005
dev_langs:
- C++
helpviewer_keywords:
- C3005
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d94d32def0a2fc5ddc3b992d4098a75f925499e7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089343"
---
# <a name="compiler-error-c3005"></a>Derleyici Hatası C3005

'error_text': OpenMP 'yönergesi' yönergesinde karşılaştı beklenmeyen belirteç

Bir OpenMP yönergesinde ill oluşturulmuş.

Aşağıdaki örneğe C3005 oluşturur:

```
// C3005.c
// compile with: /openmp
int main()
{
   #pragma omp parallel + for   // C3005
}
```

Pragma ile aynı satırda açık bir ayraç koyarsanız C3005 da meydana gelebilir.

```
// C3005b.c
// compile with: /openmp
int main() {
   #pragma omp parallel {   // C3005 put open brace on next line
   lbl2:;
   }
   goto lbl2;
}
```