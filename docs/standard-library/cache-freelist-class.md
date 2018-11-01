---
title: cache_freelist Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
ms.openlocfilehash: 56fdfb191f9208a5ffa692e1d599545ddeaeb36c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620096"
---
# <a name="cachefreelist-class"></a>cache_freelist Sınıfı

Tanımlayan bir [ayırıcı block](../standard-library/allocators-header.md) ayırır ve bellek blokları tek bir boyutta ayırmayı iptal eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*SZ*|Ayrılacak dizideki öğelerin sayısı.|
|*en fazla*|Boş listenin en büyük boyutunu temsil eden en fazla sınıf. Bu, [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), veya [max_variable_size](../standard-library/max-variable-size-class.md).|

## <a name="remarks"></a>Açıklamalar

Cache_freelist Şablon sınıfı bellek blok boyutu, ücretsiz bir listesini tutar *Sz*. Boş liste dolu olduğunda kullandığı **delete işleci** bellek ayırması engeller. Boş liste boş olduğunda kullandığı **new işleci** yeni bellek bloklarını ayrılamıyor. Boş listenin en büyük boyutu en fazla sınıf geçirilen sınıf tarafından belirlenir *Max* parametresi.

Her bellek bloğu şunları tutar *Sz* kullanılabilir bellek ve verileri baytlık, **new işleci** ve **delete işleci** gerektirir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_freelist](#cache_freelist)|Türünde bir nesne oluşturur `cache_freelist`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="allocate"></a>  cache_freelist::allocate

Bir bellek bloğu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış bir nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cache_freelist"></a>  cache_freelist::cache_freelist

Türünde bir nesne oluşturur `cache_freelist`.

```cpp
cache_freelist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>  cache_freelist::deallocate

Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Depolama alanından serbest bırakılması ilk nesneye bir işaretçi.|
|*Sayısı*|Depolama alanından serbest bırakılması nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
