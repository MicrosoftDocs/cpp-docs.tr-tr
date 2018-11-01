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
ms.openlocfilehash: 08510ecc3b7469e8f88a61dcb0df28541e170892
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666461"
---
# <a name="maxfixedsize-class"></a>max_fixed_size Sınıfı

Açıklar bir [sınıfı en fazla](../standard-library/allocators-header.md) sınırlayan nesne bir [freelist](../standard-library/freelist-class.md) nesne sabit en büyük uzunluğu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*en fazla*|Depolamak için öğelerin maksimum sayısını belirleyen max sınıfı `freelist`.|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[max_fixed_size](#max_fixed_size)|Türünde bir nesne oluşturur `max_fixed_size`.|

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

## <a name="allocated"></a>  max_fixed_size::allocated

Ayrılmış bellek bloğu sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir şey yapmaz. Her başarılı çağrı tarafından sonra bu üye işlevi çağrılan `cache_freelist::allocate` işleci **yeni**. Bağımsız değişken *_Nx* öbek işleci tarafından ayrılan bellek bloğu sayısı **yeni**.

## <a name="deallocated"></a>  max_fixed_size::deallocated

Azaltır, bellek bloğu sayısı tahsis edilir.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlev hiçbir şey yapmaz. Bu üye işlevi, her bir çağrı tarafından sonra çağrılan `cache_freelist::deallocate` işleci **Sil**. Bağımsız değişken *_Nx* işleci ile serbest Öbek bellek bloğu sayısı **Sil**.

## <a name="full"></a>  max_fixed_size::full

Daha fazla bellek blokları serbest listeye eklenmesi gerekip gerekmediğini belirten bir değeri döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `Max <= _Nblocks`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağıran `cache_freelist::deallocate`. Çağrısında **true**, `deallocate` false döndürürse, bellek bloğu boş liste; koyar `deallocate` çağrıları işleci **Sil** ayırması için blok.

## <a name="max_fixed_size"></a>  max_fixed_size::max_fixed_size

Türünde bir nesne oluşturur `max_fixed_size`.

```cpp
max_fixed_size();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu depolanan değeri başlatır `_Nblocks` sıfır.

## <a name="released"></a>  max_fixed_size::released

Boş liste bellek sayısı engeller azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Azaltır depolanan değeri `_Nblocks`. `released` Üye işlevi geçerli [sınıfı en fazla](../standard-library/allocators-header.md) tarafından çağrılır `cache_freelist::allocate` olduğunda, bir bellek bloğu boş listeden kaldırır.

## <a name="saved"></a>  max_fixed_size::saved

Boş listede bellek bloğu sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi depolanan değeri artırır `_Nblocks`. Bu üye işlevi çağıran `cache_freelist::deallocate` zaman bunu koyar bir bellek bloğu boş liste.

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
