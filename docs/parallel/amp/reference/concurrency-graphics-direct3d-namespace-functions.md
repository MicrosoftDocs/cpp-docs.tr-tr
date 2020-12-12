---
description: ': Concurrency:: Graphics::d irect3d Namespace işlevleri hakkında daha fazla bilgi edinin'
title: Concurrency::graphics::direct3d ad alanı işlevleri
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 52556835c843744e03661b3ef5b718c884765c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122362"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::graphics::direct3d ad alanı işlevleri

:::row:::
   :::column span="":::
      [`get_sampler`](#get_sampler)\
      [`get_texture`](#get_texture)
   :::column-end:::
   :::column span="":::
      [`make_sampler`](#make_sampler)
   :::column-end:::
   :::column span="":::
      [`make_texture`](#make_texture)
   :::column-end:::
   :::column span="":::
      [`msad4`](#msad4)
   :::column-end:::
:::row-end:::

## <a name="get_sampler"></a><a name="get_sampler"></a> get_sampler

Belirtilen örnekleyici nesnesini temsil eden sağlanan Hızlandırıcı görünümünde D3D örnekleyici durum arabirimini alın.

```cpp
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
D3D örnekleyici durumunun oluşturulacağı D3D Hızlandırıcısı görünümü.

*_Sampler*<br/>
Temel alınan D3D örnekleyici durum arabiriminin oluşturulduğu bir örnekleyici nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen örnekleyiciyi temsil eden D3D örnekleyici durumuna karşılık gelen IUnknown arabirim işaretçisi.

## <a name="get_texture"></a><a name="get_texture"></a> get_texture

Belirtilen [doku](texture-class.md) nesnesini temel alan Direct3D doku arabirimini alır.

```cpp
template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Dokunun öğe türü.

*_Rank*<br/>
Dokunun derecesi.

*_Texture*<br/>
Temel alınan Direct3D doku arabiriminin döndürüldüğü accelerator_view ilişkili doku veya doku görünümü.

### <a name="return-value"></a>Dönüş Değeri

Dokuyu temeldeki Direct3D dokusuyla karşılık gelen IUnknown arabirim işaretçisi.

## <a name="make_sampler"></a><a name="make_sampler"></a> make_sampler

D3D örnekleyici durumu arabirim işaretçisinden bir örnekleyici oluşturun.

```cpp
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_D3D_sampler*<br/>
Örnekleyiciyi oluşturmak için D3D örnekleyici durumunun IUnknown arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Örnekleyici, belirtilen D3D örnekleyici durumunu temsil eder.

## <a name="make_texture"></a><a name="make_texture"></a> make_texture

Belirtilen parametreleri kullanarak bir [doku](texture-class.md) nesnesi oluşturur.

```cpp
template<
    typename value_type,
    int _Rank
>
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,
    _In_ IUnknown* _D3D_texture,
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Dokudaki öğelerin türü.

*_Rank*<br/>
Dokunun derecesi.

*_Av*<br/>
Dokunun oluşturulacağı D3D Hızlandırıcısı görünümü.

*_D3D_texture*<br/>
' Den doku oluşturmak için D3D dokusunun, IUnknown arabirim işaretçisi.

*_View_format*<br/>
Bu dokusundaki oluşturulan görünümler için kullanılacak DXGI biçimi. Biçimi _D3D_texture temel biçiminden ve bu şablonun value_type türeten DXGI_FORMAT_UNKNOWN geçirin (varsayılan). Belirtilen biçim _D3D_texture temel alınan biçimiyle uyumlu olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen D3D dokusunu kullanan bir doku.

## <a name="msad4"></a><a name="msad4"></a> msad4

4 baytlık bir başvuru değerini ve 8 baytlık bir kaynak değeri karşılaştırır ve 4 toplamların bir vektörünü toplar. Her bir toplam, başvuru değeri ile kaynak değer arasındaki farklı bayt hizalamalarının maskelenmiş toplamına karşılık gelir.

```cpp
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Reference*<br/>
Tek bir uint değerindeki 4 baytlık başvuru dizisi

*_Source*<br/>
İki uint değerinin vektörde 8 baytlık Kaynak dizisi.

*_Accum*<br/>
Başvuru değeri ile kaynak değer arasındaki farklı bayt hizalamalarının maskelenmiş toplamına eklenecek 4 değerin vektörü.

### <a name="return-value"></a>Dönüş Değeri

4 toplamların vektörünü döndürür. Her bir toplam, başvuru değeri ile kaynak değer arasındaki farklı bayt hizalamalarının maskelenmiş toplamına karşılık gelir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp_graphics. h

**Ad alanı:** Concurrency:: Graphics::d irect3d

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency:: Graphics::d irect3d ad alanı](concurrency-graphics-direct3d-namespace.md)
