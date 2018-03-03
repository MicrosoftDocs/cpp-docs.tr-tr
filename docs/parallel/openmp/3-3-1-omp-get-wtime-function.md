---
title: "3.3.1 omp_get_wtime işlevi | Microsoft Docs"
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
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f89a71d1b91a27dfdd0abf13be4a5f0e30b3fd9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime İşlevi
`omp_get_wtime` İşlevi döndürür çift duyarlıklı kayan noktalı değeri geçen duvar saati süresi eşit bazı "saat" geçmişte bu yana saniye cinsinden.  Gerçek "süresi geçmiş" isteğe bağlıdır, ancak uygulama programı yürütme sırasında değiştirilmemesi sağlanır. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 İşlev aşağıdaki örnekte gösterildiği gibi geçen kez ölçmek için kullanılan, beklenen:  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 Döndürülen kez, bir uygulamada katılan tüm iş parçacıkları arasında genel olarak tutarlı olması gerekmez tasarlanmıştır tarafından "iş parçacığı başına kez" olur.