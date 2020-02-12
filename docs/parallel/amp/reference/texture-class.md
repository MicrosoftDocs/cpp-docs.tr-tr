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
ms.openlocfilehash: f7a38c84c5def629c7a42b2c05bf1ed04441593b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127783"
---
# <a name="texture-class"></a>texture Sınıfı

Doku, kapsam etki alanındaki bir `accelerator_view` veri toplamasının toplamıdır. Bir uzantı etki alanındaki her öğe için bir değişken koleksiyonudur. Her değişken, ilkel tür (`unsigned int`C++ , `int`, `float`, `double`), skaler bir tür (`norm`veya `unorm`) veya kısa bir vektör türü için karşılık gelen bir değer barındırır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename value_type,  int _Rank>
class texture;
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
|`scalar_type`|Skalar türler.|
|`value_type`|Değer türleri.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[doku Oluşturucusu](#ctor)|`texture` sınıfının yeni bir örneğini başlatır.|
|[~ doku yıkıcısı](#ctor)|`texture` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[copy_to](#copy_to)|Derin bir kopya yaparak `texture` nesnesini hedefe kopyalar.|
|[verileri](#data)|Bu dokunun ham verilerine bir CPU işaretçisi döndürür.|
|[get](#get)|Belirtilen dizindeki öğenin değerini döndürür.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Bu dokunun kopyalanacağı tercih edilen hedef olan [accelerator_view](accelerator-view-class.md) döndürür.|
|[get_depth_pitch](#get_depth_pitch)|CPU 'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını döndürür.|
|[get_row_pitch](#get_row_pitch)|CPU 'da 2B veya 3B hazırlama dokusundaki her satır arasında bulunan bayt sayısını döndürür.|
|[set](#set)|Belirtilen dizindeki öğenin değerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator ()](#operator_call)|Parametreler tarafından belirtilen öğe değerini döndürür.|
|[işleç\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[işleç =](#operator_eq)|Belirtilen [doku](texture-class.md) nesnesini buna kopyalar.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank)|`texture` nesnesinin derecesini alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[associated_accelerator_view](#associated_accelerator_view)|Bu dokunun kopyalanacağı tercih edilen hedef olan [accelerator_view](accelerator-view-class.md) alır.|
|[depth_pitch](#depth_pitch)|CPU 'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını alır.|
|[row_pitch](#row_pitch)|CPU 'da 2B veya 3B hazırlama dokusundaki her satır arasında bulunan bayt sayısını alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Texture_base`

`texture`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** Eşzamanlılık:: grafik

## <a name="dtor"></a>~ doku

`texture` nesnesini yok eder.

```cpp
~texture() restrict(cpu);
```

## <a name="associated_accelerator_view"></a>associated_accelerator_view

Bu dokunun kopyalanacağı tercih edilen hedef olan [accelerator_view](accelerator-view-class.md) alır.

```cpp
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

## <a name="copy_to"></a>copy_to

Derin bir kopya yaparak `texture` nesnesini hedefe kopyalar.

```cpp
void copy_to(texture& _Dest) const;
void copy_to(writeonly_texture_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Kopyalanacak nesne.

*_Rank*<br/>
Dokunun derecesi.

*value_type*<br/>
Dokudaki öğelerin türü.

## <a name="data"></a>verileri

Bu dokunun ham verilerine bir CPU işaretçisi döndürür.

```cpp
void* data() restrict(cpu);

const void* data() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Dokunun ham verilerine yönelik bir işaretçi.

## <a name="depth_pitch"></a>depth_pitch

CPU 'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını alır.

```cpp
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;
```

## <a name="get"></a>Al

Belirtilen dizindeki öğenin değerini döndürür.

```cpp
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizindeki öğenin değeri.

## <a name="get_associated_accelerator_view"></a>get_associated_accelerator_view

Bu dokunun kopyalanacağı tercih edilen hedef olan accelerator_view döndürür.

```cpp
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Bu dokunun kopyalanacağı tercih edilen hedef [accelerator_view](accelerator-view-class.md) .

## <a name="get_depth_pitch"></a>get_depth_pitch

CPU 'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısını döndürür.

```cpp
unsigned int get_depth_pitch() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

CPU 'da bir 3B hazırlama dokusundaki her derinlik dilimi arasında bulunan bayt sayısı.

## <a name="get_row_pitch"></a>get_row_pitch

2 boyutlu bir hazırlama dokusundaki her satır arasında veya 3 boyutlu bir hazırlama dokusundaki bir derinlik diliminin her satırı arasında bulunan bayt sayısını döndürür.

```cpp
unsigned int get_row_pitch() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

2 boyutlu bir hazırlama dokusundaki her satır arasında veya 3 boyutlu hazırlama dokusundaki bir derinlik diliminin her satırı arasında bulunan bayt sayısı.

## <a name="operator_call"></a>operator ()

Parametreler tarafından belirtilen öğe değerini döndürür.

```cpp
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
Dizin.

*_I0*<br/>
Dizinin en önemli bileşeni.

*_I1*<br/>
Dizinin en çok önemli bir bileşeni.

*_I2*<br/>
Dizinin en az önemli bileşeni.

*_Rank*<br/>
Dizinin derecesi.

### <a name="return-value"></a>Dönüş Değeri

Parametreler tarafından belirtilen öğe değeri.

## <a name="operator_at"></a>operator []

Belirtilen dizindeki öğeyi döndürür.

```cpp
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizin.

*_I0*<br/>
Dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde olan öğe.

## <a name="operator_eq"></a>işleç =

Belirtilen [doku](texture-class.md) nesnesini buna kopyalar.

```cpp
texture& operator= (
    const texture& _Other);

texture& operator= (
    texture<value_type, _Rank>&& _Other);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalamanın `texture` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `texture` nesnesine bir başvuru.

## <a name="rank"></a>sırası

`texture` nesnesinin derecesini alır.

```cpp
static const int rank = _Rank;
```

## <a name="row_pitch"></a>row_pitch

CPU 'da 2B veya 3B hazırlama dokusundaki her satır arasında bulunan bayt sayısını alır.

```cpp
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;
```

## <a name="set"></a>kurmak

Belirtilen dizindeki öğenin değerini ayarlar.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Öğenin dizini.

*_Rank*<br/>
Dizinin derecesi.

*value*<br/>
Öğesinin yeni değeri.

## <a name="ctor"></a>uyla

`texture` sınıfının yeni bir örneğini başlatır.

```cpp
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
Dokunun konumunu belirten [accelerator_view](accelerator-view-class.md) .

*_Av*<br/>
Dokunun konumunu belirten [accelerator_view](accelerator-view-class.md) .

*_Associated_av*<br/>
Bu dokusundaki veya bu dokudan kopyalar için tercih edilen hedefi belirten bir accelerator_view.

*_Bits_per_scalar_element*<br/>
Dokunun temeldeki skaler türünde her bir skaler öğe başına bit sayısı. Genel olarak, desteklenen değer 8, 16, 32 ve 64 ' dir. 0 belirtilirse, bit sayısı temeldeki scalar_type aynıdır. 64 yalnızca çift tabanlı dokular için geçerlidir.

*_Ext*<br/>
Dokunun her boyutunun kapsamı.

*_E0*<br/>
Dokunun en önemli bileşeni.

*_E1*<br/>
Dokunun bir sonraki en önemli bileşeni.

*_E2*<br/>
Dokunun kapsamının en az önemli bileşeni.

*_Input_iterator*<br/>
Giriş yineleyicisinin türü.

*_Mipmap_levels*<br/>
Temel dokudaki mipmap düzeylerinin sayısı. 0 belirtilirse, doku, belirtilen kapsam için mümkün olan en küçük boyuta kadar mipmap düzeylerinin tam aralığına sahip olur.

*_Rank*<br/>
Kapsamın derecesi.

*_Source*<br/>
Ana bilgisayar arabelleği işaretçisi.

*_Src*<br/>
Kopyalamak için dokunun.

*_Src_byte_size*<br/>
Kaynak arabellekteki bayt sayısı.

*_Src_first*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*_Src_last*<br/>
Kaynak kapsayıcıya bir bitiş yineleyicisi.

*_Other*<br/>
Diğer veri kaynağı.

*_Rank*<br/>
Bölümün derecesi.

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
