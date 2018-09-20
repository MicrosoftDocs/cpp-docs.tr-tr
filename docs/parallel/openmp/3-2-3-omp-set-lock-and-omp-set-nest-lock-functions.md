---
title: 3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 792b95baef2821bb693d9a90fc228d2b0c508e1f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420367"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock ve omp_set_nest_lock İşlevleri

Bu işlevlerin her biri, belirtilen kilit kullanılabilir ve ardından kilit ayarlar kadar işlevi yürütme iş parçacığını engeller. Basit bir kilit kilidi ise kullanılabilir. Nestable kilit kilitli olup olmadığını veya işlev yürütme iş parçacığı tarafından zaten aitse kullanılabilir. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Basit bir kilit, bağımsız değişkeni için `omp_set_lock` işlevi bir başlatılmış kilit değişkene işaret etmelidir. Kilidi sahipliğini, işlevi yürütme iş parçacığı için verilir.

Nestable kilit, bağımsız değişkeni için `omp_set_nest_lock` işlevi bir başlatılmış kilit değişkene işaret etmelidir. İç içe geçme sayısının artırılması ve iş parçacığı verilir veya kilidi sahipliğini korur.