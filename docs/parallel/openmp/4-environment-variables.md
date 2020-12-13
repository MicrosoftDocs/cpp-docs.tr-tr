---
description: 'Hakkında daha fazla bilgi edinin: 4. Ortam değişkenleri'
title: 4. Ortam değişkenleri
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: 47c0d557497a387f89c13c88c414aae9eb9377ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342536"
---
# <a name="4-environment-variables"></a>4. ortam değişkenleri

Bu bölümde, paralel kodun yürütülmesini denetleyen OpenMP C ve C++ API ortam değişkenleri (ya da benzer platforma özgü mekanizmalar) açıklanmaktadır.  Ortam değişkenlerinin adları büyük harfli olmalıdır. Bunlara atanan değerler büyük/küçük harfe duyarlıdır ve başında ve sonunda boşluk olabilir.  Program başlatıldıktan sonra değerlerde yapılan değişiklikler yok sayılır.

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

## <a name="41-omp_schedule"></a><a name="41-omp_schedule"></a> 4,1 OMP_SCHEDULE

`OMP_SCHEDULE` yalnızca `for` `parallel for` zamanlama türüne sahip olan yönergeler için geçerlidir `runtime` . Bu tür döngüler için zamanlama türü ve öbek boyutu çalışma zamanında ayarlanabilir. Bu ortam değişkenini herhangi bir kabul edilen zamanlama türüne ve isteğe bağlı bir *chunk_size* ayarlayın.

`for`Ve dışında `parallel for` bir zamanlama türüne sahip yönergeler `runtime` `OMP_SCHEDULE` yok sayılır. Bu ortam değişkeninin varsayılan değeri uygulama tanımlı ' dır. İsteğe bağlı *chunk_size* ayarlandıysa değer pozitif olmalıdır. *Chunk_size* ayarlanmamışsa, zamanlama dışında 1 değeri varsayılır `static` . Bir `static` zamanlama için varsayılan öbek boyutu, döngüye uygulanan iş parçacığı sayısına bölünen döngü yineleme alanı olarak ayarlanır.

Örnek:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>Çapraz başvurular

- [for](2-directives.md#241-for-construct) yönergesi
- [for yönergesi için Parallel](2-directives.md#251-parallel-for-construct)

## <a name="42-omp_num_threads"></a><a name="42-omp_num_threads"></a> 4,2 OMP_NUM_THREADS

`OMP_NUM_THREADS`Ortam değişkeni, yürütme sırasında kullanılacak varsayılan iş parçacığı sayısını ayarlar. `OMP_NUM_THREADS` Bu sayı, kitaplık yordamı çağırarak açıkça değiştirilirse yoksayılır `omp_set_num_threads` . Yönergede açık bir yan tümce varsa, bu da göz ardı edilir `num_threads` `parallel` .

`OMP_NUM_THREADS`Ortam değişkeninin değeri pozitif bir tamsayı olmalıdır. Etkisi, iş parçacığı sayısının dinamik ayarlamasının etkin olup olmamasına bağlıdır. Ortam değişkeni ve iş parçacıklarının dinamik ayarlaması arasındaki etkileşim hakkında kapsamlı bir kurallar kümesi için `OMP_NUM_THREADS` bkz. [Bölüm 2,3](2-directives.md#23-parallel-construct).

Şu durumlarda kullanılacak iş parçacıklarının sayısı uygulama tanımlı:

- `OMP_NUM_THREADS`ortam değişkeni belirtilmemiş,
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

## <a name="43-omp_dynamic"></a><a name="43-omp_dynamic"></a> 4,3 OMP_DYNAMIC

`OMP_DYNAMIC`Ortam değişkeni, paralel bölgelerin yürütülmesi için kullanılabilen iş parçacığı sayısı için dinamik ayarlamayı mümkün veya devre dışı bırakır. `OMP_DYNAMIC` Dinamik ayarlama açık olarak etkinleştirildiğinde veya kitaplık yordamı çağırarak devre dışı bırakıldığında yok sayılır `omp_set_dynamic` . Değeri `TRUE` veya olmalıdır `FALSE` .

`OMP_DYNAMIC`Olarak ayarlanırsa `TRUE` , paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısı, sistem kaynaklarını en iyi şekilde kullanmak için çalışma zamanı ortamı tarafından ayarlanabilir.  , `OMP_DYNAMIC` Olarak ayarlanırsa `FALSE` , dinamik ayarlama devre dışı bırakılır. Varsayılan koşul uygulama tanımlı ' dır.

Örnek:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>Çapraz başvurular

- [Paralel bölgeler](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) işlevi

## <a name="44-omp_nested"></a><a name="44-omp_nested"></a> 4,4 OMP_NESTED

Ortam değişkeni, iç içe paralelliği devre dışı `OMP_NESTED` bırakır veya devre dışı bırakır `omp_set_nested` . `OMP_NESTED`Olarak ayarlanırsa `TRUE` , iç içe paralellik etkindir. `OMP_NESTED`Olarak ayarlanırsa `FALSE` , iç içe paralellik devre dışı bırakılır. `FALSE` varsayılan değerdir.

Örnek:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>Çapraz başvuru

- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) işlevi
