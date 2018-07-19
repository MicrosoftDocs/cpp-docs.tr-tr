---
title: sync_shared sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fb9b61ec4d2abc6ae73b2ebed7571398857d517
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963465"
---
# <a name="syncshared-class"></a>sync_shared Sınıfı

Açıklayan bir [eşitleme filtresi](../standard-library/allocators-header.md) tüm ayırıcılar tarafından paylaşılan bir önbellek nesnesi erişimi bir mutex kullanan.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbellek türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|
|[equals](#equals)|Eşitlik için iki önbellekler karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="allocate"></a>  sync_shared::allocate

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

Üye işlev çağrıları mutex kilitler `cache.allocate(count)`karşılıklı dışlama kilidini açar ve önceki çağrı sonucunu döndürür `cache.allocate(count)`. `cache` Geçerli önbellek nesnesini temsil eder.

## <a name="deallocate"></a>  sync_shared::deallocate

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

Bu üye işlev çağrıları mutex kilitler `cache.deallocate(ptr, count)`burada `cache` önbellek nesnesini temsil eder ve ardından karşılıklı dışlama kilidini açar.

## <a name="equals"></a>  sync_shared::Equals

Eşitlik için iki önbellekler karşılaştırır.

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbellek türü.|
|*Diğer*|Eşitlik için karşılaştırma önbellek.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa sonucunu `cache.equals(Other.cache)`burada `cache` önbellek nesnesini temsil eder, olan **true**; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
