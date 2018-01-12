---
title: "2.6.3 barrier yönergesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9c64787d9c6cc2dd0809f75f8f9db9819174d0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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