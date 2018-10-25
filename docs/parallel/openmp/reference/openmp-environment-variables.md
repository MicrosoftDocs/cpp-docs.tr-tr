---
title: OpenMP ortam değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a229aa453b6e40f0da25252f2f8aa1be3d97a729
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074260"
---
# <a name="openmp-environment-variables"></a>OpenMP ortam değişkenleri

OpenMP API çağrısında kullanılan ortam değişkenlerini bağlantılar sağlar.

Standart OpenMP Visual C++ uygulaması, aşağıdaki ortam değişkenlerini içerir. Bu ortam değişkenleri, program başlangıcında okunduğu ve değerlerine yapılan değişiklikler çalışma zamanında yok sayıldı (örnek olarak, [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|ortam değişkeni|Açıklama|
|--------------------|-----------|
|[OMP_DYNAMIC](#omp-dynamic)|Çalışma zamanı OpenMP bir paralel bölgenin içinde iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirler.|
|[OMP_NESTED](#omp-nested)|İç içe geçmiş paralellik etkin veya ile devre dışı sürece iç içe geçmiş paralellik, etkin olup olmadığını belirten `omp_set_nested`.|
|[OMP_NUM_THREADS](#omp-num-threads)|İş parçacığı sayısı tarafından geçersiz kılınmadığı sürece paralel bölgenin içinde ayarlar [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) veya [num_threads](openmp-clauses.md#num-threads).|
|[OMP_SCHEDULE](#omp-schedule)|Davranışını değiştiren [zamanlama](openmp-clauses.md#schedule) yan tümcesi olduğunda `schedule(runtime)` belirtilen bir `for` veya `parallel for` yönergesi.|

## <a name="omp-dynamic"></a>OMP_DYNAMIC

Çalışma zamanı OpenMP bir paralel bölgenin içinde iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirler.

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Açıklamalar

`OMP_DYNAMIC` Ortam değişkeni tarafından kılınabilir [omp_set_dynamic](openmp-functions.md#omp-set-dynamic) işlevi.

Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_DYNAMIC=FALSE`.

Daha fazla bilgi için [4.3 omp_dynamıc](../../../parallel/openmp/4-3-omp-dynamic.md).

### <a name="example"></a>Örnek

Aşağıdaki komut kümelerini `OMP_DYNAMIC` ortam değişkenini TRUE:

```
set OMP_DYNAMIC=TRUE
```

Aşağıdaki komut, geçerli ayarı görüntüler `OMP_DYNAMIC` ortam değişkeni:

```
set OMP_DYNAMIC
```

## <a name="omp-nested"></a>OMP_NESTED

İç içe geçmiş paralellik etkin veya ile devre dışı sürece iç içe geçmiş paralellik, etkin olup olmadığını belirten `omp_set_nested`.

```
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Açıklamalar

`OMP_NESTED` Ortam değişkeni tarafından kılınabilir [omp_set_nested](openmp-functions.md#omp-set-nested) işlevi.

Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_DYNAMIC=FALSE`.

Daha fazla bilgi için [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).

### <a name="example"></a>Örnek

Aşağıdaki komut kümelerini `OMP_NESTED` ortam değişkenini TRUE:

```
set OMP_NESTED=TRUE
```

Aşağıdaki komut, geçerli ayarı görüntüler `OMP_NESTED` ortam değişkeni:

```
set OMP_NESTED
```

## <a name="omp-num-threads"></a>OMP_NUM_THREADS

İş parçacığı sayısı tarafından geçersiz kılınmadığı sürece paralel bölgenin içinde ayarlar [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) veya [num_threads](openmp-clauses.md#num-threads).

```
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Parametreler

*sayı*<br/>
Visual C++ uygulamasında 64 adede kadar bir paralel bölgenin içinde istediğiniz iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

`OMP_NUM_THREADS` Ortam değişkeni tarafından kılınabilir [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) işlevi ya da [num_threads](openmp-clauses.md#num-threads).

Varsayılan değer olan `num` Visual C++'da OpenMP standart hiper iş parçacıklı CPU dahil olmak üzere, sanal işlemcilerin sayısını uygulamasıdır.

Daha fazla bilgi için [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).

### <a name="example"></a>Örnek

Aşağıdaki komut kümelerini `OMP_NUM_THREADS` 16 ortam değişkeni:

```
set OMP_NUM_THREADS=16
```

Aşağıdaki komut, geçerli ayarı görüntüler `OMP_NUM_THREADS` ortam değişkeni:

```
set OMP_NUM_THREADS
```

## <a name="omp-schedule"></a>OMP_SCHEDULE

Davranışını değiştiren [zamanlama](openmp-clauses.md#schedule) yan tümcesi olduğunda `schedule(runtime)` belirtilen bir `for` veya `parallel for` yönergesi.

```
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
(İsteğe bağlı) Yinelemeler boyutunu belirtir. `size` Pozitif bir tamsayı olmalıdır. Varsayılan değer 1, aşağıdakiler haricinde `type` statiktir. Geçersiz zaman `type` olduğu `runtime`.

*Türü*<br/>
Zamanlama türü:

- `dynamic`
- `guided`
- `runtime`
- `static`

### <a name="remarks"></a>Açıklamalar

Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_SCHEDULE=static,0`.

Daha fazla bilgi için [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).

### <a name="example"></a>Örnek

Aşağıdaki komut kümelerini `OMP_SCHEDULE` ortam değişkeni:

```
set OMP_SCHEDULE="guided,2"
```

Aşağıdaki komut, geçerli ayarı görüntüler `OMP_SCHEDULE` ortam değişkeni:

```
set OMP_SCHEDULE
```
