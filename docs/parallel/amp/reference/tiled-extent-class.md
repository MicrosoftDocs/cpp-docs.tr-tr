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
ms.openlocfilehash: e2248c770c7eedde59d1cb592f7d5d7c1bfbde9a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126428"
---
# <a name="tiled_extent-class"></a>tiled_extent Sınıfı

`tiled_extent` nesnesi, bir ile üç boyutun bir `extent` nesnesidir ve bu da kapsamı alt alanı bir, iki veya üç boyutlu kutucuklara ayırır.

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
Sonraki-en önemli boyutun uzunluğu.

*_Dim2*<br/>
En az önemli boyutun uzunluğu.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[tiled_extent Oluşturucusu](#ctor)|`tiled_extent` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|`_Dim0`, `_Dim1`ve `_Dim2``tiled_extent` şablon bağımsız değişkenlerinin değerlerini yakalayan bir `extent` nesnesi döndürür.|
|[lığında](#pad)|Ölçeği, kutucuk boyutlarına eşit olarak bölünebilen şekilde ayarlanmış yeni bir `tiled_extent` nesnesi döndürür.|
|[kesilemedi](#truncate)|Yeni bir `tiled_extent` nesnesini, kutucuk boyutları tarafından eşit olarak bölünebilen şekilde ayarlanmış şekilde döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Belirtilen `tiled_index` nesnesinin içeriğini buna kopyalar.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[tile_dim0 sabiti](#tile_dim0)|En önemli boyutun uzunluğunu depolar.|
|[tile_dim1 sabiti](#tile_dim1)|Sonraki-en önemli boyutun uzunluğunu depolar.|
|[tile_dim2 sabiti](#tile_dim2)|En az önemli boyutun uzunluğunu depolar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[tile_extent](#tile_extent)|`_Dim0`, `_Dim1`ve `_Dim2``tiled_extent` şablon bağımsız değişkenlerinin değerlerini yakalayan bir `extent` nesnesi alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`extent`

`tiled_extent`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="ctor"></a> tiled_extent Oluşturucusu

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
Kopyalanacak `extent` veya `tiled_extent` nesnesi.

## <a name="get_tile_extent"></a> get_tile_extent

`_Dim0`, `_Dim1`ve `_Dim2``tiled_extent` şablon bağımsız değişkenlerinin değerlerini yakalayan bir `extent` nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Bu `tiled_extent` örneğinin boyutlarını yakalayan bir `extent` nesnesi.

## <a name="pad"></a> paneli

Ölçeği, kutucuk boyutlarına eşit olarak bölünebilen şekilde ayarlanmış yeni bir `tiled_extent` nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
tiled_extent pad() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni `tiled_extent` nesnesi değere göre.
## <a name="truncate"></a> kes

Yeni bir `tiled_extent` nesnesini, kutucuk boyutları tarafından eşit olarak bölünebilen şekilde ayarlanmış şekilde döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
tiled_extent truncate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni bir `tiled_extent` nesnesini, kutucuk boyutları tarafından eşit olarak bölünebilen şekilde ayarlanmış şekilde döndürür.

## <a name="operator_eq"></a> işleç =

Belirtilen `tiled_index` nesnesinin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalamanın `tiled_index` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `tiled_index` örneğine bir başvuru.

## <a name="tile_dim0"></a> tile_dim0

En önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a> tile_dim1

Sonraki-en önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a> tile_dim2

En az önemli boyutun uzunluğunu depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"></a> tile_extent
  `_Dim0`, `_Dim1`ve `_Dim2``tiled_extent` şablon bağımsız değişkenlerinin değerlerini yakalayan bir `extent` nesnesi alır.

### <a name="syntax"></a>Sözdizimi

```cpp
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
