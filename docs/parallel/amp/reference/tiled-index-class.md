---
title: tiled_index Sınıfı
ms.date: 03/27/2019
f1_keywords:
- tiled_index
- AMP/tiled_index
- AMP/Concurrency::tiled_index::tiled_index
- AMP/Concurrency::tiled_index::get_tile_extent
- AMP/Concurrency::tiled_index::barrier
- AMP/Concurrency::tiled_index::global
- AMP/Concurrency::tiled_index::local
- AMP/Concurrency::tiled_index::rank
- AMP/Concurrency::tiled_index::tile
- AMP/Concurrency::tiled_index::tile_dim0
- AMP/Concurrency::tiled_index::tile_dim1
- AMP/Concurrency::tiled_index::tile_dim2
- AMP/Concurrency::tiled_index::tile_origin
- AMP/Concurrency::tiled_index::tile_extent
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
ms.openlocfilehash: eda01667a6b239284c682ba6ae3f9b857c713447
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142418"
---
# <a name="tiled_index-class"></a>tiled_index Sınıfı

[Tiled_extent](tiled-extent-class.md) nesnesine bir dizin sağlar. Bu sınıfın, yerel kutucuk kaynağına göre ve genel kaynağa göreli öğelere erişim özellikleri vardır. Döşeli boşluklar hakkında daha fazla bilgi için bkz. [kutucukları kullanma](../../../parallel/amp/using-tiles.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    int _Dim0,
    int _Dim1 = 0,
    int _Dim2 = 0
>
class tiled_index : public _Tiled_index_base<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;

template <
    int _Dim0
>
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;
```

### <a name="parameters"></a>Parametreler

*_Dim0*<br/>
En önemli boyutun uzunluğu.

*_Dim1*<br/>
Sonraki-en önemli boyutun uzunluğu.

*_Dim2*<br/>
En az önemli boyutun uzunluğu.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[tiled_index Oluşturucusu](#ctor)|`tile_index` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|`tiled_index` şablon bağımsız değişkenlerinin değerleri `_Dim0`, `_Dim1`ve `_Dim2`olan bir [kapsam](extent-class.md) nesnesi döndürür.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[bariyer sabiti](#tiled_index__barrier)|Geçerli iş parçacığı kutucuğunda bir engel temsil eden [tile_barrier](tile-barrier-class.md) nesnesini depolar.|
|||
|[Küresel sabit](#tiled_index__global)|Bir kılavuz nesnesindeki genel dizini temsil eden 1, 2 veya 3. derece bir [Dizin](index-class.md) nesnesi depolar.|
|[Yerel sabit](#tiled_index__local)|Bir [tiled_extent](tiled-extent-class.md) nesnesinin geçerli kutucuğunda göreli dizini temsil eden 1, 2 veya 3. derece `index` nesnesini depolar.|
|[sıralama sabiti](#tiled_index__rank)|`tiled_index` nesnesinin derecesini depolar.|
|[kutucuk sabiti](#tiled_index__tile)|Bir `tiled_extent` nesnesinin geçerli kutucuğunun koordinatlarını temsil eden 1, 2 veya 3. derece `index` nesnesini depolar.|
|[tile_dim0 sabiti](#tiled_index__tile_dim0)|En önemli boyutun uzunluğunu depolar.|
|[tile_dim1 sabiti](#tiled_index__tile_dim1)|Sonraki-en önemli boyutun uzunluğunu depolar.|
|[tile_dim2 sabiti](#tiled_index__tile_dim2)|En az önemli boyutun uzunluğunu depolar.|
|[tile_origin sabiti](#tiled_index__tile_origin)|Bir `tiled_extent` nesnesindeki geçerli kutucuğun kaynağının genel koordinatlarını temsil eden 1, 2 veya 3. derece `index` nesnesini depolar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[tile_extent](#tile_extent)|`tiled_index` şablon bağımsız değişkenlerinin değerlerini içeren bir [kapsam](extent-class.md) nesnesi alır `tiled_index` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`ve `_Dim2`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="ctor"></a>tiled_index Oluşturucusu

`tiled_index` sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
tiled_index(
    const index<rank>& _Global,
    const index<rank>& _Local,
    const index<rank>& _Tile,
    const index<rank>& _Tile_origin,
    const tile_barrier& _Barrier ) restrict(amp,cpu);

tiled_index(
    const tiled_index& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Global*<br/>
Oluşturulan `tiled_index`genel [dizini](index-class.md) .

*_Local*<br/>
Oluşturulan `tiled_index` yerel [dizini](index-class.md)

*_Tile*<br/>
Oluşturulan `tiled_index` döşeme [dizini](index-class.md)

*_Tile_origin*<br/>
Oluşturulan `tiled_index` kutucuk kaynak [dizini](index-class.md)

*_Barrier*<br/>
Oluşturulan `tiled_index`[tile_barrier](tile-barrier-class.md) nesnesi.

*_Other*<br/>
Oluşturulan `tiled_index`kopyalanacak `tile_index` nesnesi.

### <a name="overloads"></a>Aşırı Yüklemeler

|||
|-|-|
|Ad|Açıklama|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Genel koordinatlardaki kutucuğun dizininden ve yerel koordinatlardaki kutucukta bulunan göreli konumda `tile_index` sınıfının yeni bir örneğini başlatır. `_Global` ve `_Tile_origin` parametreleri hesaplanır.|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Belirtilen `tiled_index` nesnesini kopyalayarak `tile_index` sınıfının yeni bir örneğini başlatır.|

## <a name="tiled_index__get_tile_extent"></a>get_tile_extent

`tiled_index` şablon bağımsız değişkenlerinin değerleri `_Dim0`, `_Dim1`ve `_Dim2`olan bir [kapsam](extent-class.md) nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<rank> get_tile_extent()restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

`tiled_index` şablon bağımsız değişkenlerinin değerlerine sahip `extent` nesnesi `_Dim0`, `_Dim1`ve `_Dim2`.

## <a name="tiled_index__barrier"></a>engeli

Geçerli iş parçacığı kutucuğunda bir engel temsil eden [tile_barrier](tile-barrier-class.md) nesnesini depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
const tile_barrier barrier;
```

## <a name="tiled_index__global"></a>Genel

Bir nesnenin genel dizinini temsil eden 1, 2 veya 3. sırada bir [Dizin](index-class.md) nesnesi depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
const index<rank> global;
```

## <a name="tiled_index__local"></a>Yerel

Bir [tiled_extent](tiled-extent-class.md) nesnesinin geçerli kutucuğunda göreli dizini temsil eden 1, 2 veya 3. derece bir [Dizin](index-class.md) nesnesi depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
const index<rank> local;
```

## <a name="tiled_index__rank"></a>sırası

`tiled_index` nesnesinin derecesini depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int rank = _Rank;
```

## <a name="tiled_index__tile"></a>Kaldır

Bir [tiled_extent](tiled-extent-class.md) nesnesinin geçerli kutucuğunun koordinatlarını temsil eden 1, 2 veya 3. derece bir [Dizin](index-class.md) nesnesi depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
const index<rank> tile;
```

## <a name="tiled_index__tile_dim0"></a>tile_dim0

En önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tiled_index__tile_dim1"></a>tile_dim1

Sonraki-en önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tiled_index__tile_dim2"></a>tile_dim2

En az önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tiled_index__tile_origin"></a>tile_origin

1, 2 veya 3 ' ün bir [Dizin](index-class.md) nesnesini, bir [tiled_extent](tiled-extent-class.md) nesnesi içindeki geçerli kutucuğun kaynağının genel koordinatlarını temsil eder.

### <a name="syntax"></a>Sözdizimi

```cpp
const index<rank> tile_origin
```

## <a name="tile_extent"></a>tile_extent

`tiled_index` şablon bağımsız değişkenlerinin değerlerini içeren bir [kapsam](extent-class.md) nesnesi alır `tiled_index` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`ve `_Dim2`.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
