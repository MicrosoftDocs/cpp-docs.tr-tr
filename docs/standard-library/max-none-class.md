---
title: max_none Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
ms.openlocfilehash: 41ada338d9b8546202ecd49ff975f9642f190ba0
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560549"
---
# <a name="max_none-class"></a>max_none Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesini en fazla sıfır uzunluğuna sınırlayan bir [Max Class](../standard-library/allocators-header.md) nesnesi tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>Parametreler

*Biçimlendir*\
İçinde depolanacak en fazla öğe sayısını belirleyen Max sınıfı `freelist` .

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

## <a name="max_noneallocated"></a><a name="allocated"></a> max_none:: ayrılmış

Ayrılan bellek bloklarının sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

*_Nx*\
Artış değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Her başarılı çağrıdan sonra `cache_freelist::allocate` işlecine çağrılır **`new`** . Bağımsız değişken *_Nx* , öbek işleci tarafından ayrılan bellek bloklarının sayısıdır **`new`** .

## <a name="max_nonedeallocated"></a><a name="deallocated"></a> max_none::d eayrılmış

Ayrılan bellek bloklarının sayısını azaltır.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

*_Nx*\
Artış değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi hiçbir şey yapmaz. Bu üye işlevi, her çağrıdan sonra işlecine kadar çağrılır `cache_freelist::deallocate` **`delete`** . Bağımsız değişken *_Nx* , öbekte tarafından serbest bırakılmış bellek bloklarının sayısıdır **`delete`** .

## <a name="max_nonefull"></a><a name="full"></a> max_none:: Full

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlev her zaman döndürülür **`true`** .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından çağrılır `cache_freelist::deallocate` . Çağrı döndürürse **`true`** , `deallocate` bellek bloğunu ücretsiz listeye koyar; döndürürse **`false`** , `deallocate` **`delete`** bloğu serbest bırakmak için işleç çağırır.

## <a name="max_nonereleased"></a><a name="released"></a> max_none:: yayınlandı

, Ücretsiz listedeki bellek bloklarının sayısını azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. `released`Geçerli Max sınıfının üye işlevi, `cache_freelist::allocate` boş listeden bir bellek bloğunu her kaldırdığında tarafından çağrılır.

## <a name="max_nonesaved"></a><a name="saved"></a> max_none:: kaydedildi

Ücretsiz listedeki bellek bloklarının sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Bu, `cache_freelist::deallocate` her bir bellek bloğunu ücretsiz listeye yerleştirdiğinde çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
