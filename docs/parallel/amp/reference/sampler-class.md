---
title: sampler sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee5d50976b6d91bff6d84ec288560ff1348c73d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424696"
---
# <a name="sampler-class"></a>sampler Sınıfı

Örnekleyici sınıfı, doku örnekleme için kullanılacak örnekleme yapılandırma bilgilerini toplar.

## <a name="syntax"></a>Sözdizimi

```cpp
class sampler;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[örnekleyici Oluşturucusu](#ctor)|Fazla Yüklendi. Örnekleyici örneği oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|Döndürür `address_mode` örnekleyici nesne ile ilişkili.|
|[get_border_color](#get_border_color)|Örnekleyici nesne ile ilişkili olan kenarlık rengi döndürür.|
|[get_filter_mode](#get_filter_mode)|Döndürür `filter_mode` örnekleyici nesne ile ilişkili.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator=](#operator_eq)|Fazla Yüklendi. Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[address_mode](#address_mode)|Adres modunu alır `sampler` nesne.|
|[border_color](#border_color)|Kenarlık rengini alır `sampler` nesne.|
|[filter_mode](#filter_mode)|Filtre modunu alır `sampler` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`sampler`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_graphics.h

**Namespace:** concurrency::graphics

##  <a name="ctor"></a> Örnekleyici

Örneği oluşturur [sampler sınıfı](sampler-class.md).

```cpp
sampler() restrict(cpu);    // [1] default constructor

sampler(                    // [2] constructor
    filter_mode _Filter_mode) restrict(cpu);

sampler(                    // [3] constructor
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [4] constructor
    filter_mode _Filter_mode,
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [5] copy constructor
    const sampler& _Other) restrict(amp,
    cpu);

sampler(                    // [6] move constructor
    sampler&& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parametreler

*_Filter_mode*<br/>
Örnekleme içinde kullanılacak filtre modu.

*_Address_mode*<br/>
Tüm boyutlar için örnekleme içinde kullanılacak adres modu.

*_Border_color*<br/>
Adres modu olduğunda address_border kullanılacak kenarlık rengi. Varsayılan değer `float_4(0.0f, 0.0f, 0.0f, 0.0f)` şeklindedir.

*_Diğer*<br/>
[5] kopya Oluşturucu `sampler` yeni içine Kopyalanacak nesnenin `sampler` örneği.

[6] taşıma Oluşturucu `sampler` yeni içine taşımak için nesne `sampler` örneği.

##  <a name="address_mode"></a> address_mode

Adres modunu alır `sampler` nesne.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

##  <a name="border_color"></a> border_color

Kenarlık rengini alır `sampler` nesne.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

##  <a name="filter_mode"></a> filter_mode

Filtre modunu alır `sampler` nesne.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

##  <a name="get_address_mode"></a> get_address_mode

Bunun için yapılandırılmış filtre modunu döndürür `sampler`.

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>Dönüş Değeri

Örnekleyici için yapılandırılmış adres modu.

##  <a name="get_border_color"></a> get_border_color

Bunun için yapılandırılmış kenarlık rengi döndürür `sampler`.

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Kenarlık rengi içeren float_4.

##  <a name="get_filter_mode"></a> get_filter_mode

Bunun için yapılandırılmış filtre modunu döndürür `sampler`.

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Örnekleyici için yapılandırılmış filtre modu.

##  <a name="operator_eq"></a> işleç =

Mevcut bir örnekleyici için başka bir örnekleyici nesne değeri atar.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
[1] kopya atama işleci `sampler` bunun kopyalamak için nesne `sampler`.

[2] taşıma atama işlecini `sampler` bu taşımak için nesnenin `sampler`.

### <a name="return-value"></a>Dönüş Değeri

Bu örnekleyici örneğine başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
