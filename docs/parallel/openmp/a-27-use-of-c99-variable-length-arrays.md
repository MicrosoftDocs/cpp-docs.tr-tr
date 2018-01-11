---
title: "C99 değişken uzunlukta diziler A.27 kullanımını | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4bf3136c4fb4c5c14b728acbc61f3fbf66ce08bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="a27---use-of-c99-variable-length-arrays"></a>A.27   C99 Değişken Uzunluklu Dizilerin Kullanımı
Aşağıdaki örnek, içinde nasıl C99 değişken uzunlukta diziler (VLAs) kullanılacağını gösterir. bir `firstprivate` yönergesi ([bölüm 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) sayfasında 26).  
  
> [!NOTE]
>  Değişken uzunlukta diziler Visual C++'da şu anda desteklenmiyor.  
  
```  
void f(int m, int C[m][m])  
{  
    double v1[m];  
    ...  
    #pragma omp parallel firstprivate(C, v1)  
    ...  
}  
```