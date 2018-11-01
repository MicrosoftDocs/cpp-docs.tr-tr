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
ms.openlocfilehash: a7fde40352a878575ddce8b48b4c97093ae7a960
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482881"
---
# <a name="maxvariablesize-class"></a>max_variable_size Sınıfı

Açıklar bir [sınıfı en fazla](../standard-library/allocators-header.md) sınırlayan nesne bir [freelist](../standard-library/freelist-class.md) ayrılan bellek blokları nesne sayısı için kabaca orantılı en büyük uzunluğu.

## <a name="syntax"></a>Sözdizimi

```cpp
class max_variable_size
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[max_variable_size](#max_variable_size)|Türünde bir nesne oluşturur `max_variable_size`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ayrılmış](#allocated)|Ayrılmış bellek bloğu sayısını artırır.|
|[Serbest bırakıldı](#deallocated)|Azaltır, bellek bloğu sayısı tahsis edilir.|
|[Tam](#full)|Daha fazla bellek blokları serbest listeye eklenmesi gerekip gerekmediğini belirten bir değeri döndürür.|
|[Yayımlanan](#released)|Boş liste bellek sayısı engeller azaltır.|
|[kaydedildi](#saved)|Boş listede bellek bloğu sayısını artırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="allocated"></a>  max_variable_size::allocated

Ayrılmış bellek bloğu sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi ekler *_Nx* depolanmış değere `_Nallocs`. Her başarılı çağrı tarafından sonra bu üye işlevi çağrılan `cache_freelist::allocate` işleci **yeni**. Bağımsız değişken *_Nx* öbek işleci tarafından ayrılan bellek bloğu sayısı **yeni**.

## <a name="deallocated"></a>  max_variable_size::deallocated

Azaltır, bellek bloğu sayısı tahsis edilir.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi çıkarır *_Nx* depolanmış değerden `_Nallocs`. Bu üye işlevi, her bir çağrı tarafından sonra çağrılan `cache_freelist::deallocate` işleci **Sil**. Bağımsız değişken *_Nx* işleci ile serbest Öbek bellek bloğu sayısı **Sil**.

## <a name="full"></a>  max_variable_size::Full

Daha fazla bellek blokları serbest listeye eklenmesi gerekip gerekmediğini belirten bir değeri döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `_Nallocs / 16 + 16 <= _Nblocks`.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağıran `cache_freelist::deallocate`. Çağrısında **true**, `deallocate` false döndürürse, bellek bloğu boş liste; koyar `deallocate` çağrıları işleci **Sil** ayırması için blok.

## <a name="max_variable_size"></a>  max_variable_size::max_variable_size

Türünde bir nesne oluşturur `max_variable_size`.

```cpp
max_variable_size();
```

### <a name="remarks"></a>Açıklamalar

Oluşturucu depolanmış değerleri başlatır `_Nblocks` ve `_Nallocs` sıfır.

## <a name="released"></a>  max_variable_size::RELEASED

Boş liste bellek sayısı engeller azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye, depolanan değeri azaltır işlev `_Nblocks`. `released` Geçerli max sınıfının üye işlevi çağrıldığında `cache_freelist::allocate` olduğunda, bir bellek bloğu boş listeden kaldırır.

## <a name="saved"></a>  max_variable_size::Saved

Boş listede bellek bloğu sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi depolanan değeri artırır `_Nblocks`. Bu üye işlevi çağıran `cache_freelist::deallocate` zaman bunu koyar bir bellek bloğu boş liste.

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
