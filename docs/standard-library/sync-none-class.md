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
ms.openlocfilehash: 046cbca30b6cdef2dc4e7dbbe2791d52384d9f25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376567"
---
# <a name="sync_none-class"></a>sync_none Sınıfı

Eşitleme olmayan bir [eşitleme filtresiaçıklar.](../standard-library/allocators-header.md)

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_none
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Cache`|Eşitleme filtresiyle ilişkili önbellek türü. Bu [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)veya [cache_suballoc](../standard-library/cache-suballoc-class.md)olabilir.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[Ayırması](#deallocate)|Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.|
|[equals](#equals)|Eşitlik için iki önbellek karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="sync_noneallocate"></a><a name="allocate"></a>sync_none::allocate

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Dizideki ayrılacak öğe sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlev `cache.allocate(count)`döndürür , önbellek nesnesi nerede. `cache`

## <a name="sync_nonedeallocate"></a><a name="deallocate"></a>sync_none::deallocate

Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ptr*|Depolamadan ayrılacak ilk nesneye işaretçi.|
|*Sayısı*|Depolamadan ayrılacak nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlev `cache.deallocate(ptr, count)`çağırır `cache` , önbellek nesnesini temsil eder.

## <a name="sync_noneequals"></a><a name="equals"></a>sync_none::eşittir

Eşitlik için iki önbellek karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresinin önbellek nesnesi.|
|*Diğer*|Eşitlik için karşılaştırılacak önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Üye işlev her zaman **doğru**döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
