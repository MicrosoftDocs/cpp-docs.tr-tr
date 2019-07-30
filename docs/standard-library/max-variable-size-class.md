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
ms.openlocfilehash: f8b3c61676f784bf9369c22b5db97d7b251f7ac6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447289"
---
# <a name="maxvariablesize-class"></a>max_variable_size Sınıfı

[Freelist](../standard-library/freelist-class.md) nesnesini ayrılan bellek bloklarının sayısıyla kabaca orantılı olan en büyük uzunluğa sınırlayan bir [Max Class](../standard-library/allocators-header.md) nesnesi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class max_variable_size
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[max_variable_size](#max_variable_size)|Türünde `max_variable_size`bir nesne oluşturur.|

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

## <a name="allocated"></a>max_variable_size:: ayrılmış

Ayrılan bellek bloklarının sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, saklı değere `_Nallocs` *_Nx* ekler. Bu üye işlevi, her başarılı çağrıdan `cache_freelist::allocate` sonra **New**işlecine kadar çağrılır. *_Nx* bağımsız değişkeni, **New**işlecine göre ayrılan öbekteki bellek bloklarının sayısıdır.

## <a name="deallocated"></a>max_variable_size::d eayrılan

Ayrılan bellek bloklarının sayısını azaltır.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi, saklı değerden `_Nallocs` *_Nx* 'i çıkartır. Bu üye işlevi, her çağrıdan `cache_freelist::deallocate` sonra işleç **Delete**'e kadar çağrılır. *_Nx* bağımsız değişkeni, işleç **silme**tarafından serbest bırakılmış öbek içindeki bellek bloklarının sayısıdır.

## <a name="full"></a>max_variable_size:: Full

Boş listeye daha fazla bellek bloğu eklenip eklenmeyeceğini belirten bir değer döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

ise`_Nallocs / 16 + 16 <= _Nblocks`true.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından `cache_freelist::deallocate`çağrılır. Çağrı **true**döndürürse, `deallocate` bellek bloğunu ücretsiz listeye koyar; yanlış döndürürse, `deallocate` blok serbest bırakmak için işleç **silme** yöntemini çağırır.

## <a name="max_variable_size"></a>max_variable_size::max_variable_size

Türünde `max_variable_size`bir nesne oluşturur.

```cpp
max_variable_size();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu, depolanan değerleri `_Nblocks` ve `_Nallocs` sıfıra başlatır.

## <a name="released"></a>max_variable_size:: yayınlandı

, Ücretsiz listedeki bellek bloklarının sayısını azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, depolanan değeri `_Nblocks`azaltır. Geçerli Max sınıfının `cache_freelist::allocate` üyeişlevi,boşlistedenbirbellekbloğunuher`released` kaldırdığında tarafından çağrılır.

## <a name="saved"></a>max_variable_size:: kaydedildi

Ücretsiz listedeki bellek bloklarının sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, depolanan değeri `_Nblocks`arttırır. Bu üye işlevi, her bir `cache_freelist::deallocate` bellek bloğunu ücretsiz listeye yerleştirdiğinde tarafından çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
