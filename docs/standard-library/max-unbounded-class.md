---
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
ms.openlocfilehash: fbc4351297ab8a3cc90a2a77fa31c3b134f10eab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370987"
---
# <a name="max_unbounded-class"></a>max_unbounded Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesinin maksimum uzunluğunu sınırlamayan [bir max sınıf](../standard-library/allocators-header.md) nesnesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class max_unbounded
```

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

## <a name="max_unboundedallocated"></a><a name="allocated"></a>max_unbounded::tahsis

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

## <a name="max_unboundeddeallocated"></a><a name="deallocated"></a>max_unbounded::d tahsis edilmiş

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

## <a name="max_unboundedfull"></a><a name="full"></a>max_unbounded::tam

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer verir.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

Üye işlev her zaman **yanlış**döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev `cache_freelist::deallocate`tarafından çağrılır. Arama **doğru**döndürürse, `deallocate` bellek bloğunu boş listeye koyar; yanlış dönerse, `deallocate` bloğu bulmak için operatör **silme** çağırır.

## <a name="max_unboundedreleased"></a><a name="released"></a>max_unbounded::serbest bırakıldı

Boş listedeki bellek bloklarının sayısını erteler.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. Geçerli `released` max sınıfın üye işlevi, `cache_freelist::allocate` boş listeden bir bellek bloğunu kaldırdığında çağrılır.

## <a name="max_unboundedsaved"></a><a name="saved"></a>max_unbounded::kaydedildi

Boş listedeki bellek bloklarının sayısını da martılar.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. Boş listeye `cache_freelist::deallocate` bir bellek bloğu koyduğunda çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
