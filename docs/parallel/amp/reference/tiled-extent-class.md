---
title: tiled_extent sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ffda10923d3be1baf7c9f6ed898480ee1c1367c3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067702"
---
# <a name="tiledextent-class"></a>tiled_extent Sınıfı

A `tiled_extent` nesnesi bir `extent` halidir bir, iki veya üç boyutlu kesen ve onun bir veya üç boyutta nesnesi.

### <a name="syntax"></a>Sözdizimi

```
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
Sonraki en-önemli boyutun uzunluğu.

*_Dim2*<br/>
En az önemli boyutun uzunluğu.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[tiled_extent Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `tiled_extent` sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|Döndürür bir `extent` değerlerini yakalayan bir nesne `tiled_extent` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.|
|[pad](#pad)|Yeni bir `tiled_extent` döşeme boyutları ile kalansız olacak şekilde yukarı nesne kapsamları ile ayarlandı.|
|[Kes](#truncate)|Yeni bir `tiled_extent` döşeme boyutları ile kalansız olacak şekilde aşağı kapsamları nesne ayarlanır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `tiled_index` bu nesne içine.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[tile_dim0 sabiti](#tile_dim0)|En önemli boyutun uzunluğunu saklar.|
|[tile_dim1 sabiti](#tile_dim1)|Sonraki en-önemli boyutun uzunluğunu saklar.|
|[tile_dim2 sabiti](#tile_dim2)|En az önemli boyutun uzunluğunu saklar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[tile_extent](#tile_extent)|Alır bir `extent` değerlerini yakalayan bir nesne `tiled_extent` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`extent`

`tiled_extent`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp.h

**Namespace:** eşzamanlılık

## <a name="ctor"> </a>  tiled_extent Oluşturucusu

Yeni bir örneğini başlatır `tiled_extent` sınıfı.

### <a name="syntax"></a>Sözdizimi

```
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`extent` Veya `tiled_extent` kopyalanacak nesne.

## <a name="get_tile_extent"> </a>  get_tile_extent

Döndürür bir `extent` değerlerini yakalayan bir nesne `tiled_extent` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.

### <a name="syntax"></a>Sözdizimi

```
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Bir `extent` bu boyutlarını yakalayan nesne `tiled_extent` örneği.

## <a name="pad"> </a>  paneli

Yeni bir `tiled_extent` döşeme boyutları ile kalansız olacak şekilde yukarı nesne kapsamları ile ayarlandı.

### <a name="syntax"></a>Sözdizimi

```
tiled_extent pad() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni `tiled_extent` değere göre bir nesne.
## <a name="truncate"> </a>  Kes

Yeni bir `tiled_extent` döşeme boyutları ile kalansız olacak şekilde aşağı kapsamları nesne ayarlanır.

### <a name="syntax"></a>Sözdizimi

```
tiled_extent truncate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni bir `tiled_extent` döşeme boyutları ile kalansız olacak şekilde aşağı kapsamları nesne ayarlanır.

## <a name="operator_eq"> </a>  işleç =

Belirtilen içeriğini kopyalar `tiled_index` bu nesne içine.

### <a name="syntax"></a>Sözdizimi

```
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`tiled_index` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `tiled_index` örneği.

## <a name="tile_dim0"> </a>  tile_dim0

En önemli boyutun uzunluğunu saklar.

### <a name="syntax"></a>Sözdizimi

```
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"> </a>  tile_dim1

Sonraki en-önemli boyutun uzunluğunu saklar.

### <a name="syntax"></a>Sözdizimi

```
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"> </a>  tile_dim2

En az önemli boyutun uzunluğunu saklar.

### <a name="syntax"></a>Sözdizimi

```
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"> </a>  tile_extent
  Alır bir `extent` değerlerini yakalayan bir nesne `tiled_extent` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.

### <a name="syntax"></a>Sözdizimi

```
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
