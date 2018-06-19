---
title: 2.3 parallel yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 190eacdf-2c16-4c06-8cb7-ac60eb211425
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 121454f6a98901a6c1b695a80c6ec774737b95e0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692756"
---
# <a name="23-parallel-construct"></a>2.3 parallel Yapı
Aşağıdaki komut paralel birden çok iş parçacığı tarafından yürütülür program bölgedir paralel bir bölge tanımlar. Bu paralel yürütme başlayan temel bir yapıdır.  
  
```  
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block  
```  
  
 *Yan tümcesi* aşağıdakilerden biri:  
  
 **varsa (** *skaler ifade* **)**  
  
 **Özel (** *değişken listesi* **)**  
  
 **firstprivate (** *değişken listesi* **)**  
  
 **Varsayılan (paylaşılan &#124; yok)**  
  
 **Paylaşılan (** *değişken listesi* **)**  
  
 **copyin (** *değişken listesi* **)**  
  
 **azaltma (** *işleci* **:***değişken listesi* **)**  
  
 **num_threads (** *tamsayı ifade* **)**  
  
 Bir iş parçacığı paralel yapı karşılaştığında, aşağıdaki durumlardan biri doğruysa bir takım iş parçacığı oluşturulur:  
  
-   Hayır **varsa** yan tümcesi varsa.  
  
-   **Varsa** ifadeyi hesaplar için sıfır olmayan bir değer.  
  
 Bu iş parçacığı 0, iş parçacığı sayısı ile takım ana iş parçacığı haline gelir ve ekipteki ana iş parçacığı dahil olmak üzere tüm iş parçacıklarının bölge paralel olarak yürütün. Varsa değerini **varsa** ifade sıfır, bölge sıralanır.  
  
 İstenen iş parçacığı sayısını belirlemek için aşağıdaki kuralları sırada kabul edilir. İlk Kural koşulu karşılanır uygulanacak:  
  
1.  Varsa **num_threads** yan tümcesi varsa, ardından istenen iş parçacığı sayısı tamsayı ifade değeridir.  
  
2.  Varsa **omp_set_num_threads** kitaplığı işlevini çağırdı sonra en son çalıştırılan çağrısında bağımsız değişkeninin değeri istenen iş parçacığı sayısıdır.  
  
3.  Varsa ortam değişkeni **OMP_NUM_THREADS** tanımlanır, sonra da bu ortam değişkeninin değeri istenen iş parçacığı sayısıdır.  
  
4.  Yukarıdaki yöntemlerden hiçbiri kullanıldıysa, uygulama tanımlı istenen iş parçacığı sayısı.  
  
 Varsa **num_threads** yan tümcesi varsa sonra tarafından istenen iş parçacığı sayısını yerini **omp_set_num_threads** kitaplığı işlevi veya **OMP_NUM_THREADS** ortam değişkeni paralel bölge için yalnızca bu uygulanır. Sonraki paralel bölgeler bundan etkilenmez.  
  
 Paralel bölge yürütme iş parçacığı sayısı ayrıca iş parçacığı sayısını dinamik olarak ayarlamayı desteklemediğini etkin üzerine bağlıdır. Dinamik ayarlama devre dışıysa, istenen iş parçacığı sayısını paralel bölge yürütülür. Dinamik ayarı etkinse, ardından istenen iş parçacığı paralel bölge yürütür iş parçacığı sayısı sayısıdır.  
  
 Paralel bir bölge iş parçacığı sayısını dinamik olarak ayarlamayı devre dışı bırakılır ve paralel bölge için istenen iş parçacığı sayısı çalışma zamanı sistem sağlayabilir sayıyı aşıyor karşılaşılırsa, programın davranışını olduğu uygulama tanımlı. Uygulaması, örneğin, program yürütme kesme ya da paralel bölge seri.  
  
 **Omp_set_dynamic** kitaplığı işlevi ve **omp_dynamıc** ortam değişkeni, etkinleştirmek ve iş parçacığı sayısını dinamik olarak ayarlamayı devre dışı bırakmak için kullanılabilir.  
  
 Uygulama tanımlı gerçekte iş parçacıklarının herhangi bir anda barındıran fiziksel işlemcilerin sayısı. Oluşturduktan sonra iş parçacıklarının ekipteki paralel bu bölge boyunca sabit kalır. Kullanıcı tarafından açıkça ya da otomatik olarak bir paralel bölge başka bir çalışma zamanı sistemi tarafından değiştirilebilir.  
  
 Paralel bölge dinamik kapsam içinde yer alan deyimleri her iş parçacığı tarafından yürütülür ve her iş parçacığı diğer iş parçacıklarından farklı bir yol deyimlerinin yürütebilir. Paralel bir bölge sözcük kapsamı dışında karşılaştı yönergeleri yalnız bırakılmış yönergeleri adlandırılır.  
  
 Paralel bir bölge sonunda kapsanan bir engel yoktur. Yalnızca ana iş parçacığı ekibi paralel bir bölge sonunda yürütme devam eder.  
  
 Bir iş parçacığı paralel bir bölge yürütülürken bir ekip, başka bir paralel yapı karşılaşırsa, yeni bir ekip oluşturur ve bu yeni takım ana olur. İç içe geçmiş paralel bölgeleri varsayılan olarak serileştirilir. Sonuç olarak, varsayılan olarak, bir iş parçacığı oluşan bir ekibin bir iç içe geçmiş paralel bölge yürütülür. Varsayılan davranış, çalışma zamanı kitaplığı işlevi kullanarak değiştirilebilir **omp_set_nested** veya ortam değişkeni **OMP_NESTED**. Ancak, iç içe geçmiş bir paralel bölge yürütme iş parçacığı bir takım uygulama tanımlı sayısıdır.  
  
 Kısıtlamaları **paralel** yönergesi aşağıdaki gibidir:  
  
-   En çok bir **varsa** yan tümcesi üzerinde yönergesi görünebilir.  
  
-   Belirtilmeyen olup herhangi içindeki IF etkileri yan ifade veya **num_threads** ifade oluşur.  
  
-   A **throw** yürütülen içinde paralel bir bölge aynı yapılandırılmış blok dinamik kapsam içinde devam etmek yürütme neden gerekir ve bir özel durum belirtti aynı iş parçacığı tarafından yakalanan gerekir.  
  
-   Yalnızca tek bir **num_threads** yan tümcesi üzerinde yönergesi görünebilir. **Num_threads** ifade paralel bölge bağlamı dışında değerlendirilir ve pozitif bir tamsayı değerlendirmeniz gerekir.  
  
-   Değerlendirmesi sırasını **varsa** ve **num_threads** yan tümceleri belirtilmemiş.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **özel**, **firstprivate**, **varsayılan**, **paylaşılan**, **copyin**, ve **azaltma**yan tümceleri, bkz: [bölüm 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.  
  
-   **OMP_NUM_THREADS** ortam değişkeni [bölüm 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48.  
  
-   **omp_set_dynamic** kitaplığı işlevi görmek [bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.  
  
-   **Omp_dynamıc** ortam değişkeni, bkz: [bölüm 4.3](../../parallel/openmp/4-3-omp-dynamic.md) sayfasında 49.  
  
-   **omp_set_nested** işlev, bkz: [bölüm 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) sayfasında 40.  
  
-   **OMP_NESTED** ortam değişkeni, bkz: [bölüm 4.4](../../parallel/openmp/4-4-omp-nested.md) sayfasında 49.  
  
-   **omp_set_num_threads** kitaplığı işlevi görmek [bölüm 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) sayfasında 36.