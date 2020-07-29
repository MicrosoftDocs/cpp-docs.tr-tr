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
ms.openlocfilehash: f98b5698ff14349abf9300799f00c6d9121bcf65
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222270"
---
# <a name="max_variable_size-class"></a>max_variable_size Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesini ayrılan bellek bloklarının sayısıyla kabaca orantılı olan en büyük uzunluğa sınırlayan bir [Max Class](../standard-library/allocators-header.md) nesnesi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class max_variable_size
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[max_variable_size](#max_variable_size)|Türünde bir nesne oluşturur `max_variable_size` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ayrılabilir](#allocated)|Ayrılan bellek bloklarının sayısını artırır.|
|[iptal](#deallocated)|Ayrılan bellek bloklarının sayısını azaltır.|
|[tümünü](#full)|Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.|
|[yayımlanacak](#released)|, Ücretsiz listedeki bellek bloklarının sayısını azaltır.|
|[kaydedildiğini](#saved)|Ücretsiz listedeki bellek bloklarının sayısını artırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="max_variable_sizeallocated"></a><a name="allocated"></a>max_variable_size:: ayrılmış

Ayrılan bellek bloklarının sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, depolanan değere *_Nx* ekler `_Nallocs` . Bu üye işlevi, her başarılı çağrıdan sonra işlecine çağrılır `cache_freelist::allocate` **`new`** . Bağımsız değişken *_Nx* , öbek işleci tarafından ayrılan bellek bloklarının sayısıdır **`new`** .

## <a name="max_variable_sizedeallocated"></a><a name="deallocated"></a>max_variable_size::d eayrılmış

Ayrılan bellek bloklarının sayısını azaltır.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi *_Nx* depolanan değerden çıkartır `_Nallocs` . Bu üye işlevi, her çağrıdan sonra işlecine kadar çağrılır `cache_freelist::deallocate` **`delete`** . Bağımsız değişken *_Nx* , öbekte tarafından serbest bırakılmış bellek bloklarının sayısıdır **`delete`** .

## <a name="max_variable_sizefull"></a><a name="full"></a>max_variable_size:: Full

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Eğer `_Nallocs / 16 + 16 <= _Nblocks` .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından çağrılır `cache_freelist::deallocate` . Çağrı döndürürse **`true`** , `deallocate` bellek bloğunu ücretsiz listeye koyar; false döndürürse `deallocate` **`delete`** blok serbest bırakmak için işleç çağırır.

## <a name="max_variable_sizemax_variable_size"></a><a name="max_variable_size"></a>max_variable_size:: max_variable_size

Türünde bir nesne oluşturur `max_variable_size` .

```cpp
max_variable_size();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu, depolanan değerleri `_Nblocks` ve sıfıra başlatır `_Nallocs` .

## <a name="max_variable_sizereleased"></a><a name="released"></a>max_variable_size:: yayınlandı

, Ücretsiz listedeki bellek bloklarının sayısını azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, depolanan değeri azaltır `_Nblocks` . `released`Geçerli Max sınıfının üye işlevi, `cache_freelist::allocate` boş listeden bir bellek bloğunu her kaldırdığında tarafından çağrılır.

## <a name="max_variable_sizesaved"></a><a name="saved"></a>max_variable_size:: kaydedildi

Ücretsiz listedeki bellek bloklarının sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, depolanan değeri arttırır `_Nblocks` . Bu üye işlevi, `cache_freelist::deallocate` her bir bellek bloğunu ücretsiz listeye yerleştirdiğinde tarafından çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
