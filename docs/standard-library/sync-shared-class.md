---
title: sync_shared Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
ms.openlocfilehash: 029edea59f29534491232d5d99353ccb093447bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376531"
---
# <a name="sync_shared-class"></a>sync_shared Sınıfı

Tüm ayırıcılar tarafından paylaşılan bir önbellek nesnesine erişimi denetlemek için mutex kullanan bir [eşitleme filtresi](../standard-library/allocators-header.md) açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbellek türü. Bu [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)veya [cache_suballoc](../standard-library/cache-suballoc-class.md)olabilir.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[Ayırması](#deallocate)|Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.|
|[equals](#equals)|Eşitlik için iki önbellek karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="sync_sharedallocate"></a><a name="allocate"></a>sync_shared::allocate

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Dizideki ayrılacak öğe sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlev mutex kilitler, çağırır `cache.allocate(count)`, mutex kilidini ve önceki arama `cache.allocate(count)`sonucu döndürür . `cache`geçerli önbellek nesnesini temsil eder.

## <a name="sync_shareddeallocate"></a><a name="deallocate"></a>sync_shared::d

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

Bu üye işlev mutex `cache.deallocate(ptr, count)`kilitler, çağırır , önbellek nesnesini temsil eder `cache` ve sonra mutex kilidini açar.

## <a name="sync_sharedequals"></a><a name="equals"></a>sync_shared::eşittir

Eşitlik için iki önbellek karşılaştırır.

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbellek türü.|
|*Diğer*|Eşitlik için karşılaştırılması gereken önbellek.|

### <a name="return-value"></a>Dönüş Değeri

**true** sonucu `cache.equals(Other.cache)`, önbellek `cache` nesnesini temsil eden, **doğru**ise; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
