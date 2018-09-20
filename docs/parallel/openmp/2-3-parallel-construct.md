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
ms.openlocfilehash: 4be5bdc40f69cfa0a326ffa6a7f8465e401cfd33
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448239"
---
# <a name="23-parallel-construct"></a>2.3 parallel Yapı

Aşağıdaki yönerge bir bölgesi paralel birden çok iş parçacığı tarafından yürütülecek program bir paralel bölgenin tanımlar. Bu, Paralel yürütme başlatan temel bir yapıdır.

```
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block
```

*Yan tümcesi* aşağıdakilerden biridir:

**varsa (** *skaler ifade* **)**

**Özel (** *değişken listesi* **)**

**firstprivate (** *değişken listesi* **)**

**Varsayılan (paylaşılan &#124; yok)**

**Paylaşılan (** *değişken listesi* **)**

**copyin (** *değişken listesi* **)**

**azaltma (** *işleci* **:***değişken listesi* **)** 

**num_threads (** *tamsayı ifadesi* **)**

Bir iş parçacığını paralel bir yapısı karşılaştığında, aşağıdaki durumlarda biri true ise, bir takım iş parçacıkları oluşturulur:

- Hayır **varsa** yan tümcesi varsa.

- **Varsa** ifadeyi sıfır dışında bir değeri hesaplar.

Bu iş parçacığı bir iş parçacığı numarası 0 ile takım ana iş parçacığı haline gelir ve takım ana iş parçacığı dahil olmak üzere tüm iş parçacıklarının bölge paralel olarak çalıştırmak. Varsa değerini **varsa** ifade sıfırsa, bölge sıralanır.

İstenen iş parçacığı sayısını belirlemek için aşağıdaki kurallar sırayla değerlendirilir. Koşulu karşılandığında ilk kural uygulanacak:

1. Varsa **num_threads** yan tümcesi varsa, ardından istenen iş parçacığı sayısını ifade tamsayı değeridir.

1. Varsa **omp_set_num_threads** kitaplığı işlevi çağrılır, ardından istenen iş parçacığı sayısını en yakın zamanda yürütülen çağrısında bağımsız değişken değeridir.

1. Ortam değişkenini **OMP_NUM_THREADS** tanımlanır, bu ortam değişkeninin değerini ise istenen iş parçacığı sayısı.

1. Yukarıdaki yöntemlerin hiçbiri kullanıldıysa, uygulama tanımlı istenen iş parçacığı sayısı.

Varsa **num_threads** yan tümcesi varsa sonra tarafından istenen iş parçacığı sayısını sürümlereni **omp_set_num_threads** kitaplığı işlevi veya **OMP_NUM_THREADS** yalnızca bir paralel bölgenin için ortam değişkenini uygulanır. Sonraki paralel bölgeleri bundan etkilenmez.

Paralel bölgenin yürütme iş parçacığı sayısını desteklemediğini iş parçacığı sayısını yerleştirmenin dinamik ayarına etkinleştirilmiş olup da bağlıdır. Yerleştirmenin dinamik ayarına devre dışıysa, istenen iş parçacığı sayısını paralel bölgenin yürütün. Yerleştirmenin dinamik ayarına etkinse, istenen iş parçacığı sayısı en fazla paralel bölgenin yürütebilir iş parçacığı sayısı olan.

Bir paralel bölgenin iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakıldı ve paralel bölge için istenen iş parçacığı sayısını çalışma zamanı sistemi sağladığınız aşıyor karşılaşılırsa, davranıştır programı uygulama tanımlı. Bir uygulama gibi programın yürütülmesini kesme olabilir veya paralel bölgenin serileştirmek.

**Omp_set_dynamic** kitaplığı işlevi ve **omp_dynamıc** ortam değişkeni, etkinleştirmek ve iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakmak için kullanılabilir.

Aslında iş parçacığı herhangi bir zamanda barındıran fiziksel işlemcilerin sayısını uygulama tanımlanır. Takım iş parçacıkları sayısı oluşturulduktan sonra bir paralel bölgenin süresi boyunca sabit kalır. Kullanıcı tarafından açıkça veya otomatik olarak bir paralel bölgenin başka bir çalışma zamanı sistemi tarafından değiştirilebilir.

Dinamik kapsamını paralel bölgenin içinde yer alan ifadeleri her iş parçacığı tarafından yürütülür ve diğer iş parçacıklarından farklı bir yol deyimlerinin her iş parçacığı yürütebilirsiniz. Bir paralel bölgenin dışında sözcük kapsamını karşılaştı yönergeleri yalnız bırakılmış yönergeleri olarak adlandırılır.

Bir paralel bölgenin sonunda örtük bir engel var. Yalnızca ana iş parçacığı ekibin sonunda bir paralel bölgenin, yürütme devam eder.

Bir iş parçacığında bir paralel bölgenin yürütülürken bir ekibin paralel bir başka yapının karşılaşırsa, yeni bir takım oluşturur ve bu yeni takım ana olur. İç içe geçmiş paralel bölgeleri varsayılan olarak serileştirilir. Sonuç olarak, varsayılan olarak, iç içe geçmiş bir paralel bölgenin bir iş parçacığından oluşan bir ekip tarafından yürütülür. Çalışma Zamanı Kitaplığı işlevi'ni kullanarak varsayılan davranış değiştirilebilir **omp_set_nested** veya ortam değişkenini **OMP_NESTED**. Ancak, iç içe geçmiş bir paralel bölgenin yürüten iş parçacığı ekip uygulama tanımlı sayısıdır.

Kısıtlamaları **paralel** yönerge aşağıdaki gibidir:

- En fazla bir **varsa** yönergesindeki yan tümcesi görünebilir.

- Belirtilmeyen herhangi etkileri if içinde olup olmadığını yan ifade veya **num_threads** ifade oluşur.

- A **throw** yürütülen içinde bir paralel bölgenin içinde aynı yapısal bloğunun dinamik kapsamını sürdürmek yürütme neden ve özel durum oluşturdu aynı iş parçacığı tarafından yakalanmalıdır.

- Yalnızca tek bir **num_threads** yönergesindeki yan tümcesi görünebilir. **Num_threads** deyimi bir paralel bölgenin bağlamı dışında değerlendirilir ve bir pozitif tamsayı değer olarak değerlendirilmesi gerekir.

- Değerlendirilme sırasını **varsa** ve **num_threads** yan tümceleri belirtilmez.

## <a name="cross-references"></a>Başvuruları çapraz:

- **özel**, **firstprivate**, **varsayılan**, **paylaşılan**, **copyin**, ve **azaltma**yan tümcesi bkz [bölümü 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.

- **OMP_NUM_THREADS** ortam değişkeni [bölümü 4.2](../../parallel/openmp/4-2-omp-num-threads.md) sayfasında 48.

- **omp_set_dynamic** kitaplığı işlevi görmek [bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.

- **Omp_dynamıc** ortam değişkeni, bkz: [bölümü 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 sayfasında.

- **omp_set_nested** çalışması için bkz: [bölümü 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 sayfasında.

- **OMP_NESTED** ortam değişkeni, bkz: [bölümü 4.4](../../parallel/openmp/4-4-omp-nested.md) 49 sayfasında.

- **omp_set_num_threads** kitaplığı işlevi görmek [bölümü 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 sayfasında.