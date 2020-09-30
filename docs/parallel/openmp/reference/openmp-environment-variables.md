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
ms.openlocfilehash: 3f9117c531bdf0c5a0c94e0b18a055591f431036
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503748"
---
# <a name="openmp-environment-variables"></a>OpenMP Ortam Değişkenleri

OpenMP API 'sinde kullanılan ortam değişkenlerine bağlantılar sağlar.

OpenMP standardının Visual C++ uygulanması aşağıdaki ortam değişkenlerini içerir. Bu ortam değişkenleri program başlangıcında okunurdur ve değerlerinde yapılan değişiklikler çalışma zamanında yok sayılır (örneğin, [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|Ortam değişkeni|Açıklama|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|Or yönergesinde belirtildiğinde [Schedule](openmp-clauses.md#schedule) yan tümcesinin davranışını değiştirir `schedule(runtime)` `for` `parallel for` .|
|[OMP_NUM_THREADS](#omp-num-threads)|[Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınmadıkça, paralel bölgedeki en fazla iş parçacığı sayısını ayarlar.|
|[OMP_DYNAMIC](#omp-dynamic)|OpenMP çalışma zamanının bir paralel bölgedeki iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirtir.|
|[OMP_NESTED](#omp-nested)|İç içe paralellik etkinleştirilmemiş veya ile devre dışı bırakılmadığı takdirde, iç içe paralel paralellik etkinleştirilip etkinleştirilmeyeceğini belirtir `omp_set_nested` .|

## <a name="omp_dynamic"></a><a name="omp-dynamic"></a> OMP_DYNAMIC

OpenMP çalışma zamanının bir paralel bölgedeki iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirtir.

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Açıklamalar

`OMP_DYNAMIC`Ortam değişkeni [omp_set_dynamic](openmp-functions.md#omp-set-dynamic) işlevi tarafından geçersiz kılınabilir.

OpenMP standardının Visual C++ uygulamasındaki varsayılan değer `OMP_DYNAMIC=FALSE` .

Daha fazla bilgi için bkz. [4,3 OMP_DYNAMIC](../4-environment-variables.md#43-omp_dynamic).

### <a name="example"></a>Örnek

Aşağıdaki komut, `OMP_DYNAMIC` ortam DEĞIŞKENINI true olarak ayarlar:

```cmd
set OMP_DYNAMIC=TRUE
```

Aşağıdaki komut, ortam değişkeninin geçerli ayarını görüntüler `OMP_DYNAMIC` :

```cmd
set OMP_DYNAMIC
```

## <a name="omp_nested"></a><a name="omp-nested"></a> OMP_NESTED

İç içe paralellik etkinleştirilmemiş veya ile devre dışı bırakılmadığı takdirde, iç içe paralel paralellik etkinleştirilip etkinleştirilmeyeceğini belirtir `omp_set_nested` .

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Açıklamalar

`OMP_NESTED`Ortam değişkeni [omp_set_nested](openmp-functions.md#omp-set-nested) işlevi tarafından geçersiz kılınabilir.

OpenMP standardının Visual C++ uygulamasındaki varsayılan değer `OMP_DYNAMIC=FALSE` .

Daha fazla bilgi için bkz. [4,4 OMP_NESTED](../4-environment-variables.md#44-omp_nested).

### <a name="example"></a>Örnek

Aşağıdaki komut, `OMP_NESTED` ortam DEĞIŞKENINI true olarak ayarlar:

```cmd
set OMP_NESTED=TRUE
```

Aşağıdaki komut, ortam değişkeninin geçerli ayarını görüntüler `OMP_NESTED` :

```cmd
set OMP_NESTED
```

## <a name="omp_num_threads"></a><a name="omp-num-threads"></a> OMP_NUM_THREADS

[Omp_set_num_threads](openmp-functions.md#omp-set-num-threads) veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınmadıkça, paralel bölgedeki en fazla iş parçacığı sayısını ayarlar.

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Parametreler

*numaraları*<br/>
Visual C++ uygulamasında, paralel bölgede en fazla 64 ' a kadar istediğiniz iş parçacığı sayısı.

### <a name="remarks"></a>Açıklamalar

`OMP_NUM_THREADS`Ortam değişkeni [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) işlevi veya [num_threads](openmp-clauses.md#num-threads)tarafından geçersiz kılınabilir.

`num`OpenMP standardının Visual C++ uygulamasındaki varsayılan değeri, hiper iş parçacığı oluşturma CPU 'ları dahil sanal işlemcilerin sayısıdır.

Daha fazla bilgi için bkz. [4,2 omp_num_threads](../4-environment-variables.md#42-omp_num_threads).

### <a name="example"></a>Örnek

Aşağıdaki komut, `OMP_NUM_THREADS` ortam değişkenini şu şekilde ayarlar `16` :

```cmd
set OMP_NUM_THREADS=16
```

Aşağıdaki komut, ortam değişkeninin geçerli ayarını görüntüler `OMP_NUM_THREADS` :

```cmd
set OMP_NUM_THREADS
```

## <a name="omp_schedule"></a><a name="omp-schedule"></a> OMP_SCHEDULE

Or yönergesinde belirtildiğinde [Schedule](openmp-clauses.md#schedule) yan tümcesinin davranışını değiştirir `schedule(runtime)` `for` `parallel for` .

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
Seçim Yinelemelerin boyutunu belirtir. *Boyut* pozitif bir tamsayı olmalıdır. Varsayılan değer `1` , *tür* statiktir dışında olur. *Tür* olduğunda geçerli değildir `runtime` .

*türüyle*<br/>
Zamanlama türü,,, `dynamic` ya da `guided` `runtime` `static` .

### <a name="remarks"></a>Açıklamalar

OpenMP standardının Visual C++ uygulamasındaki varsayılan değer `OMP_SCHEDULE=static,0` .

Daha fazla bilgi için bkz. [4,1 omp_schedule](../4-environment-variables.md#41-omp_schedule).

### <a name="example"></a>Örnek

Aşağıdaki komut, `OMP_SCHEDULE` ortam değişkenini ayarlar:

```cmd
set OMP_SCHEDULE="guided,2"
```

Aşağıdaki komut, ortam değişkeninin geçerli ayarını görüntüler `OMP_SCHEDULE` :

```cmd
set OMP_SCHEDULE
```
