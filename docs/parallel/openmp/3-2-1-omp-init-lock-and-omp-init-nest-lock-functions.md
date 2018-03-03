---
title: "3.2.1 omp_init_lock ve omp_init_nest_lock işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3802822465d6527e4c98a0be6a8c274d767b0f52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock ve omp_init_nest_lock İşlevleri
Bu işlevlerin bir kilit başlatma tek yöntemdir. Her işlevi parametresi ile ilişkili kilit başlatır *kilit* sonraki çağrılar kullanmak için. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 İlk durumu kilitli değil (diğer bir deyişle, hiçbir iş parçacığı kilit sahibi). Nestable kilidi ilk iç içe geçmiş sayısı sıfır olur. Bu yordamlar zaten başlatılmış olan bir kilit değişkeniyle birini çağırmak için uyumsuz.