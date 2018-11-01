---
title: sync_per_Kapsayıcı Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 641595f663c382129a40ce503ebdb789f8042cf0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466826"
---
# <a name="syncpercontainer-class"></a>sync_per_Kapsayıcı Sınıfı

Açıklayan bir [eşitleme filtresi](../standard-library/allocators-header.md) her bir ayırıcı nesne için ayrı önbellek nesnesi sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbellek türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[equals](#equals)|Eşitlik için iki önbellekler karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="equals"></a>  sync_per_container::Equals

Eşitlik için iki önbellekler karşılaştırır.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresi önbellek nesnesi.|
|*Diğer*|Eşitlik için karşılaştırma için önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi her zaman döndürür **false**.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
