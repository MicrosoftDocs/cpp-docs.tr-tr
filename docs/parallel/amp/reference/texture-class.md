---
title: texture Sınıfı
ms.date: 11/04/2016
f1_keywords:
- texture
- AMP_GRAPHICS/texture
- AMP_GRAPHICS/concurrency::graphics::texture::texture
- AMP_GRAPHICS/concurrency::graphics::texture::copy_to
- AMP_GRAPHICS/concurrency::graphics::texture::data
- AMP_GRAPHICS/concurrency::graphics::texture::get
- AMP_GRAPHICS/concurrency::graphics::texture::get_associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::get_depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::get_row_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::set
- AMP_GRAPHICS/concurrency::graphics::texture::rank
- AMP_GRAPHICS/concurrency::graphics::texture::associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::row_pitch
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
ms.openlocfilehash: 675112e108f57ad5208899005865570491e0d055
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486602"
---
# <a name="texture-class"></a>texture Sınıfı

Bir doku bulunan veri olduğu bir `accelerator_view` uzantı etki alanında. Bu uzantı etki alanındaki her öğe için değişkenlerden oluşan bir koleksiyondur. Her değişken C++ primitif türüne karşı bir değer tutar ( `unsigned int`, `int`, `float`, `double`), skalar türü ( `norm`, veya `unorm`), ya da kısa vektör türü.

## <a name="syntax"></a>Sözdizimi

```
template <typename value_type,  int _Rank>
class texture;
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
|`scalar_type`|Skaler türler.|
|`value_type`|Değer türleri.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Doku Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `texture` sınıfı.|
|[~ texture yok Edicisi](#ctor)|Yok eder `texture` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[copy_to](#copy_to)|Kopya `texture` derin kopyalama yaparak hedefe nesne.|
|[Veri](#data)|Bir CPU işaretçisini bu dokunun ham verisine döndürür.|
|[get](#get)|Belirtilen dizindeki öğenin değerini döndürür.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Döndürür [accelerator_view](accelerator-view-class.md) diğer bir deyişle bu dokunun kopyalanacağı tercih edilen hedef.|
|[get_depth_pitch](#get_depth_pitch)|Hazırlama dokusundaki CPU'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını döndürür.|
|[get_row_pitch](#get_row_pitch)|Bir hazırlama dokusundaki CPU'da bir 3B veya 2B her satırı arasında bulunan bayt sayısını döndürür.|
|[set](#set)|Belirtilen dizindeki öğenin değerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator()](#operator_call)|Parametreler ile belirtilen öğe değeri döndürür.|
|[operator]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[operator=](#operator_eq)|Belirtilen kopyalar [doku](texture-class.md) buna nesne.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıra sabiti](#rank)|Boyut sayısını alır `texture` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[associated_accelerator_view](#associated_accelerator_view)|Alır [accelerator_view](accelerator-view-class.md) diğer bir deyişle bu dokunun kopyalanacağı tercih edilen hedef.|
|[depth_pitch](#depth_pitch)|CPU'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını alır.|
|[row_pitch](#row_pitch)|Bayt her satır arasında bulunan bir 3B veya 2B hazırlama dokusundaki CPU'da alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Texture_base`

`texture`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_graphics.h

**Namespace:** Concurrency::graphics

##  <a name="dtor"></a> ~ Doku

Yok eder `texture` nesne.

```
~texture() restrict(cpu);
```

##  <a name="associated_accelerator_view"></a> associated_accelerator_view

Alır [accelerator_view](accelerator-view-class.md) diğer bir deyişle bu dokunun kopyalanacağı tercih edilen hedef.

```
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

##  <a name="copy_to"></a> copy_to

Kopya `texture` derin kopyalama yaparak hedefe nesne.

```
void copy_to(texture& _Dest) const;
void copy_to(writeonly_texture_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Üstüne kopyalanacak nesne.

*_Dizin*<br/>
Dokunun boyut sayısı.

*value_type*<br/>
Dokudaki öğelerin türü.

##  <a name="data"></a> Veri

Bir CPU işaretçisini bu dokunun ham verisine döndürür.

```
void* data() restrict(cpu);

const void* data() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Doku öğesinin ham verisine bir işaretçi.

##  <a name="depth_pitch"></a> depth_pitch

CPU'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını alır.

```
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;
```

##  <a name="get"></a> Al

Belirtilen dizindeki öğenin değerini döndürür.

```
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizindeki öğenin değeri.

##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view

Bu dokunun kopyalanacağı tercih edilen hedef olan accelerator_view döndürür.

```
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

[Accelerator_view](accelerator-view-class.md) diğer bir deyişle bu dokunun kopyalanacağı tercih edilen hedef.

##  <a name="get_depth_pitch"></a> get_depth_pitch

Hazırlama dokusundaki CPU'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını döndürür.

```
unsigned int get_depth_pitch() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Hazırlama dokusundaki CPU'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını.

##  <a name="get_row_pitch"></a> get_row_pitch

2 boyutlu bir hazırlama dokusundaki her satır arasında veya 3 boyutlu bir hazırlama dokusundaki bir derinlik diliminin her satırı arasında bulunan bayt sayısını döndürür.

```
unsigned int get_row_pitch() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

2 boyutlu bir hazırlama dokusundaki her satır arasında veya 3 boyutlu bir hazırlama dokusundaki bir derinlik diliminin her satırı arasında bulunan bayt sayısı.

##  <a name="operator_call"></a> operator()

Parametreler ile belirtilen öğe değeri döndürür.

```
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

const value_type operator() (
    int _I0) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizini.

*_I0*<br/>
Dizinin en önemli bileşeni.

*_I1*<br/>
Dizinin sonraki-en-önemli bileşeni.

*_I2*<br/>
Dizinin en az önemli bileşeni.

*_Dizin*<br/>
Dizinin boyut sayısı.

### <a name="return-value"></a>Dönüş Değeri

Parametreler ile belirtilen öğe değeri.

##  <a name="operator_at"></a> operator]

Belirtilen dizindeki öğeyi döndürür.

```
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizini.

*_I0*<br/>
Dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizindeki öğe.

##  <a name="operator_eq"></a> işleç =

Belirtilen kopyalar [doku](texture-class.md) buna nesne.

```
texture& operator= (
    const texture& _Other);

texture& operator= (
    texture<value_type, _Rank>&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`texture` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `texture` nesne.

##  <a name="rank"></a> boyut sayısı

Boyut sayısını alır `texture` nesne.

```
static const int rank = _Rank;
```

##  <a name="row_pitch"></a> row_pitch

Bayt her satır arasında bulunan bir 3B veya 2B hazırlama dokusundaki CPU'da alır.

```
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;
```

##  <a name="set"></a> Ayarlayın

Belirtilen dizindeki öğenin değerini ayarlar.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Öğenin dizini.

*_Dizin*<br/>
Dizinin boyut sayısı.

*value*<br/>
Öğenin yeni değeri.

##  <a name="ctor"></a> Doku

Yeni bir örneğini başlatır `texture` sınıfı.

```
texture(const Concurrency::extent<_Rank>& _Ext) restrict(cpu);

texture(int _E0) restrict(cpu);

texture(int _E0, int _E1) restrict(cpu);

texture(int _E0, int _E1, int _E2) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    const Concurrency::extent<_Rank>& _Ext,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    int _E2,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    const Concurrency::extent<_Rank>& _Ext,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    int _E2,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu))  ;

texture(
    int _E0,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av)  ;

texture(
    int _E0,
    int _E1,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av)  ;

texture(
    int _E0,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    const texture& _Src,
    const Concurrency::accelerator_view& _Acc_view);

texture(
    texture&& _Other);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av);

texture(
    const texture& _Src);
```

### <a name="parameters"></a>Parametreler

*_Acc_view*<br/>
[Accelerator_view](accelerator-view-class.md) dokunun konumunu belirtir.

*_Av*<br/>
[Accelerator_view](accelerator-view-class.md) dokunun konumunu belirtir.

*_Associated_av*<br/>
Tercih edilen hedef belirten bir accelerator_view için bu dokuya veya buradan kopyalar.

*_Bits_per_scalar_element*<br/>
Temel alınan skalar tür Dokuların her skalar öğe başına bit sayısı. Genel olarak, desteklenen değer 8, 16, 32 ve 64 olan. 0 belirtilirse bit sayısını temel scalar_type ile aynıdır. 64 yalnızca çift tabanlı dokular için geçerlidir.

*_Ext*<br/>
Dokunun her boyutundaki kapsam.

*_E0*<br/>
Dokunun en önemli bileşeni.

*_E1*<br/>
Doku sonraki-en-önemli bileşeni.

*_E2*<br/>
Doku kapsamındaki en az önemli bileşeni.

*_Input_iterator*<br/>
Giriş yineleyicisinin türü.

*_Mipmap_levels*<br/>
Temel dokudaki mipmap düzeylerinin sayısı. 0 belirtilirse, dokudaki mipmap düzeyleri belirtilen uzantı için olası en küçük boyuta kadar çeşitli olacaktır.

*_Dizin*<br/>
Kapsamın boyut sayısı.

*_Source*<br/>
Ana arabellek için işaretçi.

*_Src*<br/>
Kopya dokusu oluşturmak için.

*_Src_byte_size*<br/>
Kaynak arabellekteki bayt sayısı.

*_Src_first*<br/>
Kaynak kapsayıcı içine bir başlangıç yineleyicisi.

*_Src_last*<br/>
Kaynak kapsayıcı içine bir bitiş yineleyicisi.

*_Diğer*<br/>
Başka bir veri kaynağı.

*_Dizin*<br/>
Bölümün boyut sayısı.

## <a name="see-also"></a>Ayrıca Bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
