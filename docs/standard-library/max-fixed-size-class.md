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
ms.openlocfilehash: 23aa10a3398c3f20de73eb2ac6fa1372efdc32e5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228212"
---
# <a name="max_fixed_size-class"></a>max_fixed_size Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesini sabit maksimum uzunlukla sınırlayan bir [Max Class](../standard-library/allocators-header.md) nesnesi tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Biçimlendir*|İçinde depolanacak en fazla öğe sayısını belirleyen Max sınıfı `freelist` .|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[max_fixed_size](#max_fixed_size)|Türünde bir nesne oluşturur `max_fixed_size` .|

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

## <a name="max_fixed_sizeallocated"></a><a name="allocated"></a>max_fixed_size:: ayrılmış

Ayrılan bellek bloklarının sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi hiçbir şey yapmaz. Bu üye işlevi, her başarılı çağrıdan sonra işlecine çağrılır `cache_freelist::allocate` **`new`** . Bağımsız değişken *_Nx* , öbek işleci tarafından ayrılan bellek bloklarının sayısıdır **`new`** .

## <a name="max_fixed_sizedeallocated"></a><a name="deallocated"></a>max_fixed_size::d eayrılmış

Ayrılan bellek bloklarının sayısını azaltır.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi hiçbir şey yapmaz. Bu üye işlevi, her çağrıdan sonra işlecine kadar çağrılır `cache_freelist::deallocate` **`delete`** . Bağımsız değişken *_Nx* , öbekte tarafından serbest bırakılmış bellek bloklarının sayısıdır **`delete`** .

## <a name="max_fixed_sizefull"></a><a name="full"></a>max_fixed_size:: Full

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** if `Max <= _Nblocks` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından çağrılır `cache_freelist::deallocate` . Çağrı döndürürse **`true`** , `deallocate` bellek bloğunu ücretsiz listeye koyar; false döndürürse `deallocate` **`delete`** blok serbest bırakmak için işleç çağırır.

## <a name="max_fixed_sizemax_fixed_size"></a><a name="max_fixed_size"></a>max_fixed_size:: max_fixed_size

Türünde bir nesne oluşturur `max_fixed_size` .

```cpp
max_fixed_size();
```

### <a name="remarks"></a>Açıklamalar

Bu Oluşturucu, depolanan değeri `_Nblocks` sıfır olarak başlatır.

## <a name="max_fixed_sizereleased"></a><a name="released"></a>max_fixed_size:: yayınlandı

, Ücretsiz listedeki bellek bloklarının sayısını azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Depolanan değeri azaltır `_Nblocks` . `released`Geçerli [Max sınıfının](../standard-library/allocators-header.md) üye işlevi, `cache_freelist::allocate` boş listeden bir bellek bloğunu her kaldırdığında tarafından çağrılır.

## <a name="max_fixed_sizesaved"></a><a name="saved"></a>max_fixed_size:: kaydedildi

Ücretsiz listedeki bellek bloklarının sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, depolanan değeri arttırır `_Nblocks` . Bu üye işlevi, `cache_freelist::deallocate` her bir bellek bloğunu ücretsiz listeye yerleştirdiğinde tarafından çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
