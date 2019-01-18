---
title: 4. Ortam değişkenleri
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: 5d08031c252d1f3c45fc45c021d24476b393fe33
ms.sourcegitcommit: 2ebbf8093fadb9a1b78a4381439bcd5c01a89267
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/18/2019
ms.locfileid: "54397335"
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

## <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE

`OMP_SCHEDULE` yalnızca geçerli `for` ve `parallel for` zamanlama türü olan yönergeleri `runtime`. Zamanlama türü ve Öbek boyutu tüm döngüler için çalışma zamanında ayarlanabilir. Herhangi bir tanınan zamanlama türü ve isteğe bağlı bu ortam değişkenini ayarlamak *chunk_size*.

İçin `for` ve `parallel for` dışındaki bir zamanlama türü olan yönergeleri `runtime`, `OMP_SCHEDULE` göz ardı edilir. Bu ortam değişkeni için varsayılan değer uygulama tarafından tanımlanır. İsteğe bağlı *chunk_size* ayarlanmış, değeri pozitif olmalıdır. Varsa *chunk_size* , 1 değeri kabul edilir, zamanlama dışında olduğunda, ayarlı değil `static`. İçin bir `static` zamanlama varsayılan öbek boyutu döngü için uygulanan bir iş parçacığı sayısını bölü döngü yineleme alanına ayarlanır.

Örnek:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>Çapraz başvuruları

- [için](2-4-1-for-construct.md) yönergesi
- [için paralel](2-5-1-parallel-for-construct.md) yönergesi

## <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS

`OMP_NUM_THREADS` Ortam değişkenini ayarlar varsayılan yürütme sırasında kullanılacak iş parçacığı sayısı. `OMP_NUM_THREADS` Bu sayıyı açıkça çağrılarak değiştirilirse göz ardı edilir `omp_set_num_threads` yordamı. Ayrıca varsa açık bir yoksayılır `num_threads` yan tümcesi bir `parallel` yönergesi.

Değerini `OMP_NUM_THREADS` ortam değişkeni, pozitif bir tamsayı olmalıdır. İş parçacığı sayısını yerleştirmenin dinamik ayarına etkin bağlı etkisini bağlıdır. Kurallar arasındaki etkileşimi hakkında kapsamlı bir dizi için `OMP_NUM_THREADS` ortam değişken ve dinamik düzeltmesi iş parçacığı, bölüm 2.3 bakın.

Kullanılacak iş parçacığı sayısını uygulama-ise tanımlanabilir:

- `OMP_NUM_THREADS` ortam değişkeni belirtilmediyse,
- Belirtilen değer pozitif bir tamsayı değil veya
- değer, sistemin destekleyebileceği iş parçacıklarını en fazla sayısından büyüktür.

Örnek:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>Çapraz başvuruları

- [num_threads](2-3-parallel-construct.md) yan tümcesi
- [omp_set_num_threads](3-1-1-omp-set-num-threads-function.md) işlevi
- [omp_set_dynamic](3-1-7-omp-set-dynamic-function.md) işlevi

## <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC

`OMP_DYNAMIC` Ortam değişkeni etkinleştirir veya paralel bölgeleri yürütülmesi için kullanılabilir iş parçacığı sayısını yerleştirmenin dinamik ayarına devre dışı bırakır. `OMP_DYNAMIC` yerleştirmenin dinamik ayarına açıkça etkin veya devre dışı çağırarak göz ardı edilir `omp_set_dynamic` yordamı. Değeri olmalıdır `TRUE` veya `FALSE`.

Varsa `OMP_DYNAMIC` ayarlanır `TRUE`, paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısını en iyi sistem kaynakları kullanmak için çalışma zamanı ortamı tarafından ayarlanmış.  Varsa `OMP_DYNAMIC` ayarlanır `FALSE`, yerleştirmenin dinamik ayarına devre dışı bırakıldı. Uygulama tanımlı varsayılan durumdur.

Örnek:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>Çapraz başvuruları

- [Paralel bölgeleri](2-3-parallel-construct.md)
- [omp_set_dynamic](3-1-7-omp-set-dynamic-function.md) işlevi

## <a name="44-ompnested"></a>4.4 OMP_NESTED

`OMP_NESTED` Ortam değişkeni etkinleştirir veya iç içe geçmiş paralellik etkin veya devre dışı çağırarak sürece iç içe geçmiş paralellik devre dışı bırakır `omp_set_nested` yordamı. Varsa `OMP_NESTED` ayarlanır `TRUE`, iç içe geçmiş paralellik etkinleştirilir. Varsa `OMP_NESTED` ayarlanır `FALSE`, iç içe geçmiş paralellik devre dışı bırakıldı. Varsayılan değer `FALSE` şeklindedir.

Örnek:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>Çapraz

- [omp_set_nested](3-1-9-omp-set-nested-function.md) işlevi
