---
description: 'Hakkında daha fazla bilgi edinin: float_2 sınıfı'
title: float_2 Sınıfı
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::float_2::yx
- amp_short_vectors/Concurrency::graphics::float_2::operator-=
- amp_short_vectors/Concurrency::graphics::float_2::operator++
- amp_short_vectors/Concurrency::graphics::float_2::operator-
- amp_short_vectors/Concurrency::graphics::float_2::r
- amp_short_vectors/Concurrency::graphics::float_2::get_yx
- amp_short_vectors/Concurrency::graphics::float_2::get_xy
- amp_short_vectors/Concurrency::graphics::float_2::operator/=
- amp_short_vectors/Concurrency::graphics::float_2::set_yx
- amp_short_vectors/Concurrency::graphics::float_2::x
- amp_short_vectors/Concurrency::graphics::float_2::get_y
- amp_short_vectors/Concurrency::graphics::float_2::operator+=
- amp_short_vectors/Concurrency::graphics::float_2::gr
- amp_short_vectors/Concurrency::graphics::float_2::operator=
- amp_short_vectors/Concurrency::graphics::float_2::set_x
- amp_short_vectors/Concurrency::graphics::float_2::operator--
- amp_short_vectors/Concurrency::graphics::float_2::get_x
- amp_short_vectors/Concurrency::graphics::float_2::operator*=
- amp_short_vectors/Concurrency::graphics::float_2::rg
- amp_short_vectors/Concurrency::graphics::float_2::set_xy
- amp_short_vectors/Concurrency::graphics::float_2::xy
- amp_short_vectors/Concurrency::graphics::float_2
- amp_short_vectors/Concurrency::graphics::float_2::set_y
- amp_short_vectors/Concurrency::graphics::float_2::y
- amp_short_vectors/Concurrency::graphics::float_2::g
ms.assetid: b3ebd48e-f8c8-4f00-a640-357f702f0cae
ms.openlocfilehash: a0d350c9742da6c11a5bf982a1638a1fc0921eb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325856"
---
# <a name="float_2-class"></a>float_2 Sınıfı

İki yüzün kısa bir vektörünü temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class float_2;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[float_2 Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|float_2:: get_x||
|float_2:: get_xy||
|float_2:: get_y||
|float_2:: get_yx||
|float_2:: ref_g||
|float_2:: ref_r||
|float_2:: ref_x||
|float_2:: ref_y||
|float_2:: set_x||
|float_2:: set_xy||
|float_2:: set_y||
|float_2:: set_yx||

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|float_2:: operator-||
|float_2:: operator--||
|float_2:: operator * =||
|float_2:: operator/=||
|float_2:: operator + +||
|float_2:: operator + =||
|float_2:: operator =||
|float_2:: operator-=||

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[Boyut sabiti](#float_2__size)||

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|float_2:: g||
|float_2:: gr||
|float_2:: r||
|float_2:: RG||
|float_2:: x||
|float_2:: XY||
|float_2:: y||
|float_2:: yx||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`float_2`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_short_vectors. h

**Ad alanı:** Eşzamanlılık:: grafik

## <a name="float_2"></a><a name="ctor"></a> float_2

Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.

```cpp
float_2() restrict(amp,
    cpu);

float_2(
    float _V0,
    float _V1) restrict(amp,
    cpu);

float_2(
    float _V) restrict(amp,
    cpu);

float_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const double_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parametreler

*_V0*<br/>
0 öğesini başlatacak değer.

*_V1*<br/>
1 öğesini başlatacak değer.

*_V*<br/>
Başlatma değeri.

*_Other*<br/>
Başlatmak için kullanılan nesne.

## <a name="size"></a><a name="float_2__size"></a> boyutla

```cpp
static const int size = 2;
```

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
