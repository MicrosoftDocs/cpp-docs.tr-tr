---
title: max_fixed_size Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
ms.openlocfilehash: 7f75dd71caa3cfcfec19264b1da62c6d47a3e01d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370999"
---
# <a name="max_fixed_size-class"></a>max_fixed_size Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesini sabit bir maksimum uzunluğa sınırlayan [bir max sınıf](../standard-library/allocators-header.md) nesnesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Max*|Depolamak için en fazla öğe sayısını belirleyen `freelist`maksimum sınıf.|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[max_fixed_size](#max_fixed_size)|Türünde `max_fixed_size`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Ayrılan](#allocated)|Ayrılan bellek bloklarının sayısını artırım.|
|[Kaldırıldı](#deallocated)|Ayrılan bellek bloklarının sayısını eriter.|
|[Tam](#full)|Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer verir.|
|[Yayım -lanan](#released)|Boş listedeki bellek bloklarının sayısını erteler.|
|[Kaydedilmiş](#saved)|Boş listedeki bellek bloklarının sayısını da martılar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="max_fixed_sizeallocated"></a><a name="allocated"></a>max_fixed_size::tahsis

Ayrılan bellek bloklarının sayısını artırım.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir şey yapmaz. Bu üye işlev, her başarılı `cache_freelist::allocate` aramadan sonra operatöre **yeni**olarak çağrılır. _Nx *bağımsız* değişken, işleç **tarafından**ayrılan yığındaki bellek bloklarının sayısıdır.

## <a name="max_fixed_sizedeallocated"></a><a name="deallocated"></a>max_fixed_size::d tahsis edilmiş

Ayrılan bellek bloklarının sayısını eriter.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir şey yapmaz. Bu üye işlev, operatör `cache_freelist::deallocate` **sililesin**tarafından her çağrıdan sonra çağrılır. _Nx *bağımsız* değişken, işleç **silme**tarafından ayrılan yığındaki bellek bloklarının sayısıdır.

## <a name="max_fixed_sizefull"></a><a name="full"></a>max_fixed_size::tam

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer verir.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** `Max <= _Nblocks`ise ; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev `cache_freelist::deallocate`tarafından çağrılır. Arama **doğru**döndürürse, `deallocate` bellek bloğunu boş listeye koyar; yanlış dönerse, `deallocate` bloğu bulmak için operatör **silme** çağırır.

## <a name="max_fixed_sizemax_fixed_size"></a><a name="max_fixed_size"></a>max_fixed_size:max_fixed_size

Türünde `max_fixed_size`bir nesne oluşturuyor.

```cpp
max_fixed_size();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu, depolanan değeri `_Nblocks` sıfıra indirir.

## <a name="max_fixed_sizereleased"></a><a name="released"></a>max_fixed_size::serbest bırakıldı

Boş listedeki bellek bloklarının sayısını erteler.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Depolanan değeri `_Nblocks`eriter. Geçerli `released` [max sınıfın](../standard-library/allocators-header.md) üye işlevi, `cache_freelist::allocate` boş listeden bir bellek bloğunu kaldırdığında çağrılır.

## <a name="max_fixed_sizesaved"></a><a name="saved"></a>max_fixed_size::kaydedildi

Boş listedeki bellek bloklarının sayısını da martılar.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev depolanan değeri `_Nblocks`artgetirir. Bu üye işlev, `cache_freelist::deallocate` boş listeye bir bellek bloğu koyduğunda çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
