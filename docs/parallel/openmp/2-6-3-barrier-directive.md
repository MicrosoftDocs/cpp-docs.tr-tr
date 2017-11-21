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
ms.openlocfilehash: adc480a82668da3c3ad7fdb88a701b3fa80ae9e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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