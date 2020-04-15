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
ms.openlocfilehash: c49ceec72be62d8ff3125f04d97bbb6952501677
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370976"
---
# <a name="max_none-class"></a>max_none Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesini en fazla sıfır uzunluğuyla sınırlayan [bir max sınıf](../standard-library/allocators-header.md) nesnesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Max*|Depolamak için en fazla öğe sayısını belirleyen `freelist`maksimum sınıf.|

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

## <a name="max_noneallocated"></a><a name="allocated"></a>max_none::tahsis

Ayrılan bellek bloklarının sayısını artırım.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. Bu operatör `cache_freelist::allocate` **yeni**tarafından her başarılı aramadan sonra denir. _Nx *bağımsız* değişken, işleç **tarafından**ayrılan yığındaki bellek bloklarının sayısıdır.

## <a name="max_nonedeallocated"></a><a name="deallocated"></a>max_none::d tahsis edilmiş

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

## <a name="max_nonefull"></a><a name="full"></a>max_none::tam

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer verir.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlev her zaman **doğru**döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev `cache_freelist::deallocate`tarafından çağrılır. Arama **doğru**döndürürse, `deallocate` bellek bloğunu boş listeye koyar; **yanlış**dönerse, `deallocate` bloğu bulmak için operatör **silme** çağırır.

## <a name="max_nonereleased"></a><a name="released"></a>max_none::serbest bırakıldı

Boş listedeki bellek bloklarının sayısını erteler.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. Geçerli `released` max sınıfın üye işlevi, `cache_freelist::allocate` boş listeden bir bellek bloğunu kaldırdığında çağrılır.

## <a name="max_nonesaved"></a><a name="saved"></a>max_none::saved

Boş listedeki bellek bloklarının sayısını da martılar.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. Boş listeye `cache_freelist::deallocate` bir bellek bloğu koyduğunda çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
