---
title: tiled_extent Sınıfı
ms.date: 11/04/2016
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
ms.openlocfilehash: ce2710da1a745efedcd6e9e524355eda41e26de2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374704"
---
# <a name="tiled_extent-class"></a>tiled_extent Sınıfı

Nesne, `tiled_extent` uzayın kapsamını bir, iki veya üç boyutlu karolara bölen bir ila üç boyutlu bir `extent` nesnedir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    int _Dim0,
    int _Dim1,
    int _Dim2
>
class tiled_extent : public Concurrency::extent<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;

template <
    int _Dim0
>
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;
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
|[tiled_extent Yapıcı](#ctor)|`tiled_extent` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|`tiled_extent` Şablon bağımsız değişkenlerinin `_Dim0` `_Dim1`değerlerini yakalayan bir `_Dim2` `extent` nesne döndürür , ve .|
|[Pad](#pad)|Döşeme boyutları `tiled_extent` tarafından eşit bölünebilir olacak şekilde ayarlanmış ölçüde yeni bir nesne döndürür.|
|[Truncate](#truncate)|Döşeme boyutları `tiled_extent` tarafından eşit bölünebilir olacak şekilde ayarlanmış ölçüde yeni bir nesne döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[işleç=](#operator_eq)|Belirtilen `tiled_index` nesnenin içeriğini buna kopyalar.|

### <a name="public-constants"></a>Genel Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[tile_dim0 Sabiti](#tile_dim0)|En önemli boyutun uzunluğunu saklar.|
|[tile_dim1 Sabiti](#tile_dim1)|Bir sonrakien en önemli boyutun uzunluğunu depolar.|
|[tile_dim2 Sabiti](#tile_dim2)|En az önem eken boyutun uzunluğunu saklar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[tile_extent](#tile_extent)|`tiled_extent` Şablon bağımsız değişkenlerinin `_Dim0` `_Dim1`değerlerini yakalayan bir `_Dim2` `extent` nesne alır ve .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`extent`

`tiled_extent`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp.h

**Ad alanı:** Eşzamanlılık

## <a name="tiled_extent-constructor"></a><a name="ctor"> </a> tiled_extent Yapıcı

`tiled_extent` sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
`extent` Kopyalamaya `tiled_extent` veya nesneye.

## <a name="get_tile_extent"></a><a name="get_tile_extent"> </a> get_tile_extent

`tiled_extent` Şablon bağımsız değişkenlerinin `_Dim0` `_Dim1`değerlerini yakalayan bir `_Dim2` `extent` nesne döndürür , ve .

### <a name="syntax"></a>Sözdizimi

```cpp
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Bu `extent` `tiled_extent` örneğin boyutlarını yakalayan bir nesne.

## <a name="pad"></a><a name="pad"> </a> ped

Döşeme boyutları `tiled_extent` tarafından eşit bölünebilir olacak şekilde ayarlanmış ölçüde yeni bir nesne döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
tiled_extent pad() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni `tiled_extent` nesne, değere göre.

## <a name="truncate"></a><a name="truncate"> </a> budanma

Döşeme boyutları `tiled_extent` tarafından eşit bölünebilir olacak şekilde ayarlanmış ölçüde yeni bir nesne döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
tiled_extent truncate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Döşeme boyutları `tiled_extent` tarafından eşit bölünebilir olacak şekilde ayarlanmış ölçüde yeni bir nesne döndürür.

## <a name="operator"></a><a name="operator_eq"> </a> işleç=

Belirtilen `tiled_index` nesnenin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanması `tiled_index` gereken nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu `tiled_index` örneğin başvurusu.

## <a name="tile_dim0"></a><a name="tile_dim0"> </a> tile_dim0

En önemli boyutun uzunluğunu saklar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tile_dim1"> </a> tile_dim1

Bir sonrakien en önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tile_dim2"> </a> tile_dim2

En az önem eken boyutun uzunluğunu saklar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"></a><a name="tile_extent"> </a> tile_extent

`tiled_extent` Şablon bağımsız değişkenlerinin `_Dim0` `_Dim1`değerlerini yakalayan bir `_Dim2` `extent` nesne alır ve .

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
