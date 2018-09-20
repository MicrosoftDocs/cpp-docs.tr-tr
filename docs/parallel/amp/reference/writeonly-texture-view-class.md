---
title: writeonly_texture_view sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
dev_langs:
- C++
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd92e403d9c83bf50bea2703cef6a4255c6245e3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414693"
---
# <a name="writeonlytextureview-class"></a>writeonly_texture_view Sınıfı

Bir dokuya salt yazılır erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```
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

#### <a name="parameters"></a>Parametreler

*value_type*<br/>
Dokudaki öğelerin türü.

*_Dizin*<br/>
Dokunun boyut sayısı.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`scalar_type`||
|`value_type`|Dokudaki öğelerin türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[writeonly_texture_view Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `writeonly_texture_view` sınıfı.|
|[~ writeonly_texture_view yok Edicisi](#ctor)|Yok eder `writeonly_texture_view` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[set](#set)|Belirtilen dizindeki öğenin değerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator=](#operator_eq)|Belirtilen kopyalar `writeonly_texture_view` buna nesne.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıra sabiti](#rank)|Boyut sayısını alır `writeonly_texture_view` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_graphics.h

**Namespace:** Concurrency::graphics

##  <a name="dtor"></a> ~ writeonly_texture_view

Yok eder `writeonly_texture_view` nesne.

```
~writeonly_texture_view() restrict(amp,cpu);
```

##  <a name="operator_eq"></a> işleç =

Belirtilen kopyalar `writeonly_texture_view` buna nesne.

```
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`writeonly_texture_view` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `writeonly_texture_view` nesne.

##  <a name="rank"></a> boyut sayısı

Boyut sayısını alır `writeonly_texture_view` nesne.

```
static const int rank = _Rank;
```

##  <a name="set"></a> Ayarlayın

Belirtilen dizindeki öğenin değerini ayarlar.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Öğenin dizini.

*value*<br/>
Öğenin yeni değeri.

##  <a name="ctor"></a> writeonly_texture_view

Yeni bir örneğini başlatır `writeonly_texture_view` sınıfı.

```
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Dizin*<br/>
Dokunun boyut sayısı.

*value_type*<br/>
Dokudaki öğelerin türü.

*_Src*<br/>
Oluşturmak için kullanılan doku `writeonly_texture_view`.

## <a name="see-also"></a>Ayrıca Bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
