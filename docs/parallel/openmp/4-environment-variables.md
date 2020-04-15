---
title: 4. Ortam değişkenleri
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: e93c59654c17ed6dbfb7483ac2dce716ce24b52a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370261"
---
# <a name="4-environment-variables"></a>4. Çevre değişkenleri

Bu bölümde, paralel kodun yürütülmesini kontrol eden OpenMP C ve C++ API ortam değişkenleri (veya benzer platforma özgü mekanizmalar) açıklanmaktadır.  Ortam değişkenlerinin adları büyük olmalıdır. Bunlara atanan değerler büyük/küçük harf duyarsızdır ve öncü ve sondaki beyaz alana sahip olabilir.  Program başladıktan sonra değerlerde yapılan değişiklikler yoksayılır.

Ortam değişkenleri aşağıdaki gibidir:

- [OMP_SCHEDULE](#41-omp_schedule) çalışma zamanı zamanlama türünü ve yığın boyutunu ayarlar.
- [OMP_NUM_THREADS](#42-omp_num_threads) yürütme sırasında kullanılacak iş parçacığı sayısını ayarlar.
- [OMP_DYNAMIC](#43-omp_dynamic) iş parçacığı sayısının dinamik ayarını sağlar veya devre dışı eder.
- [OMP_NESTED](#44-omp_nested) iç içe paralelliği sağlar veya devre dışı kılabilir.

Bu bölümdeki örnekler yalnızca bu değişkenlerin Unix C kabuk (csh) ortamlarında nasıl ayarlanabileceğini göstermektedir. Korn kabuk ve DOS ortamlarında, eylemler benzer:

Csh:  
`setenv OMP_SCHEDULE "dynamic"`

Ksh:  
`export OMP_SCHEDULE="dynamic"`

Dos:  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a><a name="41-omp_schedule"></a>4.1 OMP_SCHEDULE

`OMP_SCHEDULE`yalnızca zamanlama `for` türüne `parallel for` `runtime`sahip direktifler için geçerlidir. Tüm bu döngüler için zamanlama türü ve yığın boyutu çalışma zamanında ayarlanabilir. Bu ortam değişkenini tanınan herhangi bir zamanlama türüne ve isteğe bağlı bir *chunk_size*ayarlayın.

Için `for` `parallel for` ve dışında bir zamanlama türü `runtime` `OMP_SCHEDULE` olan yönergeler, yoksayılır. Bu ortam değişkeni için varsayılan değer uygulama tanımlıdır. İsteğe bağlı *chunk_size* ayarlanırsa, değer pozitif olmalıdır. *chunk_size* ayarlı değilse, zamanlama nın ne zaman olduğu `static`dışında 1 değeri varsayar. Bir `static` zamanlama için, varsayılan yığın boyutu döngüye uygulanan iş parçacığı sayısına bölünen döngü yineleme alanına ayarlanır.

Örnek:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>Çapraz referans

- yönerge [için](2-directives.md#241-for-construct)
- yönerge [için paralel](2-directives.md#251-parallel-for-construct)

## <a name="42-omp_num_threads"></a><a name="42-omp_num_threads"></a>4.2 OMP_NUM_THREADS

Ortam `OMP_NUM_THREADS` değişkeni yürütme sırasında kullanılacak varsayılan iş parçacığı sayısını ayarlar. `OMP_NUM_THREADS`bu numara kitaplık yordamı çağırılarak `omp_set_num_threads` açıkça değiştirilirse yoksayılır. Ayrıca, bir `num_threads` `parallel` yönergede açık bir yan tümce varsa da göz ardı edilir.

Ortam değişkeninin `OMP_NUM_THREADS` değeri pozitif bir tamsayı olmalıdır. Etkisi, iş parçacığı sayısının dinamik olarak ayarlanıp etkinleştirilemeyeceğine bağlıdır. Ortam değişkeni ve iş parçacıklarının `OMP_NUM_THREADS` dinamik ayarı arasındaki etkileşim le ilgili kapsamlı bir kural kümesi için [bölüm 2.3'e](2-directives.md#23-parallel-construct)bakın.

Kullanılacak iş parçacığı sayısı aşağıdaki gibi yse uygulama yla tanımlanır:

- `OMP_NUM_THREADS` çevre değişkeni belirtilmemişse,
- belirtilen değer pozitif tamsayı veya
- değeri, sistemin desteklenebildiği maksimum iş parçacığı sayısından daha büyüktür.

Örnek:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>Çapraz referans

- [num_threads](2-directives.md#23-parallel-construct) maddesi
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) fonksiyonu
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) fonksiyonu

## <a name="43-omp_dynamic"></a><a name="43-omp_dynamic"></a>4.3 OMP_DYNAMIC

Ortam `OMP_DYNAMIC` değişkeni, paralel bölgelerin yürütülmesi için kullanılabilir iş parçacığı sayısının dinamik ayarını sağlar veya devre dışı kılabilir. `OMP_DYNAMIC``omp_set_dynamic` kitaplık yordamı çağırılarak dinamik ayarlama açıkça etkinleştirildiğinde veya devre dışı bırakıldığında göz ardı edilir. Değeri veya `TRUE` `FALSE`.

`OMP_DYNAMIC` Ayarlanırsa, paralel bölgeleri yürütmek için kullanılan iş parçacığı sayısı sistem kaynaklarını en iyi şekilde kullanmak için çalışma zamanı ortamı tarafından `TRUE`ayarlanabilir.  `OMP_DYNAMIC` Ayarlanmışsa, dinamik ayarlama devre dışı `FALSE`bırakılır. Varsayılan koşul uygulama tanımlı.

Örnek:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>Çapraz referans

- [Paralel bölgeler](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) fonksiyonu

## <a name="44-omp_nested"></a><a name="44-omp_nested"></a>4.4 OMP_NESTED

Ortam `OMP_NESTED` değişkeni iç içe paralellik etkin veya `omp_set_nested` kitaplık yordamı çağırarak devre dışı sürece iç içe paralellik sağlar veya devre dışı. Eğer `OMP_NESTED` ayarlanırsa `TRUE`, iç içe paralellik etkindir. Eğer `OMP_NESTED` ayarlanırsa, `FALSE`iç içe paralellik devre dışı bırakılır. Varsayılan değer: `FALSE`.

Örnek:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>Çapraz referans

- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) fonksiyonu
