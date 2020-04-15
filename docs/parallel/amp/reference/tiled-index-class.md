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
ms.openlocfilehash: 46a6b3548526f0917c4e022a12bf859242e70b20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375475"
---
# <a name="tiled_index-class"></a>tiled_index Sınıfı

[tiled_extent](tiled-extent-class.md) bir nesneye dizin sağlar. Bu sınıfın, yerel döşeme kökenine ve genel kökene göre öğelere erişecek özellikleri vardır. Döşenmiş alanlar hakkında daha fazla bilgi için, [bkz.](../../../parallel/amp/using-tiles.md)

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
Bir sonraki en önemli boyutun uzunluğu.

*_Dim2*<br/>
En az önemli boyutun uzunluğu.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[tiled_index Yapıcı](#ctor)|`tile_index` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[get_tile_extent](#tiled_index__get_tile_extent)|Şablon bağımsız değişkenlerinin `_Dim0` `_Dim1`değerlerine `tiled_index` sahip bir [kapsam](extent-class.md) nesnesi verir ve `_Dim2`.|

### <a name="public-constants"></a>Genel Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[bariyer Sabiti](#tiled_index__barrier)|İş parçacıklarının geçerli döşemesinde bir engeli temsil eden [tile_barrier](tile-barrier-class.md) bir nesne depolar.|
|||
|[küresel Sabit](#tiled_index__global)|Bir ızgara nesnesinde genel dizini temsil eden sıralama 1, 2 veya 3 [dizin](index-class.md) nesnesini depolar.|
|[yerel Sabit](#tiled_index__local)|Bir `index` [tiled_extent](tiled-extent-class.md) nesnesinin geçerli döşemesinde göreli dizini temsil eden 1, 2 veya 3 rank nesnesini depolar.|
|[sıralama Sabit](#tiled_index__rank)|Nesnenin sıralamasını `tiled_index` depolar.|
|[kiremit Sabiti](#tiled_index__tile)|Bir `index` `tiled_extent` nesnenin geçerli döşemesinin koordinatlarını temsil eden 1, 2 veya 3 numaralı bir nesneyi depolar.|
|[tile_dim0 Sabiti](#tiled_index__tile_dim0)|En önemli boyutun uzunluğunu saklar.|
|[tile_dim1 Sabiti](#tiled_index__tile_dim1)|Bir sonrakien en önemli boyutun uzunluğunu depolar.|
|[tile_dim2 Sabiti](#tiled_index__tile_dim2)|En az önem eken boyutun uzunluğunu saklar.|
|[tile_origin Sabiti](#tiled_index__tile_origin)|Bir `index` nesnedeki geçerli döşemenin kaynağının genel koordinatlarını temsil eden 1, 2 `tiled_extent` veya 3 numaralı sıralamadaki bir nesneyi depolar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[tile_extent](#tile_extent)|Şablon bağımsız değişkenleri `tiled_index` `_Dim0`şablon bağımsız değişkenlerinin `_Dim1`değerlerine `_Dim2`sahip bir [kapsam](extent-class.md) nesnesi `tiled_index` alır ve .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp.h

**Ad alanı:** Eşzamanlılık

## <a name="tiled_index-constructor"></a><a name="ctor"></a>tiled_index Yapıcı

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
Yapılandırılan `tiled_index`küresel [indeks](index-class.md) .

*_Local*<br/>
İnşa edilenin yerel [indeksi](index-class.md)`tiled_index`

*_Tile*<br/>
Yapılandırılan çini [dizini](index-class.md)`tiled_index`

*_Tile_origin*<br/>
Yapılandırılan çini menşe [indeksi](index-class.md)`tiled_index`

*_Barrier*<br/>
Yapılandırılan `tiled_index` [tile_barrier](tile-barrier-class.md) nesnesi.

*_Other*<br/>
Yapılandırılan `tile_index` `tiled_index`nesne kopyalanacak.

### <a name="overloads"></a>Aşırı Yüklemeler

|||
|-|-|
|Adı|Açıklama|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Genel koordinatlarda kiremit dizini ve yerel koordinatlarda döşemedeki göreli konumundan `tile_index` sınıfın yeni bir örneğini başolarak karşılar. Ve `_Global` `_Tile_origin` parametreler hesaplanır.|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Belirtilen `tiled_index` nesneyi kopyalayarak `tile_index` sınıfın yeni bir örneğini başolarak adlandırır.|

## <a name="get_tile_extent"></a><a name="tiled_index__get_tile_extent"></a>get_tile_extent

Şablon bağımsız değişkenlerinin `_Dim0` `_Dim1`değerlerine `tiled_index` sahip bir [kapsam](extent-class.md) nesnesi verir ve `_Dim2`.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<rank> get_tile_extent()restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Şablon `extent` bağımsız değişkenlerinin `tiled_index` `_Dim0`değerlerine sahip `_Dim1`bir `_Dim2`nesne , ve .

## <a name="barrier"></a><a name="tiled_index__barrier"></a>Bariyer

İş parçacıklarının geçerli döşemesinde bir engeli temsil eden [tile_barrier](tile-barrier-class.md) bir nesne depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
const tile_barrier barrier;
```

## <a name="global"></a><a name="tiled_index__global"></a>Küresel

Bir nesnenin genel dizinini temsil eden sıralama 1, 2 veya 3 [dizin](index-class.md) nesnesini depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
const index<rank> global;
```

## <a name="local"></a><a name="tiled_index__local"></a>Yerel

[Bir tiled_extent](tiled-extent-class.md) nesnesinin geçerli döşemesinde göreli dizini temsil eden sıralama 1, 2 veya 3 [dizin](index-class.md) nesnesini depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
const index<rank> local;
```

## <a name="rank"></a><a name="tiled_index__rank"></a>Rütbe

Nesnenin sıralamasını `tiled_index` depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int rank = _Rank;
```

## <a name="tile"></a><a name="tiled_index__tile"></a>Karo

[bir tiled_extent](tiled-extent-class.md) nesnesinin geçerli döşemesinin koordinatlarını temsil eden sıralama 1, 2 veya 3'teki bir [dizin](index-class.md) nesnesini depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
const index<rank> tile;
```

## <a name="tile_dim0"></a><a name="tiled_index__tile_dim0"></a>tile_dim0

En önemli boyutun uzunluğunu saklar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tiled_index__tile_dim1"></a>tile_dim1

Bir sonrakien en önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tiled_index__tile_dim2"></a>tile_dim2

En az önem eken boyutun uzunluğunu saklar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_origin"></a><a name="tiled_index__tile_origin"></a>tile_origin

Geçerli döşemenin kaynağının küresel koordinatlarını temsil eden sıralama 1, 2 veya [3'teki](index-class.md) bir dizin nesnesini [tiled_extent](tiled-extent-class.md) bir nesne içinde saklar.

### <a name="syntax"></a>Sözdizimi

```cpp
const index<rank> tile_origin
```

## <a name="tile_extent"></a><a name="tile_extent"></a>tile_extent

Şablon bağımsız değişkenleri `tiled_index` `_Dim0`şablon bağımsız değişkenlerinin `_Dim1`değerlerine `_Dim2`sahip bir [kapsam](extent-class.md) nesnesi `tiled_index` alır ve .

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
