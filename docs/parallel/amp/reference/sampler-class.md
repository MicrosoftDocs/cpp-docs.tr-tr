---
title: sampler Sınıfı
ms.date: 06/28/2018
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
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
ms.openlocfilehash: 8f47bf6e9b88dba1e94e9e2ed2b93c8d2d3f9b8c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126363"
---
# <a name="sampler-class"></a>sampler Sınıfı

Örnekleyici sınıfı, doku örneklemesi için kullanılacak örnekleme yapılandırma bilgilerini toplar.

## <a name="syntax"></a>Sözdizimi

```cpp
class sampler;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[örnekleyici Oluşturucusu](#ctor)|Fazla Yüklendi. Bir örnekleyici örneği oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|Örnekleyici nesnesiyle ilişkili `address_mode` döndürür.|
|[get_border_color](#get_border_color)|Örnekleyici nesnesiyle ilişkili kenarlık rengini döndürür.|
|[get_filter_mode](#get_filter_mode)|Örnekleyici nesnesiyle ilişkili `filter_mode` döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Fazla Yüklendi. Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[address_mode](#address_mode)|`sampler` nesnesinin adres modunu alır.|
|[border_color](#border_color)|`sampler` nesnesinin kenarlık rengini alır.|
|[filter_mode](#filter_mode)|`sampler` nesnesinin filtre modunu alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`sampler`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** concurrency:: Graphics

## <a name="ctor"></a>'yi

[Örnekleyici sınıfının](sampler-class.md)bir örneğini oluşturur.

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
Örneklemede kullanılacak filtre modu.

*_Address_mode*<br/>
Tüm boyutlar için örnekleme içinde kullanılacak adresleme modu.

*_Border_color*<br/>
Adres modu address_border, kullanılacak kenarlık rengi. Varsayılan değer `float_4(0.0f, 0.0f, 0.0f, 0.0f)` şeklindedir.

*_Other*<br/>
[5] kopya Oluşturucu yeni `sampler` örneğine kopyalamak için `sampler` nesnesi.

[6] yeni `sampler` örneğine taşımak için oluşturucuyu `sampler` nesneyi taşıyın.

## <a name="address_mode"></a>address_mode

`sampler` nesnesinin adres modunu alır.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

## <a name="border_color"></a>border_color

`sampler` nesnesinin kenarlık rengini alır.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

## <a name="filter_mode"></a>filter_mode

`sampler` nesnesinin filtre modunu alır.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

## <a name="get_address_mode"></a>get_address_mode

Bu `sampler`için yapılandırılan filtre modunu döndürür.

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>Dönüş Değeri

Örnekleyici için yapılandırılmış adres modu.

## <a name="get_border_color"></a>get_border_color

Bu `sampler`için yapılandırılan kenarlık rengini döndürür.

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Kenarlık rengini içeren bir float_4.

## <a name="get_filter_mode"></a>get_filter_mode

Bu `sampler`için yapılandırılan filtre modunu döndürür.

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Örnekleyici için yapılandırılmış filtre modu.

## <a name="operator_eq"></a>işleç =

Başka bir örnekleyici nesnesinin değerini var olan bir örnekleyiciyi atar.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
[1] kopya atama Işleci bu `sampler`kopyalamak için `sampler` nesnesi.

[2] Bu `sampler`taşımak için atama Işlecini `sampler` nesnesini taşıyın.

### <a name="return-value"></a>Dönüş Değeri

Bu örnekleyici örneğine bir başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
