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
ms.openlocfilehash: 9d295093031eaee0a2d4dd83aa931060e6eebc07
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832276"
---
# <a name="tiled_index-class"></a>tiled_index Sınıfı

[Tiled_extent](tiled-extent-class.md) nesnesine bir dizin sağlar. Bu sınıfın, yerel kutucuk kaynağına göre ve genel kaynağa göreli öğelere erişim özellikleri vardır. Döşeli boşluklar hakkında daha fazla bilgi için bkz. [kutucukları kullanma](../../../parallel/amp/using-tiles.md).

## <a name="syntax"></a>Söz dizimi

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
|[get_tile_extent](#tiled_index__get_tile_extent)|, [extent](extent-class.md) `tiled_index` Ve şablon bağımsız değişkenlerinin değerlerini içeren bir kapsam nesnesi döndürür `_Dim0` `_Dim1` `_Dim2` .|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[bariyer sabiti](#tiled_index__barrier)|Geçerli iş parçacığı kutucuğunda bir engel temsil eden [tile_barrier](tile-barrier-class.md) nesnesini depolar.|
|[Küresel sabit](#tiled_index__global)|Bir kılavuz nesnesindeki genel dizini temsil eden 1, 2 veya 3. derece bir [Dizin](index-class.md) nesnesi depolar.|
|[Yerel sabit](#tiled_index__local)|`index`Bir [tiled_extent](tiled-extent-class.md) nesnesinin geçerli kutucuğunda göreli dizini temsil eden 1, 2 veya 3 dereceli bir nesneyi depolar.|
|[sıralama sabiti](#tiled_index__rank)|Nesnenin derecesini depolar `tiled_index` .|
|[kutucuk sabiti](#tiled_index__tile)|`index`Bir nesnenin geçerli kutucuğunun koordinatlarını temsil eden 1, 2 veya 3 dereceli bir nesneyi depolar `tiled_extent` .|
|[tile_dim0 sabiti](#tiled_index__tile_dim0)|En önemli boyutun uzunluğunu depolar.|
|[tile_dim1 sabiti](#tiled_index__tile_dim1)|Sonraki-en önemli boyutun uzunluğunu depolar.|
|[tile_dim2 sabiti](#tiled_index__tile_dim2)|En az önemli boyutun uzunluğunu depolar.|
|[tile_origin sabiti](#tiled_index__tile_origin)|`index`Bir nesne içindeki geçerli kutucuğun kaynağının genel koordinatlarını temsil eden 1, 2 veya 3 dereceli bir nesneyi depolar `tiled_extent` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[tile_extent](#tile_extent)|[extent](extent-class.md) `tiled_index` Şablon bağımsız değişkenleri `tiled_index` şablon bağımsız değişkenlerinin, ve değerlerini içeren bir kapsam nesnesi alır `_Dim0` `_Dim1` `_Dim2` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Tiled_index_base`

`tiled_index`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="tiled_index-constructor"></a><a name="ctor"></a> tiled_index Oluşturucusu

`tiled_index` sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Söz dizimi

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
Oluşturulan genel [Dizin](index-class.md) `tiled_index` .

*_Local*<br/>
Oluşturulan [index](index-class.md)`tiled_index`

*_Tile*<br/>
Oluşturulan öğesinin döşeme [dizini](index-class.md)`tiled_index`

*_Tile_origin*<br/>
Oluşturulan öğesinin kutucuk kaynak [dizini](index-class.md)`tiled_index`

*_Barrier*<br/>
Oluşturulan [tile_barrier](tile-barrier-class.md) nesnesi `tiled_index` .

*_Other*<br/>
`tile_index`Oluşturulan öğesine kopyalanacak nesne `tiled_index` .

### <a name="overloads"></a>Aşırı Yüklemeler

|Ad|Açıklama|
|-|-|
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|`tile_index`Genel koordinatlardaki kutucuğun dizininden ve yerel koordinatlardaki kutucukta bulunan göreli konumda sınıfının yeni bir örneğini başlatır. `_Global`Ve `_Tile_origin` parametreleri hesaplanır.|
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|`tile_index`Belirtilen nesneyi kopyalayarak sınıfın yeni bir örneğini başlatır `tiled_index` .|

## <a name="get_tile_extent"></a><a name="tiled_index__get_tile_extent"></a> get_tile_extent

, [extent](extent-class.md) `tiled_index` Ve şablon bağımsız değişkenlerinin değerlerini içeren bir kapsam nesnesi döndürür `_Dim0` `_Dim1` `_Dim2` .

### <a name="syntax"></a>Syntax

```cpp
extent<rank> get_tile_extent()restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

, `extent` `tiled_index` Ve şablon bağımsız değişkenlerinin değerlerine sahip bir nesne `_Dim0` `_Dim1` `_Dim2` .

## <a name="barrier"></a><a name="tiled_index__barrier"></a> engeli

Geçerli iş parçacığı kutucuğunda bir engel temsil eden [tile_barrier](tile-barrier-class.md) nesnesini depolar.

### <a name="syntax"></a>Syntax

```cpp
const tile_barrier barrier;
```

## <a name="global"></a><a name="tiled_index__global"></a> Genel

Bir nesnenin genel dizinini temsil eden 1, 2 veya 3. sırada bir [Dizin](index-class.md) nesnesi depolar.

### <a name="syntax"></a>Syntax

```cpp
const index<rank> global;
```

## <a name="local"></a><a name="tiled_index__local"></a> Yerel

Bir [tiled_extent](tiled-extent-class.md) nesnesinin geçerli kutucuğunda göreli dizini temsil eden 1, 2 veya 3. derece bir [Dizin](index-class.md) nesnesi depolar.

### <a name="syntax"></a>Syntax

```cpp
const index<rank> local;
```

## <a name="rank"></a><a name="tiled_index__rank"></a> sırası

Nesnenin derecesini depolar `tiled_index` .

### <a name="syntax"></a>Syntax

```cpp
static const int rank = _Rank;
```

## <a name="tile"></a><a name="tiled_index__tile"></a> Kaldır

Bir [tiled_extent](tiled-extent-class.md) nesnesinin geçerli kutucuğunun koordinatlarını temsil eden 1, 2 veya 3. derece bir [Dizin](index-class.md) nesnesi depolar.

### <a name="syntax"></a>Syntax

```cpp
const index<rank> tile;
```

## <a name="tile_dim0"></a><a name="tiled_index__tile_dim0"></a> tile_dim0

En önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Syntax

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tiled_index__tile_dim1"></a> tile_dim1

Sonraki-en önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Syntax

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tiled_index__tile_dim2"></a> tile_dim2

En az önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Syntax

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_origin"></a><a name="tiled_index__tile_origin"></a> tile_origin

1, 2 veya 3 ' ün bir [Dizin](index-class.md) nesnesini, bir [tiled_extent](tiled-extent-class.md) nesnesi içindeki geçerli kutucuğun kaynağının genel koordinatlarını temsil eder.

### <a name="syntax"></a>Syntax

```cpp
const index<rank> tile_origin
```

## <a name="tile_extent"></a><a name="tile_extent"></a> tile_extent

[extent](extent-class.md) `tiled_index` Şablon bağımsız değişkenleri `tiled_index` şablon bağımsız değişkenlerinin, ve değerlerini içeren bir kapsam nesnesi alır `_Dim0` `_Dim1` `_Dim2` .

### <a name="syntax"></a>Syntax

```cpp
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
