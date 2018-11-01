---
title: A.19   İş Paylaşım Yönergelerinin Yanlış İş İçe Konulmasını Gösteren Örnekler
ms.date: 11/04/2016
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
ms.openlocfilehash: 5be09dd3282260dabc2ef30dafc249539d6a6418
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501952"
---
# <a name="a19---examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19   İş Paylaşım Yönergelerinin Yanlış İş İçe Konulmasını Gösteren Örnekler

Bu bölümdeki örnekler, yönerge iç içe geçme kuralları gösterir. Yönerge iç içe koyma hakkında daha fazla bilgi için bkz. [bölümü 2.9](../../parallel/openmp/2-9-directive-nesting.md) sayfasında 33.

Aşağıdaki örnek uyumsuz olduğundan iç ve dış `for` yönergeleri iç içe ve aynı bağlama `parallel` yönergesi:

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

Önceki örnekte bulunan aşağıdaki dinamik olarak iç içe geçmiş sürüm da uyumsuzdur:

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

Aşağıdaki örnek, uyumsuz, çünkü `for` ve `single` yönergeleri iç içe ve bunların aynı paralel bölgeye bağlayın:

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

Aşağıdaki örnek uyumsuz olduğundan bir `barrier` yönergesi içinde bir `for` kilitlenmeyle neden olabilir:

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

Aşağıdaki örnek, uyumsuz, çünkü `barrier` aynı anda yalnızca tek bir iş parçacığı, kritik bölüm girebilirsiniz Bunun nedeni, kilitlenmeyle sonuçları:

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

Aşağıdaki örnek, uyumsuz, çünkü `barrier` yalnızca bir iş parçacığı çalıştırır. Bunun nedeni, kilitlenmeyle sonuçları `single` bölümü:

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