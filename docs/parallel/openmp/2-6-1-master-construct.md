---
title: "2.6.1 master yapı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bff566967749068f9792a98dc3cf2151e4df3d9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="261-master-construct"></a>2.6.1 master Yapı
**Ana** yönergesi takım ana iş parçacığı tarafından yürütülen yapılandırılmış bir blok belirten bir yapı tanımlar. Söz dizimi **ana** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 Ekipteki başka bir iş parçacığı ilişkili yapılandırılmış blok yürütülmez. Zımni hiçbir engel için giriş veya çıkış master yapı ' dir.