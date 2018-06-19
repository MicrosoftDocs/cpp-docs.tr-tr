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
ms.openlocfilehash: ba24e923051eb887db2a81c1d9765d31a4ef7b24
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689720"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock ve omp_set_nest_lock İşlevleri
Bu işlevlerin her biri belirtilen kilit kullanılabilir ve kilidi ayarlar kadar işlevi yürütme iş parçacığı engeller. Basit bir kilit kilidi olduğunda kullanılabilir. Kilitli olması veya işlev yürütme iş parçacığı tarafından zaten sahip olduğu nestable kilit kullanılabilir. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Bağımsız değişkeni için basit bir kilitleme `omp_set_lock` işlevi bir başlatılmış kilit değişkenine işaret etmelidir. Kilit sahipliğini işlevi yürütme iş parçacığına verilir.  
  
 Nestable kilit, bağımsız değişkeni için `omp_set_nest_lock` işlevi bir başlatılmış kilit değişkenine işaret etmelidir. İç içe geçmiş sayısı artar ve iş parçacığı verilir veya kilidi sahipliğini korur.