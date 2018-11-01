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
ms.openlocfilehash: ba99d6ed3af34363bf88cde1a40e4bf37841cd8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555863"
---
# <a name="maxunbounded-class"></a>max_unbounded Sınıfı

Açıklar bir [sınıfı en fazla](../standard-library/allocators-header.md) maksimum uzunluğunu sınırlamaz nesne bir [freelist](../standard-library/freelist-class.md) nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
class max_unbounded
```

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

## <a name="allocated"></a>  max_unbounded::allocated

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

## <a name="deallocated"></a>  max_unbounded::deallocated

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

## <a name="full"></a>  max_unbounded::Full

Daha fazla bellek blokları serbest listeye eklenmesi gerekip gerekmediğini belirten bir değeri döndürür.

```cpp
bool full();
```

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi her zaman döndürür **false**.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağıran `cache_freelist::deallocate`. Çağrısında **true**, `deallocate` false döndürürse, bellek bloğu boş liste; koyar `deallocate` çağrıları işleci **Sil** ayırması için blok.

## <a name="released"></a>  max_unbounded::RELEASED

Boş liste bellek sayısı engeller azaltır.

```cpp
void released();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. `released` Geçerli max sınıfının üye işlevi çağrıldığında `cache_freelist::allocate` olduğunda, bir bellek bloğu boş listeden kaldırır.

## <a name="saved"></a>  max_unbounded::Saved

Boş listede bellek bloğu sayısını artırır.

```cpp
void saved();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlev hiçbir şey yapmaz. Tarafından çağrılır `cache_freelist::deallocate` zaman bunu koyar bir bellek bloğu boş liste.

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
