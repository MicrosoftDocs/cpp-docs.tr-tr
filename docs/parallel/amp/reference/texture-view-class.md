---
title: texture_view Sınıfı
ms.date: 11/04/2016
f1_keywords:
- texture_view
- AMP_GRAPHICS/texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_alpha
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_blue
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_green
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_red
- AMP_GRAPHICS/Concurrency::graphics::texture_view::get
- AMP_GRAPHICS/Concurrency::graphics::texture_view::sample
- AMP_GRAPHICS/Concurrency::graphics::texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::texture_view::value_type
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
ms.openlocfilehash: 6bf4b9666d746199cea92fa2bd52b691c67e4a5b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126362"
---
# <a name="texture_view-class"></a>texture_view Sınıfı

Bir dokuya okuma erişimi ve yazma erişimi sağlar. `texture_view` yalnızca değer türü `int`, `unsigned int`veya varsayılan 32-bit bpse olan `float` olan dokuları okumak için kullanılabilir. Diğer doku biçimlerini okumak için `texture_view<const value_type, _Rank>`kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename value_type,int _Rank>
class texture_view;

template<typename value_type, int _Rank>
class texture_view
   : public details::_Texture_base<value_type, _Rank>;

template<typename value_type, int _Rank>
class texture_view<const value_type, _Rank>
   : public details::_Texture_base<value_type, _Rank>;
```

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Doku topladaki öğelerin türü.

*_Rank*<br/>
`texture_view`derecesi.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`value_type`|Doku toplamalarda öğelerin türü.|
|`coordinates_type`|`texture_view`bir doku hücresi değerinin belirtmek için kullanılan koordinat türü — yani, `float`değer türü olan ilişkili dokuyla aynı dereceye sahip bir `short_vector`.|
|`gather_return_type`|Toplama işlemleri için kullanılan dönüş türü — diğer bir deyişle, örnek dört doku hücresi değerinin değerinden toplanan dört homojen renk bileşeni tutan 4 `short_vector` bir sıra.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[texture_view Oluşturucusu](#ctor)|Fazla Yüklendi. Bir `texture_view` örneği oluşturur.|
|[~ texture_view yok edici](#ctor)|`texture_view` örneğini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[gather_alpha](#gather_alpha)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texx 'in Alfa (w) bileşenlerini döndürür.|
|[gather_blue](#gather_blue)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texvert 'in mavi (z) bileşenlerini döndürür.|
|[gather_green](#gather_green)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texx 'in yeşil (y) bileşenlerini döndürür.|
|[gather_red](#gather_red)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texx 'in kırmızı (x) bileşenlerini döndürür.|
|[get](#get)|Fazla Yüklendi. Dizine göre öğe değerini alır.|
|[örnekli](#sample)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda ve ayrıntı düzeyinde dokuyu örnekler.|
|[set](#set)|Bir öğenin değerini dizine göre ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator ()](#operator_call)|Fazla Yüklendi. Dizine göre öğe değerini alır.|
|[işleç\[\]](#operator_at)|Fazla Yüklendi. Dizine göre öğe değerini alır.|
|[işleç =](#operator_eq)|Fazla Yüklendi. Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[value_type](#value_type)|`texture_view`öğelerinin değer türü.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Texture_base`

`texture_view`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** concurrency:: Graphics

## <a name="dtor"></a>~ texture_view

`texture_view` örneğini yok eder.

```cpp
~texture_view() restrict(amp, cpu);
```

## <a name="ctor"></a>texture_view

Bir `texture_view` örneği oluşturur.

```cpp
texture_view(// [1] constructor
    texture<value_type, _Rank>& _Src) restrict(amp);

texture_view(// [2] constructor
    texture<value_type, _Rank>& _Src,
    unsigned int _Mipmap_level = 0) restrict(cpu);

texture_view(// [3] constructor
    const texture<value_type, _Rank>& _Src) restrict(amp);

texture_view(// [4] constructor
    const texture<value_type, _Rank>& _Src,
    unsigned int _Most_detailed_mip,
    unsigned int _Mip_levels) restrict(cpu);

texture_view(// [5] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

texture_view(// [6] copy constructor
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);

texture_view(// [7] copy constructor
    const texture_view<const value_type, _Rank>& _Other,
    unsigned int _Most_detailed_mip,
    unsigned int _Mip_levels) restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Src*<br/>
[1, 2] Yazılabilir `texture_view` oluşturulduğu `texture` Oluşturucu.

[3, 4] Yazılabilir olmayan `texture_view` oluşturulan `texture` Oluşturucu.

*_Other*<br/>
[5] kaynak yazılabilir `texture_view`Oluşturucu kopyalayın.

[6, 7] Kopya Oluşturucu kaynak yazılabilir olmayan `texture_view`.

*_Mipmap_level*<br/>
Kaynak üzerinde bu yazılabilir `texture_view` bağlandığı `texture` belirli bir mipmap düzeyi. Varsayılan değer, en üst düzey (en ayrıntılı) MIP düzeyini temsil eden 0 ' dır.

*_Most_detailed_mip*<br/>
Görünüm için en üst düzey (en ayrıntılı) MIP düzeyi, belirtilen `texture_view` nesnesine göre.

*_Mip_levels*<br/>
`texture_view`üzerinden erişilebilen mipmap düzeylerinin sayısı.

## <a name="gather_red"></a>gather_red

Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texx 'in kırmızı (x) bileşenlerini döndürür.

```cpp
const gather_return_type gather_red(
    const sampler& _Sampler,
    const coordinates_type& _Coord) const restrict(amp);

template<
    address_mode _Address_mode = address_clamp
>
const gather_return_type gather_red(
    const coordinates_type& _Coord) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Address_mode*<br/>
`texture_view`örneklemek için kullanılacak adres modu. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
`texture_view`örneklemek için kullanılacak örnekleyici yapılandırması.

*_Coord*<br/>
Örneği alma koordinatları. Kesirli koordinat değerleri, örnek dokkarasına göre enterpolasyonu için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

4 örneklenmiş doku hücresi değerinin değerlerinin kırmızı (x) bileşenini içeren bir sıra 4 kısa vektör.

## <a name="gather_green"></a>gather_green

Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texx 'in yeşil (y) bileşenlerini döndürür.

```cpp
const gather_return_type gather_green(
    const sampler& _Sampler,
    const coordinates_type& _Coord) const restrict(amp);

template<
    address_mode _Address_mode = address_clamp
>
const gather_return_type gather_green(
    const coordinates_type& _Coord) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Address_mode*<br/>
`texture_view`örneklemek için kullanılacak adres modu. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
`texture_view`örneklemek için kullanılacak örnekleyici yapılandırması.

*_Coord*<br/>
Örneği alma koordinatları. Kesirli koordinat değerleri, örnek dokkarasına göre enterpolasyonu için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

4 örneklenmiş doku hücresi değerinin değerlerinin yeşil (y) bileşenini içeren 4. derece kısa vektör.

## <a name="gather_blue"></a>gather_blue

Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texvert 'in mavi (z) bileşenlerini döndürür.

```cpp
const gather_return_type gather_blue(
    const sampler& _Sampler,
    const coordinates_type& _Coord) const restrict(amp);

template<
    address_mode _Address_mode = address_clamp
>
const gather_return_type gather_blue(
    const coordinates_type& _Coord) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Address_mode*<br/>
`texture_view`örneklemek için kullanılacak adres modu. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
`texture_view`örneklemek için kullanılacak örnekleyici yapılandırması.

*_Coord*<br/>
Örneği alma koordinatları. Kesirli koordinat değerleri, örnek dokkarasına göre enterpolasyonu için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

4 örneklenmiş doku hücresi değerinin değerlerinin kırmızı (x) bileşenini içeren bir sıra 4 kısa vektör.

## <a name="gather_alpha"></a>gather_alpha

Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texx 'in Alfa (w) bileşenlerini döndürür.

```cpp
const gather_return_type gather_alpha(
    const sampler& _Sampler,
    const coordinates_type& _Coord) const restrict(amp);

template<
    address_mode _Address_mode = address_clamp
>
const gather_return_type gather_alpha(
    const coordinates_type& _Coord) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Address_mode*<br/>
`texture_view`örneklemek için kullanılacak adres modu. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
`texture_view`örneklemek için kullanılacak örnekleyici yapılandırması.

*_Coord*<br/>
Örneği alma koordinatları. Kesirli koordinat değerleri, örnek dokkarasına göre enterpolasyonu için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

4 örneklenmiş doku hücresi değerinin değerlerinin Alfa (w) bileşenini içeren bir sıra 4 kısa vektör.

## <a name="get"></a>Al

Belirtilen dizindeki öğenin değerini alır.

```cpp
const value_type get(
    const index<_Rank>& _Index) const restrict(amp);

value_type get(
    const index<_Rank>& _Index,
    unsigned int _Mip_level = 0) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Alınacak öğenin dizini, muhtemelen çok boyutlu.

*_Mip_level*<br/>
Değeri alması gereken mipmap düzeyi. Varsayılan 0 değeri en ayrıntılı mipmap düzeyini temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Öğenin değeri.

## <a name="operator_eq"></a>işleç =

Bu `texture_view` örneğine belirtilen `texture_view` aynı dokunun görünümünü atar.

```cpp
texture_view<value_type, _Rank>& operator= (// [1] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

texture_view<const value_type, _Rank>& operator= (// [2] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

texture_view<const value_type, _Rank>& operator= (// [3] copy constructor
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
[1, 2] Copy Oluşturucu yazılabilir bir `texture_view` nesnesi.

[3] kopya Oluşturucu yazılabilir olmayan bir `texture_view` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu `texture_view` örneğine bir başvuru.

## <a name="operator_at"></a>operator []

Dizine göre öğe değerini döndürür.

```cpp
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);

value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizin, muhtemelen çok boyutlu.

*_I0*<br/>
Tek boyutlu dizin.

### <a name="return-value"></a>Dönüş Değeri

`_Index`tarafından dizinlenen öğe değeri.

## <a name="operator_call"></a>operator ()

Dizine göre öğe değerini döndürür.

```cpp
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

const value_type operator() (
    int _I0) const restrict(amp);

const value_type operator() (
    int _I0,   int _I1) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp);

value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

value_type operator() (
    int _I0) const restrict(amp);

value_type operator() (
    int _I0,
    int _I1) const restrict(amp);

value_type operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizin, muhtemelen çok boyutlu.

*_I0*<br/>
Dizinin en önemli bileşeni.

*_I1*<br/>
Dizinin en çok önemli bir bileşeni.

*_I2*<br/>
Dizinin en az önemli bileşeni.

### <a name="return-value"></a>Dönüş Değeri

`_Index`tarafından dizinlenen öğe değeri.

## <a name="sample"></a>örnekli

Belirtilen örnekleme yapılandırmasını kullanarak belirtilen koordinatlarda ve ayrıntı düzeyinde dokuyu örnekler.

```cpp
value_type sample(
    const sampler& _Sampler,
    const coordinates_type& _Coord,
    float _Level_of_detail = 0.0f) const restrict(amp);

template<
    filter_mode _Filter_mode = filter_linear,
    address_mode _Address_mode = address_clamp
>
value_type sample(
    const coordinates_type& _Coord,
    float _Level_of_detail = 0.0f) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Filter_mode*<br/>
Texture_view örneklemek için kullanılacak filtre modu. Filtre modu, minimum ve mipmap filtreleri için aynıdır.

*_Address_mode*<br/>
Texture_view örneklemek için kullanılacak adres modu. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
Texture_view örneklemek için kullanılacak örnekleyici yapılandırması.

*_Coord*<br/>
Örneği alma koordinatları. Kesirli koordinat değerleri, doku hücresi değerinin değerleri arasında enterpolasyon için kullanılır.

*_Level_of_detail*<br/>
Değer, örneğine örnek olarak mipmap düzeyini belirtir. Kesirli değerler, iki mipmap düzeyi arasında enterpolaklik etmek için kullanılır. Varsayılan ayrıntı düzeyi 0 ' dır ve en ayrıntılı MIP düzeyini temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Enterpolasyonlu örnek değeri.

## <a name="set"></a>kurmak

Belirtilen dizindeki öğenin değerini belirtilen değere ayarlar.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Ayarlanacak öğenin dizini, muhtemelen çok boyutlu.

*value*<br/>
Öğesi ayarlanacak değer.

## <a name="value_type"></a>value_type

Texture_view öğelerinin değer türü.

```cpp
typedef typename const value_type value_type;
```

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
