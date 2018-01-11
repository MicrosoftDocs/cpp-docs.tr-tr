---
title: "3.2.5 omp_test_lock ve omp_test_nest_lock işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8fcdacdbb38a9bb27e35ada74aa2139be10c6797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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