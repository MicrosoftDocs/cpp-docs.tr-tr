---
title: texture_view sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3db02d9cafb87c0f173546687ad01390e09b9f68
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696272"
---
# <a name="textureview-class"></a>texture_view Sınıfı
Okuma erişimi ve bir doku yazma erişimi sağlar. `texture_view` değer türü olan dokular okumak için yalnızca kullanılabilir `int`, `unsigned int`, veya `float` varsayılan 32-bit bpse sahip. Diğer doku biçimleri okumak için kullandığınız `texture_view<const value_type, _Rank>`.  
  
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
 `value_type`  
 Doku toplama öğelerin türü.  
  
 `_Rank`  
 Derecesini `texture_view`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`value_type`|Doku toplamalar öğelerin türü.|  
|`coordinates_type`|Bir texel belirtmek için kullanılan koordinat türünü `texture_view`— diğer bir deyişle, bir `short_vector` bir değer türü ilişkili doku olarak aynı dereceye sahip `float`.|  
|`gather_return_type`|Operations toplamak için kullanılan dönüş türü — derece diğer bir deyişle, 4 `short_vector` ayrı tutma dört homojen renk bileşenleri örneklenen dört texel değerlerinden toplanan.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[texture_view Oluşturucusu](#ctor)|Fazla Yüklendi. Oluşturan bir `texture_view` örneği.|  
|[~ texture_view yok Edicisi](#ctor)|Bozar `texture_view` örneği.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[gather_alpha](#gather_alpha)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarının adresindeki doku örnekleri ve dört örneklenen texels alfa (w) bileşenlerinin döndürür.|  
|[gather_blue](#gather_blue)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarının adresindeki doku örnekleri ve dört örneklenen texels mavi (z) bileşenlerinin döndürür.|  
|[gather_green](#gather_green)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarının adresindeki doku örnekleri ve dört örneklenen texels yeşil (y) bileşenlerinin döndürür.|  
|[gather_red](#gather_red)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarının adresindeki doku örnekleri ve dört örneklenen texels kırmızı (x) bileşenlerinin döndürür.|  
|[get](#get)|Fazla Yüklendi. Dizine göre öğe değerini alır.|  
|[Örnek](#sample)|Fazla Yüklendi. Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatları ve ayrıntı düzeyi doku örnekleri.|  
|[set](#set)|Bir öğenin değerini dizine göre ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator()](#operator_call)|Fazla Yüklendi. Dizine göre öğe değerini alır.|  
|[[] işleci](#operator_at)|Fazla Yüklendi. Dizine göre öğe değerini alır.|  
|[operator=](#operator_eq)|Fazla Yüklendi. Atama işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[value_type](#value_type)|Değer türü öğelerinin `texture_view`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Texture_base`  
  
 `texture_view`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="dtor"></a> ~ texture_view 

 Bozar `texture_view` örneği.  
  
```  
~texture_view() restrict(amp, cpu);
```  
  
##  <a name="ctor"></a> texture_view 

 Oluşturan bir `texture_view` örneği.  
  
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
 `_Src`  
 [1, 2] Oluşturucusu  
 `texture` Üzerine yazılabilir `texture_view` oluşturulur.  
  
 [3, 4] Oluşturucusu  
 `texture` Üretileceği Paylaşımsız `texture_view` oluşturulur.  
  
 `_Other`  
 [5] kopya Oluşturucu  
 Yazılabilir kaynak `texture_view`.  
  
 [6, 7] Kopya Oluşturucu  
 Yazılabilir olmayan kaynak `texture_view`.  
  
 `_Mipmap_level`  
 Kaynak üzerinde belirli mipmap düzeyi `texture` , bu yazılabilir `texture_view` bağlar. Varsayılan değer, üst düzey (en fazla ayrıntı) MIP düzeyi temsil eden 0 ' dır.  
  
 `_Most_detailed_mip`  
 (En fazla ayrıntı) MIP düzeye belirtilen göreli görünüm için üst `texture_view` nesnesi.  
  
 `_Mip_levels`  
 Mipmap düzey üzerinden erişilebilir sayısını `texture_view`.  
  
##  <a name="gather_red"></a> gather_red 

 Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarının adresindeki doku örnekleri ve dört örneklenen texels kırmızı (x) bileşenlerinin döndürür.  
  
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
 `_Address_mode`  
 Adres modunu kullanmak için örnek için `texture_view`. Adres modunu tüm boyutları için aynıdır.  
  
 `_Sampler`  
 Kullanmak üzere örneği yapılandırma örneği `texture_view`.  
  
 `_Coord`  
 Örnekten yapılacak koordinatları. Kesirli koordinat değerler arasında örnek texels kesinti için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 4 kırmızı (x) bileşeni içeren bir derece 4 kısa vektör texel değerleri örneklenen.  
  
##  <a name="gather_green"></a> gather_green 

 Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarının adresindeki doku örnekleri ve dört örneklenen texels yeşil (y) bileşenlerinin döndürür.  
  
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
 `_Address_mode`  
 Adres modunu kullanmak için örnek için `texture_view`. Adres modunu tüm boyutları için aynıdır.  
  
 `_Sampler`  
 Kullanmak üzere örneği yapılandırma örneği `texture_view`.  
  
 `_Coord`  
 Örnekten yapılacak koordinatları. Kesirli koordinat değerler arasında örnek texels kesinti için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 4 yeşil (y) bileşeni içeren bir derece 4 kısa vektör texel değerleri örneklenen.  
  
##  <a name="gather_blue"></a> gather_blue 

 Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarının adresindeki doku örnekleri ve dört örneklenen texels mavi (z) bileşenlerinin döndürür.  
  
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
 `_Address_mode`  
 Adres modunu kullanmak için örnek için `texture_view`. Adres modunu tüm boyutları için aynıdır.  
  
 `_Sampler`  
 Kullanmak üzere örneği yapılandırma örneği `texture_view`.  
  
 `_Coord`  
 Örnekten yapılacak koordinatları. Kesirli koordinat değerler arasında örnek texels kesinti için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 4 kırmızı (x) bileşeni içeren bir derece 4 kısa vektör texel değerleri örneklenen.  
  
##  <a name="gather_alpha"></a> gather_alpha 

 Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatlarının adresindeki doku örnekleri ve dört örneklenen texels alfa (w) bileşenlerinin döndürür.  
  
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
 `_Address_mode`  
 Adres modunu kullanmak için örnek için `texture_view`. Adres modunu tüm boyutları için aynıdır.  
  
 `_Sampler`  
 Kullanmak üzere örneği yapılandırma örneği `texture_view`.  
  
 `_Coord`  
 Örnekten yapılacak koordinatları. Kesirli koordinat değerler arasında örnek texels kesinti için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir derece kısa 4 vektör alfa (4 bileşeninin texel değerleri örneklenen w) içeren.  
  
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
 `_Index`  
 Büyük olasılıkla birden çok boyutlu alınacak öğenin dizini.  
  
 `_Mip_level`  
 Mipmap düzeyi biz değeri almalısınız. Varsayılan değer 0 en ayrıntılı mipmap düzeyi temsil eder.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin değeri.  
  
##  <a name="operator_eq"></a> işleç = 

 Belirtildiği gibi aynı doku görünümünü atar `texture_view` bu `texture_view` örneği.  
  
```  
texture_view<value_type, _Rank>& operator= (// [1] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view<const value_type, _Rank>& operator= (// [2] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

 
texture_view<const value_type, _Rank>& operator= (// [3] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 [1, 2] Kopya Oluşturucu  
 Bir yazılabilir `texture_view` nesnesi.  
  
 [3] kopya Oluşturucu  
 Bir Paylaşımsız `texture_view` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `texture_view` örneği.  
  
##  <a name="operator_at"></a> [] işleci 

 Dizine göre öğe değerini döndürür.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);

 
value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Büyük olasılıkla birden çok boyutlu dizini.  
  
 `_I0`  
 Tek boyutlu dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi değeri dizine göre `_Index`.  
  
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
 `_Index`  
 Büyük olasılıkla birden çok boyutlu dizini.  
  
 `_I0`  
 Dizin en önemli bileşenidir.  
  
 `_I1`  
 Dizin İleri-için-çoğu-önemli bileşenidir.  
  
 `_I2`  
 Dizin en az önemli bileşenidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi değeri dizine göre `_Index`.  
  
##  <a name="sample"></a> Örnek 

 Belirtilen örnekleme yapılandırmayı kullanarak belirtilen koordinatları ve ayrıntı düzeyi doku örnekleri.  
  
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
 `_Filter_mode`  
 Texture_view örneklemek için kullanılacak filtre modu. Filtre modu minimization, maximization ve mipmap filtreleri ile aynıdır.  
  
 `_Address_mode`  
 Texture_view örneklemek için kullanılacak adresi modu. Adres modunu tüm boyutları için aynıdır.  
  
 `_Sampler`  
 Texture_view örneklemek için kullanmak üzere örneği yapılandırma.  
  
 `_Coord`  
 Örnekten yapılacak koordinatları. Kesirli koordinat değerler arasında texel değerleri kesinti için kullanılır.  
  
 `_Level_of_detail`  
 Değer örnekleme mipmap düzeyini belirtir. Kesirli değerler arasında iki mipmap düzeyleri kesinti için kullanılır. Ayrıntı varsayılan düzeyini en ayrıntılı MIP düzeyi temsil eden 0 ' dır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ara değerli örnek değer.  
  
##  <a name="set"></a> ayarlama 

 Belirtilen değer için belirtilen dizindeki öğeyi değerini ayarlar.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Ayarlama, büyük olasılıkla birden çok boyutlu öğenin dizini.  
  
 `value`  
 Öğe ayarlanacak değer.  
  
##  <a name="value_type"></a> value_type 

 Texture_view öğelerinin değer türü.  
  
```  
typedef typename const value_type value_type;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
