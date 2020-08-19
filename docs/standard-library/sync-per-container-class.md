---
title: sync_per_Kapsayıcı Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 51a88e6ec4eca693c652635e1574e3611d7217cd
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562109"
---
# <a name="sync_per_container-class"></a>sync_per_Kapsayıcı Sınıfı

Her ayırıcı nesnesi için ayrı bir önbellek nesnesi sağlayan bir [eşitleme filtresi](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Parametreler

*Önbellek*\
Eşitleme filtresiyle ilişkili önbelleğin türü. [`cache_chunklist`](../standard-library/cache-chunklist-class.md), [`cache_freelist`](../standard-library/cache-freelist-class.md) Veya olabilir [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[equals](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="sync_per_containerequals"></a><a name="equals"></a> sync_per_container:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

*Önbellek*\
Eşitleme filtresinin önbellek nesnesi.

*Farklı*\
Eşitlik için Karşılaştırılacak önbellek nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi her zaman döndürülür **`false`** .

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
