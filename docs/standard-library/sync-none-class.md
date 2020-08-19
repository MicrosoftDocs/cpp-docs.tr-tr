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
ms.openlocfilehash: dac4dc1182de32af485d37a00ff96370ea8d8943
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562122"
---
# <a name="sync_none-class"></a>sync_none Sınıfı

Eşitleme sağlayan bir [eşitleme filtresi](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Cache>
class sync_none
```

### <a name="parameters"></a>Parametreler

`Cache`\
Eşitleme filtresiyle ilişkili önbelleğin türü. [`cache_chunklist`](../standard-library/cache-chunklist-class.md), [`cache_freelist`](../standard-library/cache-freelist-class.md) Veya olabilir [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[equals](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="sync_noneallocate"></a><a name="allocate"></a> sync_none:: ayır

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Ayrılacak dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döner `cache.allocate(count)` , burada `cache` Cache nesnesidir.

## <a name="sync_nonedeallocate"></a><a name="deallocate"></a> sync_none::d eallocate

Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Depolamadan serbest bırakmak için ilk nesneye yönelik bir işaretçi.

*biriktirme*\
Depolamadan serbest bırakmak için nesne sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi çağırır `cache.deallocate(ptr, count)` , burada `cache` Cache nesnesini temsil eder.

## <a name="sync_noneequals"></a><a name="equals"></a> sync_none:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

*Önbellek*\
Eşitleme filtresinin önbellek nesnesi.

*Farklı*\
Eşitlik için Karşılaştırılacak önbellek nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi her zaman döndürülür **`true`** .

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
