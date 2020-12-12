---
description: 'Hakkında daha fazla bilgi edinin: uint_2 sınıfı'
title: uint_2 Sınıfı
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::uint_2::set_xy
- amp_short_vectors/Concurrency::graphics::uint_2::y
- amp_short_vectors/Concurrency::graphics::uint_2::gr
- amp_short_vectors/Concurrency::graphics::uint_2::operator-
- amp_short_vectors/Concurrency::graphics::uint_2::get_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator-=
- amp_short_vectors/Concurrency::graphics::uint_2::r
- amp_short_vectors/Concurrency::graphics::uint_2::yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator--
- amp_short_vectors/Concurrency::graphics::uint_2::set_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator=
- amp_short_vectors/Concurrency::graphics::uint_2::set_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator+=
- amp_short_vectors/Concurrency::graphics::uint_2::get_y
- amp_short_vectors/Concurrency::graphics::uint_2::xy
- amp_short_vectors/Concurrency::graphics::uint_2::x
- amp_short_vectors/Concurrency::graphics::uint_2::get_xy
- amp_short_vectors/Concurrency::graphics::uint_2::set_y
- amp_short_vectors/Concurrency::graphics::uint_2
- amp_short_vectors/Concurrency::graphics::uint_2::operator*=
- amp_short_vectors/Concurrency::graphics::uint_2::get_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator/=
- amp_short_vectors/Concurrency::graphics::uint_2::g
- amp_short_vectors/Concurrency::graphics::uint_2::operator++
- amp_short_vectors/Concurrency::graphics::uint_2::rg
ms.assetid: 9fcc9129-72b1-4da7-9012-4d3be15f1c52
ms.openlocfilehash: 6cf10e10baad6cedb06cef4358feebb11e6ce076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325816"
---
# <a name="uint_2-class"></a>uint_2 Sınıfı

İki işaretsiz tamsayının kısa vektörünü temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class uint_2;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[uint_2 Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|uint_2:: get_x||
|uint_2:: get_xy||
|uint_2:: get_y||
|uint_2:: get_yx||
|uint_2:: ref_g_Method||
|uint_2:: ref_r_Method||
|uint_2:: ref_x_Method||
|uint_2:: ref_y_Method||
|uint_2:: set_x||
|uint_2:: set_xy||
|uint_2:: set_y||
|uint_2:: set_yx||

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|uint_2:: operator--||
|uint_2:: operator% =||
|uint_2:: operator&=||
|uint_2:: operator * =||
|uint_2:: operator/=||
|uint_2:: operator ^ =||
|uint_2:: operator&#124;=||
|uint_2:: operator ~||
|uint_2:: operator + +||
|uint_2:: operator + =||
|uint_2:: operator<\<=||
|uint_2:: operator =||
|uint_2:: operator-=||
|uint_2:: operator>>=||

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[Boyut sabiti](#uint_2__size)||

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|uint_2:: g||
|uint_2:: gr||
|uint_2:: r||
|uint_2:: RG||
|uint_2:: x||
|uint_2:: XY||
|uint_2:: y||
|uint_2:: yx||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`uint_2`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_short_vectors. h

**Ad alanı:** Eşzamanlılık:: grafik

## <a name="uint_2"></a><a name="ctor"></a> uint_2

Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.

```cpp
uint_2() restrict(amp,
    cpu);

uint_2(
    unsigned int _V0,
    unsigned int _V1) restrict(amp,
    cpu);

uint_2(
    unsigned int _V) restrict(amp,
    cpu);

uint_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
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

## <a name="size"></a><a name="uint_2__size"></a> boyutla

```cpp
static const int size = 2;
```

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
