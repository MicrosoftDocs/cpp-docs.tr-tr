---
description: 'Hakkında daha fazla bilgi edinin: max_unbounded sınıfı'
title: max_unbounded Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
ms.openlocfilehash: 64501d9028b5adba0f9e3059f3581ad57d00ea27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149246"
---
# <a name="max_unbounded-class"></a>max_unbounded Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesinin maksimum uzunluğunu sınırlayan bir [Max Class](../standard-library/allocators-header.md) nesnesi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class max_unbounded
```

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

## <a name="max_unboundedallocated"></a><a name="allocated"></a> max_unbounded:: ayrılmış

Ayrılan bellek bloklarının sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

*_Nx*\
Artış değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Her başarılı çağrıdan sonra `cache_freelist::allocate` işlecine çağrılır **`new`** . Bağımsız değişken *_Nx* , öbek işleci tarafından ayrılan bellek bloklarının sayısıdır **`new`** .

## <a name="max_unboundeddeallocated"></a><a name="deallocated"></a> max_unbounded::d eayrılmış

Ayrılan bellek bloklarının sayısını azaltır.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

*_Nx*\
Artış değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi hiçbir şey yapmaz. Bu üye işlevi, her çağrıdan sonra işlecine kadar çağrılır `cache_freelist::deallocate` **`delete`** . Bağımsız değişken *_Nx* , öbekte tarafından serbest bırakılmış bellek bloklarının sayısıdır **`delete`** .

## <a name="max_unboundedfull"></a><a name="full"></a> max_unbounded:: Full

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi her zaman döndürülür **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından çağrılır `cache_freelist::deallocate` . Çağrı döndürürse **`true`** , `deallocate` bellek bloğunu ücretsiz listeye koyar; false döndürürse `deallocate` **`delete`** blok serbest bırakmak için işleç çağırır.

## <a name="max_unboundedreleased"></a><a name="released"></a> max_unbounded:: yayınlandı

, Ücretsiz listedeki bellek bloklarının sayısını azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. `released`Geçerli Max sınıfının üye işlevi, `cache_freelist::allocate` boş listeden bir bellek bloğunu her kaldırdığında tarafından çağrılır.

## <a name="max_unboundedsaved"></a><a name="saved"></a> max_unbounded:: kaydedildi

Ücretsiz listedeki bellek bloklarının sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Bu, `cache_freelist::deallocate` her bir bellek bloğunu ücretsiz listeye yerleştirdiğinde çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
