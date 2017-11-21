---
title: "Paralel bölümleri belirtme A.8 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d369c2e3a0d326ab4c835a30681f3dbe50f789f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a8---specifying-parallel-sections"></a>A.8   Paralel Bölümleri Belirtme
Aşağıdaki örnekte, (için [bölüm 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) sayfasında 14) işlevleri *xaxis*, *yaxis*, ve *zaxis* aynı anda çalıştırılabilecek. İlk `section` yönergesi isteğe bağlıdır.  Unutmayın tüm `section` yönergeleri gereksinim içinde sözcük kapsamını görünmesi `parallel sections` oluşturun.  
  
```  
#pragma omp parallel sections  
{  
    #pragma omp section  
        xaxis();  
    #pragma omp section  
        yaxis();  
    #pragma omp section  
        zaxis();  
}  
```