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
ms.openlocfilehash: 0d409928de4bf66bcc6d6dda3008131f87e790c3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460164"
---
# <a name="maxnone-class"></a>max_none Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesini en fazla sıfır uzunluğuna sınırlayan bir [Max Class](../standard-library/allocators-header.md) nesnesi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*en fazla*|İçinde depolanacak en fazla öğe sayısını belirleyen Max sınıfı `freelist`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ayrılabilir](#allocated)|Ayrılan bellek bloklarının sayısını artırır.|
|[iptal](#deallocated)|Ayrılan bellek bloklarının sayısını azaltır.|
|[tümünü](#full)|Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.|
|[yayımlanacak](#released)|, Ücretsiz listedeki bellek bloklarının sayısını azaltır.|
|[kaydedildiğini](#saved)|Ücretsiz listedeki bellek bloklarının sayısını artırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ayrıcılar >

**Ad alanı:** stdext

## <a name="allocated"></a>max_none:: ayrılmış

Ayrılan bellek bloklarının sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Her başarılı çağrıdan `cache_freelist::allocate` sonra **New**işlecine kadar çağrılır. *_Nx* bağımsız değişkeni, **New**işlecine göre ayrılan öbekteki bellek bloklarının sayısıdır.

## <a name="deallocated"></a>max_none::d eayrılan

Ayrılan bellek bloklarının sayısını azaltır.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi hiçbir şey yapmaz. Bu üye işlevi, her çağrıdan `cache_freelist::deallocate` sonra işleç **Delete**'e kadar çağrılır. *_Nx* bağımsız değişkeni, işleç **silme**tarafından serbest bırakılmış öbek içindeki bellek bloklarının sayısıdır.

## <a name="full"></a>max_none:: Full

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlev her zaman **true**değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından `cache_freelist::deallocate`çağrılır. Çağrı **true**döndürürse, `deallocate` bellek bloğunu ücretsiz listeye koyar; yanlış döndürürse, `deallocate` blok serbest bırakmak için işleç **silme** yöntemini çağırır.

## <a name="released"></a>max_none:: yayınlandı

, Ücretsiz listedeki bellek bloklarının sayısını azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Geçerli Max sınıfının `cache_freelist::allocate` üyeişlevi,boşlistedenbirbellekbloğunuher`released` kaldırdığında tarafından çağrılır.

## <a name="saved"></a>max_none:: kaydedildi

Ücretsiz listedeki bellek bloklarının sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Bu, `cache_freelist::deallocate` her bir bellek bloğunu ücretsiz listeye yerleştirdiğinde çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
