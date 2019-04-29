---
title: 4. Ortam değişkenleri
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: b41829fd9cf2f90312f669ef991f56dda02947f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363199"
---
# <a name="4-environment-variables"></a>4. Ortam değişkenleri

OpenMP C ve C++ API ortam değişkenlerini (veya benzer bir platforma özgü mekanizmaları) Bu bölümde açıklanmaktadır paralel kod yürütme denetimi.  Ortam değişkenlerinin adları büyük olmalıdır. Atanmış değerleri büyük/küçük harfe duyarsızdır ve öndeki ve sondaki boşluk olabilir.  Değerlerin program başlatıldıktan sonra yapılan değişiklikler yok sayılır.

Ortam değişkenleri aşağıdaki gibidir:

- [OMP_SCHEDULE](#41-omp_schedule) çalışma zamanı zamanlama türü ve öbek boyutunu ayarlar.
- [OMP_NUM_THREADS](#42-omp_num_threads) yürütme sırasında kullanılacak iş parçacığı sayısını ayarlar.
- [Omp_dynamıc](#43-omp_dynamic) etkinleştirir veya iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakır.
- [OMP_NESTED](#44-omp_nested) etkinleştirir veya iç içe geçmiş paralellik devre dışı bırakır.

Bu bölümdeki örnekler, yalnızca bu değişkenleri UNIX C Kabuğu (csh) ortamlarda nasıl ayarlanabilir gösterir. Korn kabuk ve DOS ortamları, eylemleri benzerdir:

csh:  
`setenv OMP_SCHEDULE "dynamic"`

ksh:  
`export OMP_SCHEDULE="dynamic"`

DOS:  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a>4.1 OMP_SCHEDULE

`OMP_SCHEDULE` yalnızca geçerli `for` ve `parallel for` zamanlama türü olan yönergeleri `runtime`. Zamanlama türü ve Öbek boyutu tüm döngüler için çalışma zamanında ayarlanabilir. Herhangi bir tanınan zamanlama türü ve isteğe bağlı bu ortam değişkenini ayarlamak *chunk_size*.

İçin `for` ve `parallel for` dışındaki bir zamanlama türü olan yönergeleri `runtime`, `OMP_SCHEDULE` göz ardı edilir. Bu ortam değişkeni için varsayılan değer uygulama tarafından tanımlanır. İsteğe bağlı *chunk_size* ayarlanmış, değeri pozitif olmalıdır. Varsa *chunk_size* , 1 değeri kabul edilir, zamanlama dışında olduğunda, ayarlı değil `static`. İçin bir `static` zamanlama varsayılan öbek boyutu döngü için uygulanan bir iş parçacığı sayısını bölü döngü yineleme alanına ayarlanır.

Örnek:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>Çapraz başvuruları

- [için](2-directives.md#241-for-construct) yönergesi
- [için paralel](2-directives.md#251-parallel-for-construct) yönergesi

## <a name="42-omp_num_threads"></a>4.2 OMP_NUM_THREADS

`OMP_NUM_THREADS` Ortam değişkenini ayarlar varsayılan yürütme sırasında kullanılacak iş parçacığı sayısı. `OMP_NUM_THREADS` Bu sayıyı açıkça çağrılarak değiştirilirse göz ardı edilir `omp_set_num_threads` yordamı. Ayrıca varsa açık bir yoksayılır `num_threads` yan tümcesi bir `parallel` yönergesi.

Değerini `OMP_NUM_THREADS` ortam değişkeni, pozitif bir tamsayı olmalıdır. İş parçacığı sayısını yerleştirmenin dinamik ayarına etkin bağlı etkisini bağlıdır. Kurallar arasındaki etkileşimi hakkında kapsamlı bir dizi için `OMP_NUM_THREADS` ortam değişkeni ve dinamik ayarı iş parçacığı, bkz [bölümünde 2.3](2-directives.md#23-parallel-construct).

Kullanılacak iş parçacığı sayısını uygulama-ise tanımlanabilir:

- `OMP_NUM_THREADS` ortam değişkeni belirtilmediyse,
- Belirtilen değer pozitif bir tamsayı değil veya
- değer, sistemin destekleyebileceği iş parçacıklarını en fazla sayısından büyüktür.

Örnek:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>Çapraz başvuruları

- [num_threads](2-directives.md#23-parallel-construct) yan tümcesi
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) işlevi
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) işlevi

## <a name="43-omp_dynamic"></a>4.3 OMP_DYNAMIC

`OMP_DYNAMIC` Ortam değişkeni etkinleştirir veya paralel bölgeleri yürütülmesi için kullanılabilir iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakır. `OMP_DYNAMIC` yerleştirmenin dinamik ayarına açıkça etkin veya devre dışı çağırarak göz ardı edilir `omp_set_dynamic` yordamı. Değeri olmalıdır `TRUE` veya `FALSE`.

Varsa `OMP_DYNAMIC` ayarlanır `TRUE`, paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısını en iyi sistem kaynakları kullanmak için çalışma zamanı ortamı tarafından ayarlanmış.  Varsa `OMP_DYNAMIC` ayarlanır `FALSE`, yerleştirmenin dinamik ayarına devre dışı bırakıldı. Uygulama tanımlı varsayılan durumdur.

Örnek:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>Çapraz başvuruları

- [Paralel bölgeleri](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) işlevi

## <a name="44-omp_nested"></a>4.4 OMP_NESTED

`OMP_NESTED` Ortam değişkeni etkinleştirir veya iç içe geçmiş paralellik etkin veya devre dışı çağırarak sürece iç içe geçmiş paralellik devre dışı bırakır `omp_set_nested` yordamı. Varsa `OMP_NESTED` ayarlanır `TRUE`, iç içe geçmiş paralellik etkinleştirilir. Varsa `OMP_NESTED` ayarlanır `FALSE`, iç içe geçmiş paralellik devre dışı bırakıldı. Varsayılan değer `FALSE` şeklindedir.

Örnek:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>Çapraz

- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) işlevi
