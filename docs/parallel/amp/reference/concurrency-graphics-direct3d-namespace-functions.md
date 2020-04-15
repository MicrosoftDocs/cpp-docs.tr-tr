---
title: Concurrency::graphics::direct3d ad alanı işlevleri
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 330c1aa94b1d122901fc23576686032400249d31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376386"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::graphics::direct3d ad alanı işlevleri

||||
|-|-|-|
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|
|[make_texture](#make_texture)|[msad4](#msad4)|

## <a name="get_sampler"></a><a name="get_sampler"></a>get_sampler

Belirtilen örnekleyici nesnesini temsil eden verilen hızlandırıcı görünümünde D3D örnekleyici durumu arabirimini alın.

```cpp
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
D3D örnekleyici durumunun oluşturulacak d3D hızlandırıcı görünümü.

*_Sampler*<br/>
Altta yatan D3D örnekleyici durum arabiriminin oluşturulduğu bir örnekleyici nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Verilen örnekleyiciyi temsil eden D3D örnekleyici durumuna karşılık gelen IUnknown arabirim işaretçisi.

## <a name="get_texture"></a><a name="get_texture"></a>get_texture

Belirtilen [doku](texture-class.md) nesnesinin altında yatan Direct3D doku arabirimini alır.

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
Temel Direct3D doku arabiriminin döndürüldildiği accelerator_view ilişkili doku veya doku görünümü.

### <a name="return-value"></a>Dönüş Değeri

Doku altında yatan Direct3D dokuya karşılık gelen IUnknown arabirim işaretçisi.

## <a name="make_sampler"></a><a name="make_sampler"></a>make_sampler

D3D örnekleyici durum arabirimi işaretçisinden bir örnekleyici oluşturun.

```cpp
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_D3D_sampler*<br/>
Örnekleyici oluşturmak için D3D örnekleyici durumunun IUnknown arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Örnekleyici, sağlanan D3D örnekleyici durumunu temsil eder.

## <a name="make_texture"></a><a name="make_texture"></a>make_texture

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
Dokunun oluşturulacak d3D hızlandırıcı görünümü.

*_D3D_texture*<br/>
D3D doku iUnknown arabirim işaretçisi doku oluşturmak için.

*_View_format*<br/>
Bu dokudan oluşturulan görünümler için kullanılacak DXGI biçimi. Biçimi _D3D_texture'nin temel biçiminden ve bu şablonun value_type türetmek için DXGI_FORMAT_UNKNOWN (varsayılan) geçirin. Sağlanan biçim, _D3D_texture temel biçimiyle uyumlu olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan D3D dokusunu kullanan bir doku.

## <a name="msad4"></a><a name="msad4"></a>msad4

4 baytlık referans değerini ve 8 baytlık kaynak değerini karşılaştırır ve 4 toplamlı bir vektör birikir. Her toplam, başvuru değeri ve kaynak değer arasındaki farklı bayt hizalamalarının mutlak farklarının maskeli toplamına karşılık gelir.

```cpp
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Reference*<br/>
Bir uint değerinde4 baytreferans dizisi

*_Source*<br/>
İki uint değerden oluşan bir vektördeki 8 baytlık kaynak dizi.

*_Accum*<br/>
Referans değeri ve kaynak değer arasındaki farklı bayt hizalamalarının mutlak farklarının maskeli toplamına eklenecek 4 değerden oluşan bir vektör.

### <a name="return-value"></a>Dönüş Değeri

4 toplamlı bir vektör verir. Her toplam, başvuru değeri ve kaynak değer arasındaki farklı bayt hizalamalarının mutlak farklarının maskeli toplamına karşılık gelir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp_graphics.h

**Ad alanı:** Eşzamanlılık::grafikler::direct3d

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics::direct3d Ad Alanı](concurrency-graphics-direct3d-namespace.md)
