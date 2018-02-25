---
title: "texture sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 822797fb04104b28cf72f8d8ea4291a5ad283d20
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="texture-class"></a>texture Sınıfı
Veri toplama üzerinde bir doku olan bir `accelerator_view` ölçüde etki alanındaki. Değişkenleri, bir uzantı etki alanındaki her öğe için bir tane koleksiyonudur. Her bir değişken C++ ilkel türüne karşılık gelen bir değer tutar ( `unsigned int`, `int`, `float`, `double`), skaler bir tür ( `norm`, veya `unorm`), ya da kısa vektör türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename value_type,  int _Rank>  
class texture;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value_type`  
 Dokudaki öğelerin türü.  
  
 `_Rank`  
 Doku derecesini.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`scalar_type`|Skaler türler.|  
|`value_type`|Değer türleri.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Doku Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `texture` sınıfı.|  
|[~ texture yok Edicisi](#ctor)|Bozar `texture` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[copy_to](#copy_to)|Kopya `texture` derin bir kopya yaparak bu hedefe nesnesi.|  
|[Veri](#data)|Bir CPU işaretçi bu doku ham verileri döndürür.|  
|[get](#get)|Belirtilen dizindeki öğenin değerini döndürür.|  
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Döndürür [accelerator_view](accelerator-view-class.md) diğer bir deyişle kopyalanması bu doku için tercih edilen hedef.|  
|[get_depth_pitch](#get_depth_pitch)|CPU üzerinde doku hazırlama 3B her derinliği dilimi arasında bayt sayısını döndürür.|  
|[get_row_pitch](#get_row_pitch)|Her satırda bir 2B veya CPU üzerinde doku hazırlama 3B arasında bayt sayısını döndürür.|  
|[set](#set)|Öğesinin değeri belirtilen dizindeki ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator()](#operator_call)|Parametrelerle belirtilen öğenin değerini döndürür.|  
|[operator[]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|  
|[operator=](#operator_eq)|Belirtilen kopyalar [doku](texture-class.md) bu bir nesne.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[sıra sabiti](#rank)|Derecesini alır `texture` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[associated_accelerator_view](#associated_accelerator_view)|Alır [accelerator_view](accelerator-view-class.md) diğer bir deyişle kopyalanması bu doku için tercih edilen hedef.|  
|[depth_pitch](#depth_pitch)|Bir 3B hazırlama doku CPU üzerinde her derinliği dilimi arasındaki bayt sayısını alır.|  
|[row_pitch](#row_pitch)|Her satırda bir 2B veya 3B arasında bayt sayısı, CPU üzerinde doku hazırlama alır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Texture_base`  
  
 `texture`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_graphics.h  
  
 **Namespace:** Concurrency::graphics  
  
##  <a name="dtor"></a> ~ texture 

 Bozar `texture` nesnesi.  
  
```  
~texture() restrict(cpu);
```  
  
##  <a name="associated_accelerator_view"></a> associated_accelerator_view 

 Alır [accelerator_view](accelerator-view-class.md) diğer bir deyişle kopyalanması bu doku için tercih edilen hedef.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="copy_to"></a> copy_to 

 Kopya `texture` derin bir kopya yaparak bu hedefe nesnesi.  
  
```  
void copy_to(texture& _Dest) const; 
void copy_to(writeonly_texture_view<value_type, _Rank>& _Dest) const; 
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Kopyalamak için nesne.  
  
 `_Rank`  
 Doku derecesini.  
  
 `value_type`  
 Dokudaki öğelerin türü.  
  
##  <a name="data">Veri</a> 

 Bir CPU işaretçi bu doku ham verileri döndürür.  
  
```  
void* data() restrict(cpu);

 
const void* data() const restrict(cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Doku ham verileri için bir işaretçi.  
  
##  <a name="depth_pitch"></a> depth_pitch 

 Bir 3B hazırlama doku CPU üzerinde her derinliği dilimi arasındaki bayt sayısını alır.  
  
```  
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;  
```  
  
##  <a name="get"></a> Al 

 Belirtilen dizindeki öğenin değerini döndürür.  
  
```  
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Öğenin dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizindeki öğesinin değeri.  
  
##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view 

 Tercih edilen kopyalanması bu doku hedefidir accelerator_view döndürür.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 [Accelerator_view](accelerator-view-class.md) diğer bir deyişle kopyalanması bu doku için tercih edilen hedef.  
  
##  <a name="get_depth_pitch"></a> get_depth_pitch 

 CPU üzerinde doku hazırlama 3B her derinliği dilimi arasında bayt sayısını döndürür.  
  
```  
unsigned int get_depth_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 CPU üzerinde doku hazırlama 3B her derinliği dilimi arasındaki bayt sayısı.  
  
##  <a name="get_row_pitch"></a> get_row_pitch 

 Bayt sayısını 2 boyutlu hazırlama doku her satırda bir derinliği dilimi 3 boyutlu hazırlama doku her satır arasında veya döndürür.  
  
```  
unsigned int get_row_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her satırda bir 2 boyutlu hazırlama doku derinliği dilim 3 boyutlu hazırlama doku içindeki her satır arasında veya bayt sayısı.  
  
##  <a name="operator_call"></a> operator() 

 Parametrelerle belirtilen öğenin değerini döndürür.  
  
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
 `_Index`  
 Dizini.  
  
 `_I0`  
 Dizin en önemli bileşenidir.  
  
 `_I1`  
 Dizin İleri-için-çoğu-önemli bileşenidir.  
  
 `_I2`  
 Dizin en az önemli bileşenidir.  
  
 `_Rank`  
 Dizin derecesini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parametrelerle belirtilen öğe değeri.  
  
##  <a name="operator_at"></a> [] işleci 

 Belirtilen dizindeki öğeyi döndürür.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Dizini.  
  
 `_I0`  
 Dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizindeki öğeyi.  
  
##  <a name="operator_eq"></a> işleç = 

 Belirtilen kopyalar [doku](texture-class.md) bu bir nesne.  
  
```  
texture& operator= (
    const texture& _Other);

 
texture& operator= (
    texture<value_type, _Rank>&& _Other);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `texture` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `texture` nesnesi.  
  
##  <a name="rank"></a> RANK 

 Derecesini alır `texture` nesnesi.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="row_pitch"></a> row_pitch 

 Her satırda bir 2B veya 3B arasında bayt sayısı, CPU üzerinde doku hazırlama alır.  
  
```  
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;  
```  
  
##  <a name="set"></a> set 

 Öğesinin değeri belirtilen dizindeki ayarlar.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Öğenin dizini.  
  
 `_Rank`  
 Dizin derecesini.  
  
 `value`  
 Öğesinin yeni değeri.  
  
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
 `_Acc_view`  
 [Accelerator_view](accelerator-view-class.md) doku konumunu belirtir.  
  
 `_Av`  
 [Accelerator_view](accelerator-view-class.md) doku konumunu belirtir.  
  
 `_Associated_av`  
 Tercih edilen hedef belirten bir accelerator_view için veya bu doku kopyalar.  
  
 `_Bits_per_scalar_element`  
 Temel alınan skaler bir türde doku skaler her öğe başına bit sayısı. Genel olarak, desteklenen değer: 8, 16, 32 ve 64. 0 belirtilirse bit sayısını temel scalar_type aynıdır. 64 yalnızca çift tabanlı dokular için geçerlidir.  
  
 `_Ext`  
 Her boyut doku içindeki kapsamı.  
  
 `_E0`  
 Doku en önemli bileşenidir.  
  
 `_E1`  
 Doku İleri-için-çoğu-önemli bileşenidir.  
  
 `_E2`  
 Doku kapsamını en az önemli bileşenidir.  
  
 `_Input_iterator`  
 Giriş interator türü.  
  
 `_Mipmap_levels`  
 Temel alınan doku mipmap düzey sayısı. 0 belirtilirse, belirtilen kapsam için en küçük olası ölçüye mipmap düzeyleri tam aralığını doku gerekir.  
  
 `_Rank`  
 Uzantı derecesini.  
  
 `_Source`  
 Bir ana bilgisayar arabellek için bir işaretçi.  
  
 `_Src`  
 Doku kopyalamak için.  
  
 `_Src_byte_size`  
 Kaynak arabellekteki bayt sayısı.  
  
 `_Src_first`  
 Başlangıç yineleyici kaynak kapsayıcı içine.  
  
 `_Src_last`  
 Bitiş yineleyici kaynak kapsayıcı içine.  
  
 `_Other`  
 Diğer veri kaynağı.  
  
 `_Rank`  
 Bölüm derecesini.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
