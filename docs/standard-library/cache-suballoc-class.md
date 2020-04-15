---
title: cache_suballoc Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: 55860a65fc77f834ed699f3a5114768b7efdde6f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366727"
---
# <a name="cache_suballoc-class"></a>cache_suballoc Sınıfı

Tek bir boyuttaki bellek bloklarını ayıran ve ayıran bir [blok ayırıcı](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sz*|Dizideki ayrılacak öğe sayısı.|

## <a name="remarks"></a>Açıklamalar

cache_suballoc sınıfı şablonu, ayrılmış bellek bloklarını, serbest liste boşolduğunda, `freelist<sizeof(Type), max_unbounded>` **işleç** yeni ile ayrılan daha büyük bir yığından bellek bloklarını kullanarak, ücretsiz bir listede depolar.

Her yığın `Sz * Nelts` kullanılabilir bellek baytları ve **işleç yeni** ve **işleç silmek** gerektiren verileri tutar. Ayrılan parçalar asla serbest bırakılmaz.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_suballoc](#cache_suballoc)|Türünde `cache_suballoc`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[Ayırması](#deallocate)|Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="cache_suballocallocate"></a><a name="allocate"></a>cache_suballoc::allocate

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

## <a name="cache_suballoccache_suballoc"></a><a name="cache_suballoc"></a>cache_suballoc:cache_suballoc

Türünde `cache_suballoc`bir nesne oluşturuyor.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cache_suballocdeallocate"></a><a name="deallocate"></a>cache_suballoc::deallocate

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
