---
title: "3.3.2 omp_get_wtick işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1ad08500-bcb0-40d9-a81f-f131819006c9
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 926ed8551ce032a52232a023a3f191a1b7efb233
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="332-ompgetwtick-function"></a>3.3.2 omp_get_wtick İşlevi
`omp_get_wtick` İşlevi döndürür çift duyarlıklı kayan noktalı değeri saniye sayısını eşit art arda gelen saat dilimleri arasında. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
double omp_get_wtick(void);  
```