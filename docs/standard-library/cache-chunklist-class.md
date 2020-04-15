---
title: cache_chunklist Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
ms.openlocfilehash: d0dd6176a34bd625069511106c491225d1467d08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366750"
---
# <a name="cache_chunklist-class"></a>cache_chunklist Sınıfı

Tek bir boyuttaki bellek bloklarını ayıran ve ayıran bir [blok ayırıcı](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sz*|Dizideki ayrılacak öğe sayısı.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, gerektiğinde bir bellek bloğu için depolama ayırmak için blokları alt ayırma, ham bellek parçaları ayırmak için **yeni işleç** kullanır; ayrılan bellek bloklarını her bir yığın için ayrı bir serbest listede saklar ve bellek bloklarından hiçbiri kullanılmadığında bir öbek bulmak için **işleç silme** kullanır.

Her bellek bloğu kullanılabilir bellek *Sz* bayt ve ait olduğu yığın için bir işaretçi tutar. Her yığın `Nelts` bellek blokları, üç işaretçi, bir int ve **işleç yeni** ve **operatör silmek** gerektiren verileri tutar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_chunklist](#cache_chunklist)|Türünde `cache_chunklist`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[Ayırması](#deallocate)|Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="cache_chunklistallocate"></a><a name="allocate"></a>cache_chunklist::allocate

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

## <a name="cache_chunklistcache_chunklist"></a><a name="cache_chunklist"></a>cache_chunklist:cache_chunklist

Türünde `cache_chunklist`bir nesne oluşturuyor.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cache_chunklistdeallocate"></a><a name="deallocate"></a>cache_chunklist::deallocate

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
