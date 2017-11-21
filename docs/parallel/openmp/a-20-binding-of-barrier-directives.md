---
title: "Barrier yönergesi A.20 bağlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8d88c431753d918c05866324dd6436a091d6057a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a20---binding-of-barrier-directives"></a>A.20   barrier Yönergelerini Bağlama
Yönerge bağlama kuralları çağrısı için bir **engel** en yakın kapsayan bağlamak için yönergesi `parallel` yönergesi. Yönerge bağlama hakkında daha fazla bilgi için bkz: [bölüm 2.8](../../parallel/openmp/2-8-directive-binding.md) sayfasında 32.  
  
 Aşağıdaki örnekte, çağrısından *ana* için *sub2* uyumlu olmadığından **engel** (içinde *sub3*) paralel bölgesine bağlar içinde *sub2*. Çağrısından *ana* için *Abon1* uyumlu olmadığından **engel** alt yordama paralel bölgede bağlar *sub2*.  Çağrısından *ana* için *sub3* uyumlu olmadığından **engel** paralel bir bölgeye bağlamaz ve yok sayılır. Ayrıca **engel** kapsayan paralel bölge içindeki iş parçacığı ve oluşturulan tüm iş parçacıklarının takım eşitler *Abon1*.  
  
```  
int main()  
{  
    sub1(2);  
    sub2(2);  
    sub3(2);  
}  
  
void sub1(int n)  
{  
    int i;  
    #pragma omp parallel private(i) shared(n)  
    {  
        #pragma omp for  
        for (i=0; i<n; i++)  
            sub2(i);  
    }  
}  
  
void sub2(int k)  
{  
     #pragma omp parallel shared(k)  
     sub3(k);  
}  
  
void sub3(int n)  
{  
    work(n);  
    #pragma omp barrier  
    work(n);  
}  
```