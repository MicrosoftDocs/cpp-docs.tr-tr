---
title: cache_freelist Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
ms.openlocfilehash: d757909d3e54fed35bf42b943b9f9740dffee115
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366745"
---
# <a name="cache_freelist-class"></a>cache_freelist Sınıfı

Tek bir boyuttaki bellek bloklarını ayıran ve ayıran bir [blok ayırıcı](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sz*|Dizideki ayrılacak öğe sayısı.|
|*Max*|Serbest listenin en büyük boyutunu temsil eden maksimum sınıf. Bu [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), veya [max_variable_size](../standard-library/max-variable-size-class.md)olabilir.|

## <a name="remarks"></a>Açıklamalar

cache_freelist sınıf şablonu boyutu *Sz*bellek blokları ücretsiz bir listesini tutar. Ücretsiz liste dolu olduğunda bellek blokları anlaşma operatör **silme** kullanır. Boş liste boş olduğunda, yeni bellek blokları ayırmak için **yeni işleç** kullanır. Serbest listenin maksimum boyutu Max parametresinde geçen *Max* sınıf max sınıfı tarafından belirlenir.

Her bellek bloğu kullanılabilir bellek *Sz* bayt ve **operatör yeni** ve operatör **silmek** gerektiren veri tutar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Cache_freelist](#cache_freelist)|Türünde `cache_freelist`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[Ayırması](#deallocate)|Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="cache_freelistallocate"></a><a name="allocate"></a>cache_freelist::allocate

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

## <a name="cache_freelistcache_freelist"></a><a name="cache_freelist"></a>cache_freelist:cache_freelist

Türünde `cache_freelist`bir nesne oluşturuyor.

```cpp
cache_freelist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cache_freelistdeallocate"></a><a name="deallocate"></a>cache_freelist::d

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

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
