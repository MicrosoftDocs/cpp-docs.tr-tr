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
ms.openlocfilehash: 4cb311289207dbcf78186e11b2c7f03c503389e5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450310"
---
# <a name="syncnone-class"></a>sync_none Sınıfı

Eşitleme sağlayan bir [eşitleme filtresi](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_none
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Cache`|Eşitleme filtresiyle ilişkili önbelleğin türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)veya [cache_suballoc](../standard-library/cache-suballoc-class.md)olabilir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[equals](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ayrıcılar >

**Ad alanı:** stdext

## <a name="allocate"></a>sync_none:: allocate

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*biriktirme*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi döner `cache.allocate(count)`, burada `cache` Cache nesnesidir.

## <a name="deallocate"></a>sync_none::d eallocate

Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Depolamadan serbest bırakmak için ilk nesneye yönelik bir işaretçi.|
|*biriktirme*|Depolamadan serbest bırakmak için nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi çağırır `cache.deallocate(ptr, count)`, burada `cache` Cache nesnesini temsil eder.

## <a name="equals"></a>sync_none:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresinin önbellek nesnesi.|
|*Diğer*|Eşitlik için Karşılaştırılacak önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi her zaman **true**değerini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
