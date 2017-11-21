---
title: "Özel yan tümcesinin A.24 örnek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6f0690f06ac51288605ae4bdd7f12b977f77cf58
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a24---example-of-the-private-clause"></a>A.24   private Yan Tümcesi Örneği
`private` Yan tümcesi ([bölüm 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) sayfasında 25) paralel bölgesi yalnızca etkisi bölgenin dinamik kapsam için değil, bölge sözcük kapsamını için kullanılıyor.  Bu nedenle, değişkenin herhangi kullandığı aşağıdaki örnekte *bir* içinde `for` yordamı döngüde *f* özel bir kopyası anlamına gelir *bir*, çalışırken bir kullanımı yordamı *g* genel başvuruyor *bir*.  
  
```  
int a;  
  
void f(int n)   
{  
    a = 0;  
  
    #pragma omp parallel for private(a)  
    for (int i=1; i<n; i++)   
    {  
        a = i;  
        g(i, n);  
        d(a);     // Private copy of "a"  
        ...  
    }  
    ...  
  
void g(int k, int n)   
{  
    h(k,a); // The global "a", not the private "a" in f  
}  
```