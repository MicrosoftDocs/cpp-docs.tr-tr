---
title: 3.2.5 omp_test_lock ve omp_test_nest_lock işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5349134bf92f407d4b65df9b92e3eebe87c097c1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426152"
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 omp_test_lock ve omp_test_nest_lock İşlevleri

Bu işlevler bir kilidi ayarlama girişiminde bulunuldu ancak iş parçacığının yürütülmesini engellemez. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

Bağımsız değişken bir başlatılmış kilit değişkene işaret etmelidir. Bu işlevler, aynı şekilde kilit ayarlama girişimi `omp_set_lock` ve `omp_set_nest_lock`dışında iş parçacığının yürütülmesini engellemez.

Basit bir kilitleme `omp_test_lock` işlevi lock başarılı bir şekilde ayarlanmışsa sıfır olmayan bir değer döndürür; Aksi takdirde, sıfır döndürür.

Bir nestable kilit için `omp_test_nest_lock` işlevi lock başarılı bir şekilde ayarlanmışsa yeni iç içe geçme sayısını döndürür; Aksi takdirde, sıfır döndürür.