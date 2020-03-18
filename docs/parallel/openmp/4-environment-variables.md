---
title: 4. Ortam değişkenleri
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: b41829fd9cf2f90312f669ef991f56dda02947f7
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417056"
---
# <a name="4-environment-variables"></a>4. ortam değişkenleri

Bu bölümde, paralel kodun yürütülmesini denetleyen C++ OpenMP C ve API ortam değişkenleri (ya da benzer platforma özgü mekanizmalar) açıklanmaktadır.  Ortam değişkenlerinin adları büyük harfli olmalıdır. Bunlara atanan değerler büyük/küçük harfe duyarlıdır ve başında ve sonunda boşluk olabilir.  Program başlatıldıktan sonra değerlerde yapılan değişiklikler yok sayılır.

Ortam değişkenleri aşağıdaki gibidir:

- [Omp_schedule](#41-omp_schedule) çalışma zamanı zamanlama türünü ve öbek boyutunu ayarlar.
- [Omp_num_threads](#42-omp_num_threads) , yürütme sırasında kullanılacak iş parçacığı sayısını belirler.
- [OMP_DYNAMIC](#43-omp_dynamic) , iş parçacıklarının sayısını dinamik olarak ayarlamayı mümkün veya devre dışı bırakır.
- [OMP_NESTED](#44-omp_nested) iç içe paralel paralellik etkinleştirilir veya devre dışı bırakır.

Bu bölümdeki örneklerde yalnızca bu değişkenlerin UNIX C kabuğu (csh) ortamlarında nasıl ayarlanbileceği gösterilmektedir. Korn kabuğu ve DOS ortamlarında, işlemler benzerdir:

CSH:  
`setenv OMP_SCHEDULE "dynamic"`

ksh:  
`export OMP_SCHEDULE="dynamic"`

ÇALıŞTıRAN  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a>4,1 OMP_SCHEDULE

`OMP_SCHEDULE` yalnızca zamanlama türü `runtime`olan `for` ve `parallel for` yönergeleri için geçerlidir. Bu tür döngüler için zamanlama türü ve öbek boyutu çalışma zamanında ayarlanabilir. Bu ortam değişkenini herhangi bir kabul edilen zamanlama türüne ve isteğe bağlı bir *chunk_size*ayarlayın.

`runtime`dışında bir zamanlama türüne sahip `for` ve `parallel for` yönergeleri için `OMP_SCHEDULE` yok sayılır. Bu ortam değişkeninin varsayılan değeri uygulama tanımlı ' dır. İsteğe bağlı *chunk_size* ayarlandıysa değer pozitif olmalıdır. *Chunk_size* ayarlanmamışsa, zamanlamanın `static`dışında 1 değeri varsayılır. Bir `static` zamanlaması için, varsayılan öbek boyutu, döngüye uygulanan iş parçacığı sayısına bölünen döngü yineleme alanı olarak ayarlanır.

Örnek:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>Çapraz başvurular

- [for](2-directives.md#241-for-construct) yönergesi
- [for yönergesi için Parallel](2-directives.md#251-parallel-for-construct)

## <a name="42-omp_num_threads"></a>4,2 OMP_NUM_THREADS

`OMP_NUM_THREADS` ortam değişkeni, yürütme sırasında kullanılacak varsayılan iş parçacığı sayısını ayarlar. Bu sayı, `omp_set_num_threads` kitaplığı yordamı çağırarak açıkça değiştirilirse `OMP_NUM_THREADS` yok sayılır. Ayrıca, bir `parallel` yönergesinde açık bir `num_threads` yan tümcesi varsa de yok sayılır.

`OMP_NUM_THREADS` ortam değişkeninin değeri pozitif bir tamsayı olmalıdır. Etkisi, iş parçacığı sayısının dinamik ayarlamasının etkin olup olmamasına bağlıdır. `OMP_NUM_THREADS` ortam değişkeni ve iş parçacıklarının dinamik ayarlaması arasındaki etkileşim hakkında kapsamlı bir kurallar kümesi için bkz. [bölüm 2,3](2-directives.md#23-parallel-construct).

Şu durumlarda kullanılacak iş parçacıklarının sayısı uygulama tanımlı:

- `OMP_NUM_THREADS` ortam değişkeni belirtilmemiş,
- Belirtilen değer pozitif bir tamsayı değil veya
- değer, sistemin destekleyebileceği en fazla iş parçacığı sayısından daha büyük.

Örnek:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>Çapraz başvurular

- [num_threads](2-directives.md#23-parallel-construct) yan tümcesi
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) işlevi
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) işlevi

## <a name="43-omp_dynamic"></a>4,3 OMP_DYNAMIC

`OMP_DYNAMIC` ortam değişkeni, paralel bölgelerin yürütülmesi için kullanılabilen iş parçacığı sayısı için dinamik ayarlamayı mümkün veya devre dışı bırakır. Dinamik ayarlama açık olarak etkinleştirildiğinde veya `omp_set_dynamic` kitaplığı yordamı çağırarak devre dışı bırakıldığında `OMP_DYNAMIC` yok sayılır. Değeri `TRUE` veya `FALSE`olmalıdır.

`OMP_DYNAMIC` `TRUE`olarak ayarlanırsa, paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı, sistem kaynaklarını en iyi şekilde kullanmak için çalışma zamanı ortamı tarafından ayarlanabilir.  `OMP_DYNAMIC` `FALSE`olarak ayarlanırsa, dinamik ayarlama devre dışı bırakılır. Varsayılan koşul uygulama tanımlı ' dır.

Örnek:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>Çapraz başvurular

- [Paralel bölgeler](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) işlevi

## <a name="44-omp_nested"></a>4,4 OMP_NESTED

`OMP_NESTED` ortam değişkeni, iç içe paralelliği etkin hale `omp_set_nested` getirerek veya devre dışı bırakarak iç içe paralelliği devre dışı bırakır veya devre dışı bırakır. `OMP_NESTED` `TRUE`olarak ayarlanırsa, iç içe paralellik etkin olur. `OMP_NESTED` `FALSE`olarak ayarlanırsa, iç içe paralellik devre dışı bırakılır. Varsayılan değer `FALSE` şeklindedir.

Örnek:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>Çapraz başvuru

- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) işlevi
