---
title: sync_none sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e27611b077a6a1ea4715f20e6524f394af3b48f5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
|[Serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|
|[equals](#equals)|Eşitlik için iki önbellekleri karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="allocate"></a>  sync_none::allocate

Bir bellek bloğu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`count`|Ayrılacak dizideki öğelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `cache.allocate(count)`, burada `cache` önbellek nesnesidir.

## <a name="deallocate"></a>  sync_none::deallocate

Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Depolama biriminden bırakılmasına ilk nesne için bir işaretçi.|
|`count`|Depolama biriminden bırakılmasına nesnelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrılarını `cache.deallocate(ptr, count)`, burada `cache` önbellek nesnesini temsil eder.

## <a name="equals"></a>  sync_none::Equals

Eşitlik için iki önbellekleri karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Cache`|Eşitleme filtresi önbellek nesnesi.|
|`Other`|Eşitlik için karşılaştırmak için önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Üye işlev her zaman döndürür `true`.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
