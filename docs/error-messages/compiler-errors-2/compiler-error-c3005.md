---
title: Derleyici Hatası C3005
ms.date: 11/04/2016
f1_keywords:
- C3005
helpviewer_keywords:
- C3005
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
ms.openlocfilehash: 1303fd667c92af6fd8d0476da9468b4c7d090e6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350747"
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