---
title: "3.2.3 omp_set_lock ve omp_set_nest_lock işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5f78307023091b2e9d17ca3ff8fa2d3214c458cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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