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
ms.openlocfilehash: cea2f09837e5efc6969e4ab305d106b9c9728412
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447213"
---
# <a name="maxunbounded-class"></a>max_unbounded Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesinin maksimum uzunluğunu sınırlayan bir [Max Class](../standard-library/allocators-header.md) nesnesi tanımlar.

## <a name="syntax"></a>Sözdizimi

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

**Üst bilgi:** \<ayrıcılar >

**Ad alanı:** stdext

## <a name="allocated"></a>max_unbounded:: ayrılmış

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

## <a name="deallocated"></a>max_unbounded::d eayrılan

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

## <a name="full"></a>max_unbounded:: Full

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

Üye işlev her zaman **false**döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından `cache_freelist::deallocate`çağrılır. Çağrı **true**döndürürse, `deallocate` bellek bloğunu ücretsiz listeye koyar; yanlış döndürürse, `deallocate` blok serbest bırakmak için işleç **silme** yöntemini çağırır.

## <a name="released"></a>max_unbounded:: yayınlandı

, Ücretsiz listedeki bellek bloklarının sayısını azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Geçerli Max sınıfının `cache_freelist::allocate` üyeişlevi,boşlistedenbirbellekbloğunuher`released` kaldırdığında tarafından çağrılır.

## <a name="saved"></a>max_unbounded:: kaydedildi

Ücretsiz listedeki bellek bloklarının sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi hiçbir şey yapmaz. Bu, `cache_freelist::deallocate` her bir bellek bloğunu ücretsiz listeye yerleştirdiğinde çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
