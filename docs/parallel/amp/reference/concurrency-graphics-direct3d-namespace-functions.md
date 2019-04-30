---
title: 'CONCURRENCY::Graphics:: Direct3D ad alanı işlevleri'
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 18fb409b033ea14c3a140ea6600fc43cf3a8d603
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405553"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>CONCURRENCY::Graphics:: Direct3D ad alanı işlevleri

||||
|-|-|-|
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|
|[make_texture](#make_texture)|[msad4](#msad4)|

##  <a name="get_sampler"></a>  get_sampler

Belirtilen örnekleyici nesnesini temsil eden belirli hızlandırıcıda D3D örnekleyici durumu arabirimini alın görüntüleyin.

```
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Av*<br/>
D3D örnekleyici durumun oluşturulacağı olduğu bir D3D Hızlandırıcısı görünümü.

*_Sampler*<br/>
Kendisi için temel D3D örnekleyici durumu arabirimini oluşturulan bir örnekleyici nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Verilen örnekleyiciyi temsil eden D3D örnekleyici durumuna karşılık gelen IUnknown arabirim işaretçisi.

##  <a name="get_texture"></a>  get_texture

Belirtilen temel Direct3D Doku arabirimini alır [doku](texture-class.md) nesne.

```
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

*_Dizin*<br/>
Dokunun boyut sayısı.

*_Texture*<br/>
Bir doku veya doku görünümü için esas Direct3D Doku arabirimini döndürülen accelerator_view ile ilişkili.

### <a name="return-value"></a>Dönüş Değeri

Dokunun altındaki Direct3D dokusuna karşılık gelen IUnknown arabirim işaretçisi.

##  <a name="make_sampler"></a>  make_sampler

Bir D3D örnekleyici durumu arabirim işaretçisinden bir örnekleyici oluşturun.

```
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_D3D_sampler*<br/>
Örnekleyicinin oluşturulacağı D3D örnekleyicisinin bilinmeyen arayüz işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Örnekleyici, sağlanan D3D örnekleyici durumunu temsil eder.

##  <a name="make_texture"></a>  make_texture

Oluşturur bir [doku](texture-class.md) belirtilen parametreleri kullanarak nesne.

```
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

*_Dizin*<br/>
Dokunun boyut sayısı.

*_Av*<br/>
Üzerinde dokunun oluşturulması bir D3D Hızlandırıcısı görünümü.

*_D3D_texture*<br/>
Dokunun oluşturulacağı D3D dokusunu bilinmeyen arayüz işaretçisi.

*_View_format*<br/>
Bu dokudan oluşturulan görünümler için kullanılacak DXGI biçimi. Biçimi (varsayılan) _d3d_texture temel biçimi ve bu şablonun value_type biçimi türetmek için geçirin. Sağlanan biçim _d3d_texture temel biçimiyle uyumlu olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Sağlanan D3D dokusunu kullanan bir doku.

##  <a name="msad4"></a>  msad4

4 bayt başvuru değerini ve 8 bayt kaynak değerini karşılaştırır ve 4 toplamlarının vektörünü biriktirir. Her bir toplamın maskelenmiş başvuru değeri ile kaynak değer arasındaki farklı bayt hizalamalarının, mutlak farkları toplamına karşılık gelir.

```
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>Parametreler

*_Başvuru*<br/>
Bir birim değerinde 4 baytlık başvuru dizisi

*_Source*<br/>
İki uint değerlerinin vektördeki 8 baytlık kaynak dizisi.

*_Accum*<br/>
Maskeli başvuru değeri ile kaynak değer arasındaki farklı bayt hizalamalarının, mutlak farkları toplamına eklenecek 4 değer oluşan bir vektörü.

### <a name="return-value"></a>Dönüş Değeri

4 toplamlı bir vektör döndürür. Her bir toplamın maskelenmiş başvuru değeri ile kaynak değer arasındaki farklı bayt hizalamalarının, mutlak farkları toplamına karşılık gelir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp_graphics.h

**Namespace:** CONCURRENCY::Graphics:: Direct3D

## <a name="see-also"></a>Ayrıca bkz.

[Concurrency::graphics::direct3d Ad Alanı](concurrency-graphics-direct3d-namespace.md)
