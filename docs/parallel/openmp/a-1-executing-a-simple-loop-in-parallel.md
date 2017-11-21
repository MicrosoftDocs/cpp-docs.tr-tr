---
title: "Basit bir döngüsü Paralel yürütme A.1 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d2c6cfe794b9d7f50d7e12b8d2f444628ec6d79f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1   Basit Döngüyü Paralel Yürütme
Aşağıdaki örnek, bir basit döngü kullanarak paralel hale gösterilmiştir `parallel for` yönergesi ([bölüm 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) sayfasında 16). Döngü yineleme değişkeni varsayılan olarak, özel olduğundan özel yan tümcesinde açıkça belirtmek gerekli değildir.  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```