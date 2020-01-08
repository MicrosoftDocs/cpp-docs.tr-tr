---
title: Derleyici hatası C3001
ms.date: 11/04/2016
f1_keywords:
- C3001
helpviewer_keywords:
- C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
ms.openlocfilehash: 737754eb314b577ac73e91a5aab1ad31773fc5f3
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302217"
---
# <a name="compiler-error-c3001"></a>Derleyici hatası C3001

' error_text ': bir OpenMP yönergesi adı bekleniyor

`omp` pragma 'ın arkasından bir yönerge gelmelidir.

Aşağıdaki örnek C3001 oluşturur:

```c
// C3001.c
// compile with: /openmp
int main()
{
   #pragma omp   // C3001 missing token
}
```
