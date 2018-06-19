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
ms.openlocfilehash: f480a75efff737356c1477593e182537ae73a8c8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690227"
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 omp_unset_lock ve omp_unset_nest_lock İşlevleri
Bu işlevlerin bir kilit sahipliğini yayınlama yöntemdir. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Bu işlevlerin her biri bağımsız değişkeni işlevi yürütme iş parçacığı tarafından sahip olunan bir başlatılmış kilit değişkeni işaret etmelidir. İş parçacığı, kilit sahibi değil ise tanımlanmamış bir davranıştır.  
  
 Basit bir kilitleme `omp_unset_lock` işlevi işlevi kilidi sahipliğini yürütme iş parçacığı serbest bırakır.  
  
 Nestable kilitleme `omp_unset_nest_lock` azaltır iç içe geçmiş sayısı ve sürümler sonuç sayısı sıfırsa işlevi kilidi sahipliğini yürütme iş parçacığı işlev.