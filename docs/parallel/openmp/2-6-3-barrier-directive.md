---
title: 2.6.3 barrier yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68df92207feb45a77055098cdb1227a68b04bcab
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689798"
---
# <a name="263-barrier-directive"></a>2.6.3 barrier Yönergesi
**Engel** yönergesi takım tüm iş parçacıklarının eşitler. Tüm diğer bu noktası ulaştınız karşılaştığında, her iş parçacığı ekipteki bekler. Söz dizimi **engel** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp barrier new-line  
```  
  
 Tüm iş parçacıklarının ekipteki engel karşılaşmış sonra Ekipteki her bir iş parçacığı paralel barrier yönergesi sonra ifadeler çalıştırmasını başlar. Çünkü unutmayın **engel** yönergesi sözdizimi bir parçası olarak C dili bildirimi sahip değil, bir program içindeki yerleşimi bazı kısıtlamalar vardır. Bkz: [ek C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) resmi dilbilgisi için. Aşağıdaki örnek, bu kısıtlamaları gösterir.  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```