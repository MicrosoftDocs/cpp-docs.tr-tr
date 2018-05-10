---
title: Azaltma yan tümcesini kullanarak A.7 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e71e65bc-a25c-4f02-b507-66b52bf950a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfa7042d32ed3a82dc2cf73ab565f0db6b98d3d8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="a7---using-the-reduction-clause"></a>A.7   reduction Yan Tümcesini Kullanma
Aşağıdaki örnek, azaltma yan tümcesi gösterir ([bölüm 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) sayfasında 28):  
  
```  
#pragma omp parallel for private(i) shared(x, y, n) \  
                         reduction(+: a, b)  
    for (i=0; i<n; i++) {  
        a = a + x[i];  
        b = b + y[i];  
    }  
```