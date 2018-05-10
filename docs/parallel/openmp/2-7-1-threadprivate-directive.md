---
title: 2.7.1 threadprivate yönergesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9912ccbfa6f5773ec1e523245f75e675bb82244
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="271-threadprivate-directive"></a>2.7.1 threadprivate Yönergesi
`threadprivate` Yönergesi yapar adlandırılmış dosya kapsamı, ad alanı kapsamı veya statik blok kapsamı değişkenleri belirtilen *değişken listesi* özel bir iş parçacığı için. *değişken listesi* tamamlanmamış bir türleri olmadığı değişkenleri virgülle ayrılmış listesi. Söz dizimi `threadprivate` yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp threadprivate(variable-list) new-line  
```  
  
 Her kopyası bir `threadprivate` değişkeni başlatılır yüklenirse, bu kopyayı ilk referansı önce programında ve normal şekilde belirtilmeyen bir noktada (yani, ana kopyayı seri bir programın yürütülmesini içinde başlatılması gibi). Bir nesne açık bir başlatıcı başvuruda bulunulan gerçekleştiriyorsanız bir `threadprivate` değişkeni ve değeri nesnenin değiştiren değişkeni bir kopyasını ilk referansı önce ve sonra belirtilmeyen bir davranıştır.  
  
 Herhangi bir özel değişken ile başka bir iş parçacığının kopyasını bir iş parçacığı başvurmaması gibi bir `threadprivate` nesnesi. Seri bölgeler ve ana bölge programının sırasında başvuruları ana iş parçacığının nesne kopyasına olacaktır.  
  
 İlk paralel bölge yürütüldükten sonra verileri `threadprivate` nesneleri, yalnızca dinamik mekanizması iş parçacıkları, devre dışı bırakıldı ve iş parçacığı sayısı için tüm paralel bölgeler değişmeden kalır, devam etmek için garanti.  
  
 Kısıtlamaları `threadprivate` yönergesi aşağıdaki gibidir:  
  
-   A `threadprivate` yönergesi dosya kapsamı veya ad alanı kapsam değişkenleri için herhangi bir tanım veya bildirimi dışında görünmesi gerekir ve tüm başvuruları herhangi bir değişken kendi listesinde sözcüksel olarak gelmelidir.  
  
-   Her bir değişken *değişken listesi* , bir `threadprivate` yönergesi dosya veya ad alanı kapsamında bir değişken bildirimi sözcüksel olarak yönergesi önündeki dosya veya ad alanı kapsamda başvurmalıdır.  
  
-   A `threadprivate` yönergesi statik blok kapsamı değişkenler için değişkenin kapsamını ve iç içe geçmiş kapsamdaki değil görünmelidir. Yönergesi sözcüksel olarak kendi listesinde değişkenlerden herhangi birini yapılan tüm başvuruları gelmelidir.  
  
-   Her bir değişken *değişken listesi* , bir `threadprivate` yönergesi blok kapsamında bir değişken bildirimi sözcüksel olarak yönergesi önündeki aynı kapsamda başvurmalıdır. Değişken bildirimi statik depolama sınıfı tanımlayıcısı kullanmanız gerekir.  
  
-   Bir değişken belirtilmişse bir `threadprivate` yönerge bir çeviri birimi de belirtilmelidir bir `threadprivate` onu bildirilen her çeviri biriminde yönergesi.  
  
-   A `threadprivate` değişkeni gerekir görünmüyor tüm yan tümcesinde `copyin`, `copyprivate`, `schedule`, `num_threads`, veya **varsa** yan tümcesi.  
  
-   Adresini bir `threadprivate` değişken bir adres sabiti değil.  
  
-   A `threadprivate` değişkeni tamamlanmamış bir tür veya bir başvuru türü değil olmalıdır.  
  
-   A `threadprivate` değişkeni POD olmayan sınıf türü ile açık bir başlatıcı bildirilirse erişilebilir, anlaşılır kopya Oluşturucu olması gerekir.  
  
 Aşağıdaki örnek, nasıl bir başlatıcı görünür bir değişken değiştirme belirtilmeyen davranışı neden olabilir ve aynı zamanda bir yardımcı nesnesini ve bir kopya Oluşturucu kullanarak bu sorundan kaçınmak nasıl gösterilmektedir.  
  
```  
int x = 1;  
T a(x);  
const T b_aux(x); /* Capture value of x = 1 */  
T b(b_aux);  
#pragma omp threadprivate(a, b)  
  
void f(int n) {  
   x++;  
   #pragma omp parallel for  
   /* In each thread:  
   * Object a is constructed from x (with value 1 or 2?)  
   * Object b is copy-constructed from b_aux  
   */  
   for (int i=0; i<n; i++) {  
      g(a, b); /* Value of a is unspecified. */  
   }  
}  
```  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   Dinamik zincirlerini görmek [bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.  
  
-   `OMP_DYNAMIC` ortam değişkeni, bkz: [bölüm 4.3](../../parallel/openmp/4-3-omp-dynamic.md) sayfasında 49.