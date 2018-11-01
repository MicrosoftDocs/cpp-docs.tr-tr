---
title: sync_none Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
ms.openlocfilehash: eba2c60e621df717f29c0b25c735df3fda285fa0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510207"
---
# <a name="syncnone-class"></a>sync_none Sınıfı

Açıklayan bir [eşitleme filtresi](../standard-library/allocators-header.md) eşitleme sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_none
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Cache`|Eşitleme filtresiyle ilişkili önbellek türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|
|[equals](#equals)|Eşitlik için iki önbellekler karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="allocate"></a>  sync_none::allocate

Bir bellek bloğu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `cache.allocate(count)`burada `cache` önbellek nesnesi.

## <a name="deallocate"></a>  sync_none::deallocate

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

Üye işlev çağrıları `cache.deallocate(ptr, count)`burada `cache` önbellek nesnesini temsil eder.

## <a name="equals"></a>  sync_none::Equals

Eşitlik için iki önbellekler karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresi önbellek nesnesi.|
|*Diğer*|Eşitlik için karşılaştırma için önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi her zaman döndürür **true**.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
