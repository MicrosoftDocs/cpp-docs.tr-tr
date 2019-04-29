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
ms.openlocfilehash: 0f2b627afa216f03592fe913afece1a80f5bd5a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351527"
---
# <a name="textureview-class"></a>texture_view Sınıfı

Okuma erişimi ve bir doku yazma erişimi sağlar. `texture_view` yalnızca değer türü olan dokuları okumak için kullanılabilir `int`, `unsigned int`, veya `float` varsayılan 32-bit bpse sahip. Diğer doku biçimlerini okumak için kullandığınız `texture_view<const value_type, _Rank>`.

## <a name="syntax"></a>Sözdizimi

```
template<typename value_type,int _Rank>
class texture_view;

template<typename value_type, int _Rank>
class texture_view
   : public details::_Texture_base<value_type, _Rank>;

template<typename value_type, int _Rank>
class texture_view<const value_type, _Rank>
   : public details::_Texture_base<value_type, _Rank>;
```

#### <a name="parameters"></a>Parametreler

*value_type*<br/>
Doku toplamındaki öğelerin türü.

*_Dizin*<br/>
Boyut sayısı `texture_view`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`value_type`|Doku Toplamlarındaki öğelerin türü.|
|`coordinates_type`|İçinde bir doku hücresini belirtmek için kullanılan koordinatın türü `texture_view`— diğer bir deyişle, bir `short_vector` değer türüne sahip olan ilişkili doku ile aynı dereceye sahip `float`.|
|`gather_return_type`|Toplama işlemleri için kullanılan dönüş türü — diğer bir deyişle, 4. derece `short_vector` dört homojen renk bileşenini içeren örneklenen dört görüntü doku hücresi değerlerinden toplanan.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[texture_view Oluşturucusu](#ctor)|Fazla Yüklendi. Oluşturur bir `texture_view` örneği.|
|[~ texture_view yok Edicisi](#ctor)|Yok eder `texture_view` örneği.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[gather_alpha](#gather_alpha)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texel'in alfa (w) bileşenlerini döndürür.|
|[gather_blue](#gather_blue)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texel'in mavi (z) bileşenlerini döndürür.|
|[gather_green](#gather_green)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texel'in yeşil (y) bileşenlerini döndürür.|
|[gather_red](#gather_red)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texel'in kırmızı (x) bileşenlerini döndürür.|
|[get](#get)|Fazla Yüklendi. Dizine göre öğe değerini alır.|
|[Örnek](#sample)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda ve ayrıntı düzeyinde dokuyu örnekler.|
|[set](#set)|Bir öğenin değerini dizine göre ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator()](#operator_call)|Fazla Yüklendi. Dizine göre öğe değerini alır.|
|[İşleci\[\]](#operator_at)|Fazla Yüklendi. Dizine göre öğe değerini alır.|
|[operator=](#operator_eq)|Fazla Yüklendi. Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[value_type](#value_type)|Öğelerinin değer türü `texture_view`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Texture_base`

`texture_view`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_graphics.h

**Namespace:** concurrency::graphics

##  <a name="dtor"></a> ~ texture_view

Yok eder `texture_view` örneği.

```
~texture_view() restrict(amp, cpu);
```

##  <a name="ctor"></a> texture_view

Oluşturur bir `texture_view` örneği.

```
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
[1, 2] Oluşturucu `texture` üzerine yazılabilir `texture_view` oluşturulur.

[3, 4] Oluşturucu `texture` üzerine yazılamaz `texture_view` oluşturulur.

*_Diğer*<br/>
[5] kopya Oluşturucu kaynağın yazılabilir `texture_view`.

[6, 7] Kopya kurucusu kaynağın yazılabilir olmayan `texture_view`.

*_Mipmap_level*<br/>
Kaynak öğesindeki belirli mipmap düzeyi `texture` , bu yazılabilir `texture_view` bağlar. Varsayılan değer, en üst düzey (en ayrıntılı) mip düzeyini temsil eden 0 ' dır.

*_Most_detailed_mip*<br/>
Üst düzey (en ayrıntılı) MIP düzeyini belirtilen göreli bir görünüm için `texture_view` nesne.

*_Mip_levels*<br/>
Erişilebilir mipmap düzeylerinin sayısını `texture_view`.

##  <a name="gather_red"></a> gather_red

Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texel'in kırmızı (x) bileşenlerini döndürür.

```
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
Kullanılacak adres modu örneği `texture_view`. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
Kullanılacak örnekleyici yapılandırması için örnek `texture_view`.

*_Coord*<br/>
Örneğin alındığı koordinatlar. Kesirli koordinat değerleri örnek texel'ler arasında enterpolasyon için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

4 kırmızı (x) bileşenini içeren 4. derece kısa vektör örnek doku hücresi değerinin örneklenir.

##  <a name="gather_green"></a> gather_green

Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texel'in yeşil (y) bileşenlerini döndürür.

```
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
Kullanılacak adres modu örneği `texture_view`. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
Kullanılacak örnekleyici yapılandırması için örnek `texture_view`.

*_Coord*<br/>
Örneğin alındığı koordinatlar. Kesirli koordinat değerleri örnek texel'ler arasında enterpolasyon için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

4 yeşil (y) bileşenini içeren 4. derece kısa vektör örnek doku hücresi değerinin örneklenir.

##  <a name="gather_blue"></a> gather_blue

Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texel'in mavi (z) bileşenlerini döndürür.

```
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
Kullanılacak adres modu örneği `texture_view`. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
Kullanılacak örnekleyici yapılandırması için örnek `texture_view`.

*_Coord*<br/>
Örneğin alındığı koordinatlar. Kesirli koordinat değerleri örnek texel'ler arasında enterpolasyon için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

4 kırmızı (x) bileşenini içeren 4. derece kısa vektör örnek doku hücresi değerinin örneklenir.

##  <a name="gather_alpha"></a> gather_alpha

Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda dokuyu örnekler ve örneklenen dört texel'in alfa (w) bileşenlerini döndürür.

```
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
Kullanılacak adres modu örneği `texture_view`. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
Kullanılacak örnekleyici yapılandırması için örnek `texture_view`.

*_Coord*<br/>
Örneğin alındığı koordinatlar. Kesirli koordinat değerleri örnek texel'ler arasında enterpolasyon için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

4. derece kısa vektör alfa (w bileşen 4 örnek doku hücresi değerinin örneklenen) içeren.

##  <a name="get"></a> Al

Belirtilen dizindeki öğenin değerini alır.

```
const value_type get(
    const index<_Rank>& _Index) const restrict(amp);

value_type get(
    const index<_Rank>& _Index,
    unsigned int _Mip_level = 0) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Büyük olasılıkla çok boyutlu alınacak öğenin dizini.

*_Mip_level*<br/>
İçinden değeri almamız mipmap düzeyi. Varsayılan değer 0 en ayrıntılı mipmap düzeyini temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Öğenin değeri.

##  <a name="operator_eq"></a> işleç =

Belirtilen aynı doku görünümü atar `texture_view` bu `texture_view` örneği.

```
texture_view<value_type, _Rank>& operator= (// [1] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

texture_view<const value_type, _Rank>& operator= (// [2] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

texture_view<const value_type, _Rank>& operator= (// [3] copy constructor
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
[1, 2] Yazılabilir bir kopya Oluşturucu `texture_view` nesne.

[3] kopya Oluşturucu yazılabilir olmayan bir `texture_view` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `texture_view` örneği.

##  <a name="operator_at"></a> operator]

Dizine göre öğe değerini döndürür.

```
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);

value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Büyük olasılıkla çok boyutlu dizin.

*_I0*<br/>
Tek boyutlu dizin.

### <a name="return-value"></a>Dönüş Değeri

Tarafından dizine eklenen öğe değeri `_Index`.

##  <a name="operator_call"></a> operator()

Dizine göre öğe değerini döndürür.

```
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
Büyük olasılıkla çok boyutlu dizin.

*_I0*<br/>
Dizinin en önemli bileşeni.

*_I1*<br/>
Dizinin sonraki-en-önemli bileşeni.

*_I2*<br/>
Dizinin en az önemli bileşeni.

### <a name="return-value"></a>Dönüş Değeri

Tarafından dizine eklenen öğe değeri `_Index`.

##  <a name="sample"></a> Örnek

Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarda ve ayrıntı düzeyinde dokuyu örnekler.

```
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
Texture_view örneklemek için kullanılacak filtre modu. Filtre modu küçültme, büyütme ve mipmap filtreleri için aynıdır.

*_Address_mode*<br/>
Texture_view örneklemek için kullanılacak adres modu. Adres modu tüm boyutlar için aynıdır.

*_Sampler*<br/>
Texture_view örneklemek için kullanılacak örnekleyici yapılandırması.

*_Coord*<br/>
Örneğin alındığı koordinatlar. Kesirli koordinat değerleri texel değerleri arasında enterpolasyon için kullanılır.

*_Level_of_detail*<br/>
Değer, örnekleme yapılacak mipmap düzeyini belirtir. Kesirli değerler iki mipmap düzeyi arasında enterpolasyon için kullanılır. Varsayılan ayrıntı düzeyi, en ayrıntılı mip düzeyini temsil eden 0 ' dır.

### <a name="return-value"></a>Dönüş Değeri

İlişkilendirilmiş örnek değer.

##  <a name="set"></a> Ayarlayın

Belirtilen değer için belirtilen dizindeki öğenin değerini ayarlar.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Büyük olasılıkla çok boyutlu ayarlanacak öğenin dizini.

*value*<br/>
Öğe ayarlanacak değer.

##  <a name="value_type"></a> value_type

Texture_view'un öğelerinin değer türü.

```
typedef typename const value_type value_type;
```

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
