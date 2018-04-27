---
title: max_fixed_size sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d8f90b39c2675e4b3e219afada4a27dcd3ffb70e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="maxfixedsize-class"></a>max_fixed_size Sınıfı

Açıklayan bir [max sınıfı](../standard-library/allocators-header.md) sınırlar nesnesi bir [freelist](../standard-library/freelist-class.md) sabit uzunluk nesnesine.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Max`|Depolamak öğelerinin üst limiti belirler max sınıfı `freelist`.|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[max_fixed_size](#max_fixed_size)|Türünde bir nesne oluşturur `max_fixed_size`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ayrılmış](#allocated)|Ayrılmış bellek blokları sayısını artırır.|
|[Serbest bırakıldı](#deallocated)|Azaltır sayısı bellek blokları ayrılmış.|
|[tam](#full)|Daha fazla bellek blokları ücretsiz listesine eklenmesi gerekip gerekmediğini belirten bir değer döndürür.|
|[Yayımlanma tarihi](#released)|Boş listede bellek sayısı engeller azaltır.|
|[kaydedildi](#saved)|Bellek blokları ücretsiz listesinde sayısını artırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="allocated"></a>  max_fixed_size::allocated

Ayrılmış bellek blokları sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`_Nx`|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlevini hiçbir şey yapmaz. Bu üye işlev her başarılı çağrısı tarafından sonra çağrılır `cache_freelist::allocate` işleci `new`. Bağımsız değişken `_Nx` operatör tarafından ayrılan Öbek bellek bloğu sayısıdır `new`.

## <a name="deallocated"></a>  max_fixed_size::deallocated

Azaltır sayısı bellek blokları ayrılmış.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`_Nx`|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Üye işlevini hiçbir şey yapmaz. Her çağırdıktan sonra bu üye işlev çağrılır `cache_freelist::deallocate` işleci `delete`. Bağımsız değişken `_Nx` işleciyle serbest Öbek bellek bloğu sayısıdır `delete`.

## <a name="full"></a>  max_fixed_size::full

Daha fazla bellek blokları ücretsiz listesine eklenmesi gerekip gerekmediğini belirten bir değer döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

`true` varsa `Max <= _Nblocks`; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Bu üye fonksiyonu tarafından çağrılır `cache_freelist::deallocate`. Çağrı döndürmesi durumunda `true`, `deallocate` false değerini döndürürse, bellek bloğu boş liste; koyar `deallocate` çağrıları işleci `delete` ayırması için blok.

## <a name="max_fixed_size"></a>  max_fixed_size::max_fixed_size

Türünde bir nesne oluşturur `max_fixed_size`.

```cpp
max_fixed_size();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu, depolanan değer başlatır `_Nblocks` sıfır.

## <a name="released"></a>  max_fixed_size::released

Boş listede bellek sayısı engeller azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Azaltır depolanan değer `_Nblocks`. `released` Geçerli üye işlevi [max sınıfı](../standard-library/allocators-header.md) tarafından çağrılır `cache_freelist::allocate` olduğunda, bir bellek bloğu boş listeden kaldırır.

## <a name="saved"></a>  max_fixed_size::saved

Bellek blokları ücretsiz listesinde sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi depolanan değer artırır `_Nblocks`. Bu üye fonksiyonu tarafından çağrılır `cache_freelist::deallocate` zaman onu koyar bir bellek bloğu boş liste.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
