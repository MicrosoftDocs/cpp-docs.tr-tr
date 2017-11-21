---
title: "3.3.1 omp_get_wtime işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c5f48f2cbc5cb77d20884632881b779986dac6d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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