---
title: OpenMP Ortam Değişkenleri
ms.date: 03/20/2019
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
ms.openlocfilehash: bee9b0fbdf147ee962ff92d0b3b9ff57d4209f84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363881"
---
# <a name="openmp-environment-variables"></a>OpenMP Ortam Değişkenleri

OpenMP API'de kullanılan ortam değişkenlerine bağlantılar sağlar.

OpenMP standardının Visual C++ uygulaması aşağıdaki ortam değişkenlerini içerir. Bu ortam değişkenleri program başlangıç sırasında okunur ve değerlerinde yapılan değişiklikler çalışma zamanında göz ardı edilir (örneğin, _putenv kullanarak [_wputenv).](../../../c-runtime-library/reference/putenv-wputenv.md)

|Ortam değişkeni|Açıklama|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|`for` Bir veya `parallel for` yönergede belirtildiğinde `schedule(runtime)` [zamanlama](openmp-clauses.md#schedule) yan tümcesinin davranışını değiştirir.|
|[OMP_NUM_THREADS](#omp-num-threads)|[omp_set_num_threads](openmp-functions.md#omp-set-num-threads) veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınmadığı sürece paralel bölgedeki en fazla iş parçacığı sayısını ayarlar.|
|[OMP_DYNAMIC](#omp-dynamic)|OpenMP çalışma süresinin paralel bir bölgedeki iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirtir.|
|[OMP_NESTED](#omp-nested)|İç içe paralellik etkin değilse, iç içe paralellik etkin `omp_set_nested`veya devre dışı bırakılmış sürece, iç içe paralellik etkin olup olmadığını belirtir.|

## <a name="omp_dynamic"></a><a name="omp-dynamic"></a>Omp_dynamıc

OpenMP çalışma süresinin paralel bir bölgedeki iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirtir.

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Açıklamalar

Ortam `OMP_DYNAMIC` değişkeni [omp_set_dynamic](openmp-functions.md#omp-set-dynamic) işlevi tarafından geçersiz kılınabilir.

OpenMP standardının Visual C++ uygulamasındavarsayılan değer `OMP_DYNAMIC=FALSE`.

Daha fazla bilgi için [4,3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)bakın.

### <a name="example"></a>Örnek

Aşağıdaki komut çevre `OMP_DYNAMIC` değişkenini TRUE olarak ayarlar:

```cmd
set OMP_DYNAMIC=TRUE
```

Aşağıdaki komut, ortam değişkeninin geçerli ayarını `OMP_DYNAMIC` görüntüler:

```cmd
set OMP_DYNAMIC
```

## <a name="omp_nested"></a><a name="omp-nested"></a>Omp_nested

İç içe paralellik etkin değilse, iç içe paralellik etkin `omp_set_nested`veya devre dışı bırakılmış sürece, iç içe paralellik etkin olup olmadığını belirtir.

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Açıklamalar

Ortam `OMP_NESTED` değişkeni [omp_set_nested](openmp-functions.md#omp-set-nested) işlevi tarafından geçersiz kılınabilir.

OpenMP standardının Visual C++ uygulamasındavarsayılan değer `OMP_DYNAMIC=FALSE`.

Daha fazla bilgi için [4,4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)bakın.

### <a name="example"></a>Örnek

Aşağıdaki komut çevre `OMP_NESTED` değişkenini TRUE olarak ayarlar:

```cmd
set OMP_NESTED=TRUE
```

Aşağıdaki komut, ortam değişkeninin geçerli ayarını `OMP_NESTED` görüntüler:

```cmd
set OMP_NESTED
```

## <a name="omp_num_threads"></a><a name="omp-num-threads"></a>Omp_num_threads

[omp_set_num_threads](openmp-functions.md#omp-set-num-threads) veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınmadığı sürece paralel bölgedeki en fazla iş parçacığı sayısını ayarlar.

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Parametreler

*sayı*<br/>
Paralel bölgede istediğiniz maksimum iş parçacığı sayısı, Visual C++ uygulamasında 64'e kadar.

### <a name="remarks"></a>Açıklamalar

Ortam `OMP_NUM_THREADS` değişkeni [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) işlevi veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınabilir.

OpenMP standardının `num` Visual C++ uygulamasında varsayılan değeri, hiperiş parçacığı CPU'ları da dahil olmak üzere sanal işlemci sayısıdır.

Daha fazla bilgi için [4,2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)bakın.

### <a name="example"></a>Örnek

Aşağıdaki komut ortam `OMP_NUM_THREADS` değişkenini şu şekilde `16`ayarlar:

```cmd
set OMP_NUM_THREADS=16
```

Aşağıdaki komut, ortam değişkeninin geçerli ayarını `OMP_NUM_THREADS` görüntüler:

```cmd
set OMP_NUM_THREADS
```

## <a name="omp_schedule"></a><a name="omp-schedule"></a>OMP_SCHEDULE

`for` Bir veya `parallel for` yönergede belirtildiğinde `schedule(runtime)` [zamanlama](openmp-clauses.md#schedule) yan tümcesinin davranışını değiştirir.

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
(İsteğe bağlı) Yinelemelerin boyutunu belirtir. *boyutu* pozitif bir tamsayı olmalıdır. Varsayılan değer, `1` *türü* statik olduğu durumlar dışındadır. *Türü* . `runtime`

*Türü*<br/>
`dynamic`Zamanlama türü, ya , `guided` `runtime`, `static`, ya da .

### <a name="remarks"></a>Açıklamalar

OpenMP standardının Visual C++ uygulamasındavarsayılan değer `OMP_SCHEDULE=static,0`.

Daha fazla bilgi için [4,1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)bakın.

### <a name="example"></a>Örnek

Aşağıdaki komut ortam `OMP_SCHEDULE` değişkenini ayarlar:

```cmd
set OMP_SCHEDULE="guided,2"
```

Aşağıdaki komut, ortam değişkeninin geçerli ayarını `OMP_SCHEDULE` görüntüler:

```cmd
set OMP_SCHEDULE
```
