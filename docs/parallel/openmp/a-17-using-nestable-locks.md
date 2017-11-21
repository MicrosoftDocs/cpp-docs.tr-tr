---
title: Nestable kilitler kullanmaktan A.17 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8ef386ed-ddc4-4d40-80aa-cc39f0fb5e4b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3464c7d183b20d2d0eb851489c8aecf86321876f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a17---using-nestable-locks"></a>A.17   İç İçe Konulabilir Kilitleri Kullanma
Aşağıdaki örnekte (için [bölüm 3.2](../../parallel/openmp/3-2-lock-functions.md) sayfasında 41) nestable kilit hem tüm yapısı ve kendi üyelerinden biri için güncelleştirmeleri eşitlemek için nasıl kullanılabileceğini gösterir.  
  
```  
#include <omp.h>  
typedef struct {int a,b; omp_nest_lock_t lck;} pair;  
  
void incr_a(pair *p, int a)  
{  
    // Called only from incr_pair, no need to lock.  
    p->a += a;  
}  
  
void incr_b(pair *p, int b)  
{  
    // Called both from incr_pair and elsewhere,  
    // so need a nestable lock.  
  
    omp_set_nest_lock(&p->lck);  
    p->b += b;  
    omp_unset_nest_lock(&p->lck);  
}  
  
void incr_pair(pair *p, int a, int b)  
{  
    omp_set_nest_lock(&p->lck);  
    incr_a(p, a);  
    incr_b(p, b);  
    omp_unset_nest_lock(&p->lck);  
}  
  
void f(pair *p)  
{  
    extern int work1(), work2(), work3();  
    #pragma omp parallel sections  
    {  
        #pragma omp section  
            incr_pair(p, work1(), work2());  
        #pragma omp section  
            incr_b(p, work3());  
    }  
}  
```