---
title: 3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 426ac0a5ff974e486f70eed2965fdc27d5acc941
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419119"
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 omp_unset_lock ve omp_unset_nest_lock İşlevleri

Bu işlevler bir kilidin sahipliğini serbest bir yöntem sağlar. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

Bu işlevlerin her biri bağımsız değişken, işlev yürütme iş parçacığı tarafından sahip olunan bir başlatılmış kilit değişkenine işaret etmelidir. İş parçacığı, kilit sahip değilse, davranış tanımlanmamıştır.

Basit bir kilitleme `omp_unset_lock` işlevi kilidi sahipliğini işlev yürütme iş parçacığını serbest bırakır.

Bir nestable kilit için `omp_unset_nest_lock` işlev iç içe geçme sayısı ve yayınlar sonuç sayısı sıfır ise, işlev kilidi sahipliğini yürüten iş parçacığının azaltır.