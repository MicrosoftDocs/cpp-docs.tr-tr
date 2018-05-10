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
ms.openlocfilehash: 5023f0b089d76e92be886f4917905f57dda7a018
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 omp_test_lock ve omp_test_nest_lock İşlevleri
Bu işlevlerin bir kilit ayarlama girişiminde bulunuldu, ancak yürütme iş parçacığının engellemez. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Bağımsız değişkeni bir başlatılmış kilit değişkenine işaret etmelidir. Bu işlevler aynı şekilde kilit ayarlama girişimi `omp_set_lock` ve `omp_set_nest_lock`, yürütme iş parçacığının engellemez dışında.  
  
 Basit bir kilitleme `omp_test_lock` işlevi kilidi başarılı bir şekilde ayarlanmışsa, sıfır olmayan bir değer döndürür; Aksi halde, sıfır döndürür.  
  
 Nestable kilitleme `omp_test_nest_lock` işlevi kilidi başarılı bir şekilde ayarlanmışsa, yeni iç içe geçmiş sayısını döndürür; Aksi halde, sıfır döndürür.