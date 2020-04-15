---
title: sync_per_Kapsayıcı Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 2c60911b5469cbf74944c9f63af44f2351790280
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376559"
---
# <a name="sync_per_container-class"></a>sync_per_Kapsayıcı Sınıfı

Her ayırıcı nesne için ayrı bir önbellek nesnesi sağlayan bir [eşitleme filtresi](../standard-library/allocators-header.md) açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbellek türü. Bu [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)veya [cache_suballoc](../standard-library/cache-suballoc-class.md)olabilir.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[equals](#equals)|Eşitlik için iki önbellek karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="sync_per_containerequals"></a><a name="equals"></a>sync_per_container::eşittir

Eşitlik için iki önbellek karşılaştırır.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresinin önbellek nesnesi.|
|*Diğer*|Eşitlik için karşılaştırılacak önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Üye işlev her zaman **yanlış**döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
