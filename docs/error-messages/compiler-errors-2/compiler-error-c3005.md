---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3005'
title: Derleyici hatası C3005
ms.date: 11/04/2016
f1_keywords:
- C3005
helpviewer_keywords:
- C3005
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
ms.openlocfilehash: df9e0c94aa0ba47e1c2f63858419c15881f9bd74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272428"
---
# <a name="compiler-error-c3005"></a>Derleyici hatası C3005

' error_text ': OpenMP ' Directive ' yönergesinde beklenmeyen belirteçle karşılaşıldı

Bir OpenMP yönergesi hatalı biçimlendirilmiş.

Aşağıdaki örnek C3005 oluşturur:

```c
// C3005.c
// compile with: /openmp
int main()
{
   #pragma omp parallel + for   // C3005
}
```

C3005, pragma ile aynı satıra bir açık küme ayracı yerleştirirseniz da oluşabilir.

```c
// C3005b.c
// compile with: /openmp
int main() {
   #pragma omp parallel {   // C3005 put open brace on next line
   lbl2:;
   }
   goto lbl2;
}
```
