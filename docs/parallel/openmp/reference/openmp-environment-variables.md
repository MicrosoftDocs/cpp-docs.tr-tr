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
ms.openlocfilehash: 838427320fcb68cedb97b36156fc18002ed962d8
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417007"
---
# <a name="openmp-environment-variables"></a>OpenMP Ortam Değişkenleri

OpenMP API 'sinde kullanılan ortam değişkenlerine bağlantılar sağlar.

OpenMP standardının C++ görsel uygulanması aşağıdaki ortam değişkenlerini içerir. Bu ortam değişkenleri program başlangıcında okunurdur ve değerlerinde yapılan değişiklikler çalışma zamanında yok sayılır (örneğin, [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|Ortam değişkeni|Açıklama|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|`for` veya `parallel for` yönergesinde `schedule(runtime)` belirtildiğinde [Schedule](openmp-clauses.md#schedule) yan tümcesinin davranışını değiştirir.|
|[OMP_NUM_THREADS](#omp-num-threads)|[Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınmadıkça, paralel bölgedeki en fazla iş parçacığı sayısını ayarlar.|
|[OMP_DYNAMIC](#omp-dynamic)|OpenMP çalışma zamanının bir paralel bölgedeki iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirtir.|
|[OMP_NESTED](#omp-nested)|İç içe paralellik etkinleştirilmemiş veya `omp_set_nested`ile devre dışı bırakılmamışsa, iç içe paralel paralellik etkinleştirilip etkinleştirilmeyeceğini belirtir.|

## <a name="omp-dynamic"></a>OMP_DYNAMIC

OpenMP çalışma zamanının bir paralel bölgedeki iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirtir.

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Açıklamalar

`OMP_DYNAMIC` ortam değişkeni [omp_set_dynamic](openmp-functions.md#omp-set-dynamic) işlevi tarafından geçersiz kılınabilir.

OpenMP standardının görsel C++ uygulamasındaki varsayılan değer `OMP_DYNAMIC=FALSE`.

Daha fazla bilgi için bkz. [4,3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).

### <a name="example"></a>Örnek

Aşağıdaki komut `OMP_DYNAMIC` ortam değişkenini TRUE olarak ayarlar:

```cmd
set OMP_DYNAMIC=TRUE
```

Aşağıdaki komut `OMP_DYNAMIC` ortam değişkeninin geçerli ayarını görüntüler:

```cmd
set OMP_DYNAMIC
```

## <a name="omp-nested"></a>OMP_NESTED

İç içe paralellik etkinleştirilmemiş veya `omp_set_nested`ile devre dışı bırakılmamışsa, iç içe paralel paralellik etkinleştirilip etkinleştirilmeyeceğini belirtir.

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Açıklamalar

`OMP_NESTED` ortam değişkeni [omp_set_nested](openmp-functions.md#omp-set-nested) işlevi tarafından geçersiz kılınabilir.

OpenMP standardının görsel C++ uygulamasındaki varsayılan değer `OMP_DYNAMIC=FALSE`.

Daha fazla bilgi için bkz. [4,4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).

### <a name="example"></a>Örnek

Aşağıdaki komut `OMP_NESTED` ortam değişkenini TRUE olarak ayarlar:

```cmd
set OMP_NESTED=TRUE
```

Aşağıdaki komut `OMP_NESTED` ortam değişkeninin geçerli ayarını görüntüler:

```cmd
set OMP_NESTED
```

## <a name="omp-num-threads"></a>OMP_NUM_THREADS

[Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınmadıkça, paralel bölgedeki en fazla iş parçacığı sayısını ayarlar.

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Parametreler

*numaraları*<br/>
Görsel C++ uygulamada 64 'e kadar, paralel bölgede istediğiniz en fazla iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

`OMP_NUM_THREADS` ortam değişkeni [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) işlevi veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınabilir.

OpenMP standardının görsel C++ uygulamasındaki `num` varsayılan değeri, hiper iş parçacığı oluşturma CPU 'ları dahil sanal işlemcilerin sayısıdır.

Daha fazla bilgi için bkz. [4,2 omp_num_threads](../../../parallel/openmp/4-2-omp-num-threads.md).

### <a name="example"></a>Örnek

Aşağıdaki komut `OMP_NUM_THREADS` ortam değişkenini `16`olarak ayarlar:

```cmd
set OMP_NUM_THREADS=16
```

Aşağıdaki komut `OMP_NUM_THREADS` ortam değişkeninin geçerli ayarını görüntüler:

```cmd
set OMP_NUM_THREADS
```

## <a name="omp-schedule"></a>OMP_SCHEDULE

`for` veya `parallel for` yönergesinde `schedule(runtime)` belirtildiğinde [Schedule](openmp-clauses.md#schedule) yan tümcesinin davranışını değiştirir.

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Seçim Yinelemelerin boyutunu belirtir. *Boyut* pozitif bir tamsayı olmalıdır. *Türün* statik olması dışında varsayılan değer `1`. *Tür* `runtime`olduğunda geçerli değildir.

*type*<br/>
`dynamic`, `guided`, `runtime`ya da `static`zamanlama türü.

### <a name="remarks"></a>Açıklamalar

OpenMP standardının görsel C++ uygulamasındaki varsayılan değer `OMP_SCHEDULE=static,0`.

Daha fazla bilgi için bkz. [4,1 omp_schedule](../../../parallel/openmp/4-1-omp-schedule.md).

### <a name="example"></a>Örnek

Aşağıdaki komut `OMP_SCHEDULE` ortam değişkenini ayarlar:

```cmd
set OMP_SCHEDULE="guided,2"
```

Aşağıdaki komut `OMP_SCHEDULE` ortam değişkeninin geçerli ayarını görüntüler:

```cmd
set OMP_SCHEDULE
```
