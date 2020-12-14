---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3001'
title: Derleyici hatası C3001
ms.date: 11/04/2016
f1_keywords:
- C3001
helpviewer_keywords:
- C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
ms.openlocfilehash: cf8acec3fb95553787e14968b9ce3e608da83916
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253604"
---
# <a name="compiler-error-c3001"></a>Derleyici hatası C3001

' error_text ': bir OpenMP yönergesi adı bekleniyor

`omp`Pragma 'ın arkasından bir yönerge gelmelidir.

Aşağıdaki örnek C3001 oluşturur:

```c
// C3001.c
// compile with: /openmp
int main()
{
   #pragma omp   // C3001 missing token
}
```
