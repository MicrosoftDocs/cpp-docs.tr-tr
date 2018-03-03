---
title: "2.6.1 master yapı | Microsoft Docs"
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
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2517e19b49f1314e7432bb265756193ea3bb8f91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="261-master-construct"></a>2.6.1 master Yapı
**Ana** yönergesi takım ana iş parçacığı tarafından yürütülen yapılandırılmış bir blok belirten bir yapı tanımlar. Söz dizimi **ana** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 Ekipteki başka bir iş parçacığı ilişkili yapılandırılmış blok yürütülmez. Zımni hiçbir engel için giriş veya çıkış master yapı ' dir.