---
title: max_variable_size Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
ms.openlocfilehash: 79e37d8c464a009e4a5196aeacc8d4a718e355b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370966"
---
# <a name="max_variable_size-class"></a>max_variable_size Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesini ayrılan bellek bloklarının sayısıyla kabaca orantılı olan en büyük uzunluğa sınırlayan [bir max sınıf](../standard-library/allocators-header.md) nesnesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class max_variable_size
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[max_variable_size](#max_variable_size)|Türünde `max_variable_size`bir nesne oluşturuyor.|

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

## <a name="max_variable_sizeallocated"></a><a name="allocated"></a>max_variable_size::tahsis

Ayrılan bellek bloklarının sayısını artırım.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye *_Nx* işlev depolanan değere `_Nallocs`_Nx ekler. Bu üye işlev, her başarılı `cache_freelist::allocate` aramadan sonra operatöre **yeni**olarak çağrılır. _Nx *bağımsız* değişken, işleç **tarafından**ayrılan yığındaki bellek bloklarının sayısıdır.

## <a name="max_variable_sizedeallocated"></a><a name="deallocated"></a>max_variable_size::d tahsis edilmiş

Ayrılan bellek bloklarının sayısını eriter.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlev depolanan *_Nx* değerden `_Nallocs`_Nx çıkarır. Bu üye işlev, operatör `cache_freelist::deallocate` **sililesin**tarafından her çağrıdan sonra çağrılır. _Nx *bağımsız* değişken, işleç **silme**tarafından ayrılan yığındaki bellek bloklarının sayısıdır.

## <a name="max_variable_sizefull"></a><a name="full"></a>max_variable_size::tam

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer verir.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** `_Nallocs / 16 + 16 <= _Nblocks`eğer .

### <a name="remarks"></a>Açıklamalar

Bu üye işlev `cache_freelist::deallocate`tarafından çağrılır. Arama **doğru**döndürürse, `deallocate` bellek bloğunu boş listeye koyar; yanlış dönerse, `deallocate` bloğu bulmak için operatör **silme** çağırır.

## <a name="max_variable_sizemax_variable_size"></a><a name="max_variable_size"></a>max_variable_size:max_variable_size

Türünde `max_variable_size`bir nesne oluşturuyor.

```cpp
max_variable_size();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu depolanan değerleri `_Nblocks` ve `_Nallocs` sıfıra başlanır.

## <a name="max_variable_sizereleased"></a><a name="released"></a>max_variable_size::serbest bırakıldı

Boş listedeki bellek bloklarının sayısını erteler.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev depolanan değeri `_Nblocks`üçer. Geçerli `released` max sınıfın üye işlevi, `cache_freelist::allocate` boş listeden bir bellek bloğunu kaldırdığında çağrılır.

## <a name="max_variable_sizesaved"></a><a name="saved"></a>max_variable_size::kaydedildi

Boş listedeki bellek bloklarının sayısını da martılar.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev depolanan değeri `_Nblocks`artgetirir. Bu üye işlev, `cache_freelist::deallocate` boş listeye bir bellek bloğu koyduğunda çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
