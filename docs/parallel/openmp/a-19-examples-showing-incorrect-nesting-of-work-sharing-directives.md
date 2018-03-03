---
title: "Yanlış iç içe geçmiş iş paylaşım yönergeleri gösteren A.19 örnekler | Microsoft Docs"
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
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8a3f8a4e1ca62a77c16dafedd0921ca842d7a048
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="a19---examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19   İş Paylaşım Yönergelerinin Yanlış İş İçe Konulmasını Gösteren Örnekler
Bu bölümdeki örnekleri yönerge iç içe geçmiş kuralları gösterilmektedir. Yönerge iç içe geçirme hakkında daha fazla bilgi için bkz: [bölüm 2.9](../../parallel/openmp/2-9-directive-nesting.md) sayfasında 33.  
  
 Aşağıdaki örnek uyumsuz olduğundan iç ve dış `for` yönergeleri yerleştirilir ve bağlamak için aynı `parallel` yönergesi:  
  
```  
void wrong1(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
      int i, j;  
      #pragma omp for  
      for (i=0; i<n; i++) {  
          #pragma omp for  
              for (j=0; j<n; j++)  
                 work(i, j);  
     }  
   }  
}  
```  
  
 Aşağıdaki dinamik olarak iç içe geçmiş önceki örnekte de uyumsuz sürümüdür:  
  
```  
void wrong2(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++)  
        work1(i, n);  
  }  
}  
  
void work1(int i, int n)  
{  
  int j;  
  #pragma omp for  
    for (j=0; j<n; j++)  
      work2(i, j);  
}  
```  
  
 Aşağıdaki örnek uyumsuz olduğundan `for` ve `single` yönergeleri iç içe geçmiş ve aynı paralel bölgeye Bağla:  
  
```  
void wrong3(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        #pragma omp single  
          work(i);  
      }  
  }  
}  
```  
  
 Aşağıdaki örnek uyumsuz olduğundan bir `barrier` içinde yönerge bir `for` kilitlenmeyle neden olabilir:  
  
```  
void wrong4(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        work1(i);  
        #pragma omp barrier  
        work2(i);  
      }  
  }  
}  
```  
  
 Aşağıdaki örnek uyumsuz olduğundan `barrier` sonuçlanır kilitlenmeyle kritik bölüm aynı anda yalnızca bir iş parçacığı girebilirsiniz due için nedeni:  
  
```  
void wrong5()  
{  
  #pragma omp parallel  
  {  
    #pragma omp critical  
    {  
       work1();  
       #pragma omp barrier  
       work2();  
    }  
  }  
}  
```  
  
 Aşağıdaki örnek uyumsuz olduğundan `barrier` sonuçlanır kilitlenmeyle yalnızca bir iş parçacığı yürütür due için nedeni `single` bölümü:  
  
```  
void wrong6()  
{  
  #pragma omp parallel  
  {  
    setup();  
    #pragma omp single  
    {  
      work1();  
      #pragma omp barrier  
      work2();  
    }  
    finish();  
  }  
}  
```