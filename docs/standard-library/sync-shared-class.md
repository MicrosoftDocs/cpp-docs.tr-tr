---
description: 'Hakkında daha fazla bilgi edinin: sync_shared sınıfı'
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
ms.openlocfilehash: 4093b85ce6f10552cba462074aee2a448cc5ce3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183288"
---
# <a name="sync_shared-class"></a>sync_shared Sınıfı

Tüm ayırıcılar tarafından paylaşılan bir önbellek nesnesine erişimi denetlemek için bir mutex kullanan bir [eşitleme filtresi](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>Parametreler

*Önbellek*\
Eşitleme filtresiyle ilişkili önbelleğin türü. [`cache_chunklist`](../standard-library/cache-chunklist-class.md), [`cache_freelist`](../standard-library/cache-freelist-class.md) Veya olabilir [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[eşittir](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="sync_sharedallocate"></a><a name="allocate"></a> sync_shared:: ayır

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Ayrılacak dizideki öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi mutex 'i kilitler, çağırır, `cache.allocate(count)` mutex 'i kaldırır ve önceki çağrının sonucunu döndürür `cache.allocate(count)` . `cache` geçerli önbellek nesnesini temsil eder.

## <a name="sync_shareddeallocate"></a><a name="deallocate"></a> sync_shared::d eallocate

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

Bu üye işlevi, `cache.deallocate(ptr, count)` `cache` önbellek nesnesini temsil eden ve sonra mutex 'in kilidini eden mutex, çağrılarını kilitler.

## <a name="sync_sharedequals"></a><a name="equals"></a> sync_shared:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

*Önbellek*\
Eşitleme filtresiyle ilişkili önbelleğin türü.

*Farklı*\
Eşitlik için Karşılaştırılacak önbellek.

### <a name="return-value"></a>Dönüş Değeri

**`true`** sonucu ise `cache.equals(Other.cache)` , `cache` Cache nesnesini temsil eder **`true`** ; Aksi takdirde, olur **`false`** .

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
