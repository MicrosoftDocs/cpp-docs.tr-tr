---
title: sync_per_Kapsayıcı Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 378451ac2643d62271fd9e7fa44706a84ee8bb83
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450282"
---
# <a name="syncpercontainer-class"></a>sync_per_Kapsayıcı Sınıfı

Her ayırıcı nesnesi için ayrı bir önbellek nesnesi sağlayan bir [eşitleme filtresi](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbelleğin türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)veya [cache_suballoc](../standard-library/cache-suballoc-class.md)olabilir.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[equals](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ayrıcılar >

**Ad alanı:** stdext

## <a name="equals"></a>sync_per_container:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresinin önbellek nesnesi.|
|*Diğer*|Eşitlik için Karşılaştırılacak önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Üye işlev her zaman **false**döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
