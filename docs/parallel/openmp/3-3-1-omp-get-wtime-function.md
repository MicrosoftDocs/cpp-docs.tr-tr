---
title: 3.3.1 omp_get_wtime işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d71296d23df72464ed730713566c95e2403760a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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