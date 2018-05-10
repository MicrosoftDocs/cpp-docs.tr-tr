---
title: 'CONCURRENCY::Graphics:: Direct3D ad alanı işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
dev_langs:
- C++
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed95ed8df8a42dc62684c71a3005c2f33fecd18
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>CONCURRENCY::Graphics:: Direct3D ad alanı işlevleri
||||  
|-|-|-|  
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|  
|[make_texture](#make_texture)|[msad4](#msad4)|  

 
##  <a name="get_sampler"></a>  get_sampler  
 Get verilen Hızlandırıcı D3D örneği durumu arabirimde belirtilen örneği nesne bu temsil görüntüleyin.  
  
```  
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,  
    const sampler& _Sampler) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Av`  
 Oluşturulması olduğu D3D örneği durumu D3D Hızlandırıcı görüntüleyin.  
  
 `_Sampler`  
 Temel alınan D3D örneği durumu arabirimi oluşturulacağı bir örneği nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen örneği temsil eden D3D örneği durumuna karşılık gelen IUnknown arabirimi işaretçisi.  
  
##  <a name="get_texture"></a>  get_texture  
 Belirtilen temel Direct3D Doku arabirimi alır [doku](texture-class.md) nesnesi.  
  
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
 `value_type`  
 Doku öğe türü.  
  
 `_Rank`  
 Doku derecesini.  
  
 `_Texture`  
 Bir doku veya arka plandaki Direct3D Doku arabirimi döndürülen accelerator_view ile ilişkili doku görünümü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Doku temel Direct3D Doku karşılık gelen IUnknown arabirimi işaretçisi.  
  
##  <a name="make_sampler"></a>  make_sampler  
 Bir örneği D3D örneği durumu arabirimi işaretçi oluşturun.  
  
```  
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_D3D_sampler`  
 IUnknown arabirimi işaretçisi gelen örneği oluşturmak için D3D örneği durumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir örneği sağlanan D3D örneği durumunu temsil eder.  
  
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
 `value_type`  
 Dokudaki öğelerin türü.  
  
 `_Rank`  
 Doku derecesini.  
  
 `_Av`  
 Oluşturulması olduğu doku D3D Hızlandırıcı görüntüleyin.  
  
 `_D3D_texture`  
 IUnknown arabirimi işaretçisi gelen doku oluşturmak için D3D doku.  
  
 `_View_format`  
 Bu doku oluşturulan görünümleri için kullanılacak DXGI biçimi. Temel alınan _D3D_texture biçimlerinin ve bu şablonu value_type biçimi türetilen DXGI_FORMAT_UNKNOWN (varsayılan) geçirin. Sağlanan biçimi _D3D_texture temel biçimiyle uyumlu olması gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sağlanan D3D doku kullanarak doku.  
  
##  <a name="msad4"></a>  msad4  
 Bir 4-bayt başvurusu ve 8-bayt kaynak değeri karşılaştırır ve 4 SUM'ları vektörü birikir. Her toplam farklı bayt hizalamaları mutlak farklar başvuru ve kaynak değerleri arasında maskelenmiş toplamını karşılık gelir.  
  
```  
inline uint4 msad4(
    uint _Reference,  
    uint2 _Source,  
    uint4 _Accum) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Reference`  
 Bir uint değeri 4 bayt başvuru dizisi  
  
 `_Source`  
 Kaynak iki uint değerlerin vektör 8 bayt dizisi.  
  
 `_Accum`  
 Farklı bayt hizalamaları mutlak farklar başvuru ve kaynak değerleri arasında maskelenmiş toplamına eklenecek 4 değerleri vektörü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 4 SUM'ları vektörü döndürür. Her toplam farklı bayt hizalamaları mutlak farklar başvuru ve kaynak değerleri arasında maskelenmiş toplamını karşılık gelir.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_graphics.h  
  
 **Namespace:** CONCURRENCY::Graphics:: Direct3D 

## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::graphics::direct3d Ad Alanı](concurrency-graphics-direct3d-namespace.md)
