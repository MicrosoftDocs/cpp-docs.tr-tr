---
title: max_none sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44981141be5bfb4f18cb278e724ab905aebcc5cf
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964177"
---
# <a name="maxnone-class"></a>max_none Sınıfı

Açıklar bir [sınıfı en fazla](../standard-library/allocators-header.md) sınırlayan nesne bir [freelist](../standard-library/freelist-class.md) nesne en fazla uzunluğu sıfır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*en fazla*|Depolamak için öğelerin maksimum sayısını belirleyen max sınıfı `freelist`.|

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

## <a name="allocated"></a>  max_none::allocated

Ayrılmış bellek bloğu sayısını artırır.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Artış değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. Her başarılı çağrı tarafından sonra adlı `cache_freelist::allocate` işleci **yeni**. Bağımsız değişken *_Nx* öbek işleci tarafından ayrılan bellek bloğu sayısı **yeni**.

## <a name="deallocated"></a>  max_none::deallocated

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

## <a name="full"></a>  max_none::Full

Daha fazla bellek blokları serbest listeye eklenmesi gerekip gerekmediğini belirten bir değeri döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

Bu üye işlevi her zaman döndürür **true**.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağıran `cache_freelist::deallocate`. Çağrısında **true**, `deallocate` false döndürürse, bellek bloğu boş liste; koyar `deallocate` çağrıları işleci **Sil** ayırması için blok.

## <a name="released"></a>  max_none::RELEASED

Boş liste bellek sayısı engeller azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. `released` Geçerli max sınıfının üye işlevi çağrıldığında `cache_freelist::allocate` olduğunda, bir bellek bloğu boş listeden kaldırır.

## <a name="saved"></a>  max_none::Saved

Boş listede bellek bloğu sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. Tarafından çağrılır `cache_freelist::deallocate` zaman bunu koyar bir bellek bloğu boş liste.

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
