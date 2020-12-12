---
description: 'Hakkında daha fazla bilgi edinin: writeonly_texture_view sınıfı'
title: writeonly_texture_view Sınıfı
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 17e9ed49c5fb3c976343d8c3ad8690d7f41b166d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314535"
---
# <a name="writeonly_texture_view-class"></a>writeonly_texture_view Sınıfı

Bir dokuya WriteOnly erişimi sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
```

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Dokudaki öğelerin türü.

*_Rank*<br/>
Dokunun derecesi.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`scalar_type`||
|`value_type`|Dokudaki öğelerin türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[writeonly_texture_view Oluşturucusu](#ctor)|`writeonly_texture_view` sınıfının yeni bir örneğini başlatır.|
|[~ writeonly_texture_view yok edici](#ctor)|Nesneyi yok eder `writeonly_texture_view` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[kurmak](#set)|Belirtilen dizindeki öğenin değerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Belirtilen `writeonly_texture_view` nesneyi buna kopyalar.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank)|Nesnenin derecesini alır `writeonly_texture_view` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** Eşzamanlılık:: grafik

## <a name="writeonly_texture_view"></a><a name="dtor"></a> ~ writeonly_texture_view

Nesneyi yok eder `writeonly_texture_view` .

```cpp
~writeonly_texture_view() restrict(amp,cpu);
```

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Belirtilen `writeonly_texture_view` nesneyi buna kopyalar.

```cpp
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
`writeonly_texture_view` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu nesneye bir başvuru `writeonly_texture_view` .

## <a name="rank"></a><a name="rank"></a> sırası

Nesnenin derecesini alır `writeonly_texture_view` .

```cpp
static const int rank = _Rank;
```

## <a name="set"></a><a name="set"></a> kurmak

Belirtilen dizindeki öğenin değerini ayarlar.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Öğenin dizini.

*değer*<br/>
Öğesinin yeni değeri.

## <a name="writeonly_texture_view"></a><a name="ctor"></a> writeonly_texture_view

`writeonly_texture_view` sınıfının yeni bir örneğini başlatır.

```cpp
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Dokunun derecesi.

*value_type*<br/>
Dokudaki öğelerin türü.

*_Src*<br/>
Oluşturmak için kullanılan doku `writeonly_texture_view` .

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
