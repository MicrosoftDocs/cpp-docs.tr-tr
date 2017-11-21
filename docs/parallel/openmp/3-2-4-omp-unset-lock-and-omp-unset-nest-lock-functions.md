---
title: "3.2.4 omp_unset_lock ve omp_unset_nest_lock işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c7a3aebc404205c85627820188e137713317eb7d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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