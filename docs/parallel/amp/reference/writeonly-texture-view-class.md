---
title: writeonly_texture_view Sınıfı
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 8978a548ed246c59d7e7f007f1180685c7343a14
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126246"
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
|[~ writeonly_texture_view yok edici](#ctor)|`writeonly_texture_view` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[set](#set)|Belirtilen dizindeki öğenin değerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Belirtilen `writeonly_texture_view` nesnesini buna kopyalar.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank)|`writeonly_texture_view` nesnesinin derecesini alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** Eşzamanlılık:: grafik

## <a name="dtor"></a>~ writeonly_texture_view

`writeonly_texture_view` nesnesini yok eder.

```cpp
~writeonly_texture_view() restrict(amp,cpu);
```

## <a name="operator_eq"></a>işleç =

Belirtilen `writeonly_texture_view` nesnesini buna kopyalar.

```cpp
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
kopyalamanın `writeonly_texture_view` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu `writeonly_texture_view` nesnesine bir başvuru.

## <a name="rank"></a>sırası

`writeonly_texture_view` nesnesinin derecesini alır.

```cpp
static const int rank = _Rank;
```

## <a name="set"></a>kurmak

Belirtilen dizindeki öğenin değerini ayarlar.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Öğenin dizini.

*value*<br/>
Öğesinin yeni değeri.

## <a name="ctor"></a>writeonly_texture_view

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
`writeonly_texture_view`oluşturmak için kullanılan doku.

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
