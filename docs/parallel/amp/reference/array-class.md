---
title: array sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- array
- AMP/array
- AMP/Concurrency::array::array
- AMP/Concurrency::array::copy_to
- AMP/Concurrency::array::data
- AMP/Concurrency::array::get_accelerator_view
- AMP/Concurrency::array::get_associated_accelerator_view
- AMP/Concurrency::array::get_cpu_access_type
- AMP/Concurrency::array::get_extent
- AMP/Concurrency::array::reinterpret_as
- AMP/Concurrency::array::section
- AMP/Concurrency::array::view_as
- AMP/Concurrency::array::rank
- AMP/Concurrency::array::accelerator_view
- AMP/Concurrency::array::associated_accelerator_view
- AMP/Concurrency::array::cpu_access_type
- AMP/Concurrency::array::extent
dev_langs:
- C++
helpviewer_keywords:
- array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0a7d063d5e57d77735a33eac8ec944d41032fea
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="array-class"></a>array Sınıfı
Hızlandırıcı için veri taşımak için kullanılan bir veri kapsayıcısını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename value_type, int _Rank>  
friend class array;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value_type`  
 Veri öğesi türü.  
  
 `_Rank`  
 Dizi derecesini.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Array Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `array` sınıfı.|  
|[~ array yok Edicisi](#dtor)|Bozar `array` nesnesi.|  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[copy_to](#copy_to)|Dizinin içeriğini başka bir diziye kopyalar.|  
|[Veri](#data)|Bir işaretçi dizi ham verileri döndürür.|  
|[get_accelerator_view](#get_accelerator_view)|Döndürür [accelerator_view](accelerator-view-class.md) dizi burada ayrılır konumu temsil eden nesne. Bu özellik yalnızca CPU üzerinde erişilebilir.|  
|[get_associated_accelerator_view](#get_associated_accelerator_view)|İkinci alır [accelerator_view](accelerator-view-class.md) örneği oluşturmak için bir hazırlama Oluşturucu çağrıldığında bir parametre olarak geçirilen nesne `array` nesne.|  
|[get_cpu_access_type](#get_cpu_access_type)|Döndürür [access_type](concurrency-namespace-enums-amp.md#access_type) dizi. Bu yöntem yalnızca CPU üzerinde erişilebilir.|  
|[get_extent](#get_extent)|Döndürür [ölçüde](extent-class.md) dizi nesnesi.|  
|[reinterpret_as](#reinterpret_as)|Tüm öğeleri içeren tek boyutlu bir dizi döndürür `array` nesnesi.|  
|[section](#section)|Alt döndürür `array` belirtilen kaynağa ve bu, isteğe bağlı olarak, nesne belirtilen uzantı sahiptir.|  
|[view_as](#view_as)|Döndürür bir [array_view](array-view-class.md) gelen oluşturulan nesne `array` nesne.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleç std::vector&lt;value_type&gt;](#operator_vec)|Kullanan `copy(*this, vector)` örtük olarak bir std dönüştürme için::[vektör](../../../standard-library/vector-class.md) nesnesi.|  
|[operator()](#operator_call)|Parametrelerle belirtilen öğenin değerini döndürür.|  
|[[] işleci](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|  
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `array` bunu nesnesine.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[sıra sabiti](#rank)|Dizi derecesini depolar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[accelerator_view](#accelerator_view)|Alır [accelerator_view](accelerator-view-class.md) dizi burada ayrılır konumu temsil eden nesne. Bu özellik yalnızca CPU üzerinde erişilebilir.|  
|[associated_accelerator_view](#associated_accelerator_view)|İkinci alır [accelerator_view](accelerator-view-class.md) örneği oluşturmak için bir hazırlama Oluşturucu çağrıldığında bir parametre olarak geçirilen nesne `array` nesne.|  
|[cpu_access_type](#cpu_access_type)|Alır [access_type](concurrency-namespace-enums-amp.md#access_type) CPU depolama dizisinin nasıl erişebileceğinizi temsil eder.|  
|[Kapsam](#extent)|Dizi şeklini tanımlar ölçüde alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Türü `array<T,N>` yoğun ve normal temsil eder (Basit değil) *N*-Hızlandırıcı veya CPU gibi belirli bir konumda bulunan boyutlu bir dizi. Dizideki öğeler veri türünde `T`, hedef Hızlandırıcı ile uyumlu bir türde olması gerekir. Rağmen derece `N`, (, dizi türü bir parçasıdır ve statik olarak belirlenir, dizi kapsamını çalışma zamanı tarafından belirlenir ve sınıfı kullanılarak ifade `extent<N>`.  
  
 Bazı işlevler için özelleştirilmiş rağmen bir dizi boyutları, herhangi bir sayıda olabilir `array` derece bir, iki ila üç nesneleriyle. Boyut değişkeni atlarsanız, varsayılan değer 1 ' dir.  
  
 Dizi veri bitişik bellek yerleştirilir. Bir en az önemli boyutundaki farklı bellekte bitişik öğelerdir.  
  
 Derin bir kopya diziyi başka diziye kopyalandığında, yapıldığından diziler mantıksal değer türleri olduğu kabul edilir. İki dizi hiçbir zaman aynı veri'ı seçin.  
  
 `array<T,N>` Türü, çeşitli senaryolarda kullanılır:  
  
-   Veri kapsayıcısı hesaplamalar Hızlandırıcı üzerinde de kullanılabilir.  
  
-   (Ve diğer diziler kopyalamak için kullanılabilir) bellek CPU konaktaki tutmak için bir veri kapsayıcısı.  
  
-   Ana bilgisayar aygıtı kopyaları hızlı bir aracı gibi davranan bir hazırlama nesnesine.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `array`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a> ~ array 

 Bozar `array` nesnesi.  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="accelerator_view"></a> accelerator_view 

 Alır [accelerator_view](accelerator-view-class.md) dizi burada ayrılır konumu temsil eden nesne. Bu özellik yalnızca CPU üzerinde erişilebilir.  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="ctor"></a> Dizi 

 Yeni bir örneğini başlatır [array sınıfı](array-class.md). İçin varsayılan oluşturucu yok yok `array<T,N>`. Tüm oluşturucular yalnızca CPU üzerinde çalışır. Üzerinde Direct3D hedef yürütülemez.  
  
```  
explicit array(  
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);  
  
explicit array(  
    int _E0) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first, 
    _InputIterator _Src_last) restrict(cpu);
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,    
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
explicit array(  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);  
  
array(  
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av,  
    accelerator_view _Associated_Av) restrict(cpu);  
  
array(const array& _Other) restrict(cpu);  
  
array(array&& _Other) restrict(cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Associated_Av`  
 Dizi tercih edilen hedef konumunu belirten bir accelerator_view.  
  
 `_Av`  
 Bir [accelerator_view](accelerator-view-class.md) nesne dizi konumunu belirtir.  
  
 `_Cpu_access_type`  
 İstenen [access_type](concurrency-namespace-enums-amp.md#access_type) CPU dizi. Bu parametrenin varsayılan değeri olan `access_type_auto` CPU bırakarak `access_type` çalışma zamanının belirleme. Gerçek CPU `access_type` dizi aracılığıyla sorgulanabilir için `get_cpu_access_type` yöntemi.  
  
 `_Extent`  
 Her boyut bir dizinin içindeki kapsamı.  
  
 `_E0`  
 Bu bölümde kapsamını en önemli bileşenidir.  
  
 `_E1`  
 Bu bölümde kapsamını İleri-için-çoğu-önemli bileşenidir.  
  
 `_E2`  
 Bu bölümde kapsamını en az önemli bileşenidir.  
  
 `_InputIterator`  
 Giriş interator türü.  
  
 `_Src`  
 Kopyalamak için nesne için.  
  
 `_Src_first`  
 Başlangıç yineleyici kaynak kapsayıcı içine.  
  
 `_Src_last`  
 Bitiş yineleyici kaynak kapsayıcı içine.  
  
 `_Other`  
 Diğer veri kaynağı.  
  
 `_Rank`  
 Bölüm derecesini.  
  
 `value_type`  
 Kopyalanan öğelerin veri türü.  
  
##  <a name="associated_accelerator_view"></a> associated_accelerator_view 

 İkinci alır [accelerator_view](accelerator-view-class.md) örneği oluşturmak için bir hazırlama Oluşturucu çağrıldığında bir parametre olarak geçirilen nesne `array` nesne.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="copy_to"></a> copy_to 

 İçeriğini kopyalar `array` başka bir `array`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 [Array_view](array-view-class.md) kopyalamak için nesne.  
  
##  <a name="cpu_access_type"></a> cpu_access_type 

 Bu dizi için izin verilen CPU access_type alır.  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="data"></a> Veri 

 İşaretçi için ham verileri döndüren `array`.  
  
```  
value_type* data() restrict(amp, cpu);
  
const value_type* data() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi ham verileri için bir işaretçi.  
  
##  <a name="extent"></a> Kapsam 

 Alır [ölçüde](extent-class.md) şeklini tanımlayan nesne `array`.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="get_accelerator_view"></a> get_accelerator_view 

 Döndürür [accelerator_view](accelerator-view-class.md) konumu temsil eden nesnesi nerede `array` nesne ayrılır. Bu özellik yalnızca CPU üzerinde erişilebilir.  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;  
```    
  
### <a name="return-value"></a>Dönüş Değeri  
 `accelerator_view` Konumu temsil eden nesnesi nerede `array` nesne ayrılır.  
  
##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view 

 İkinci alır [accelerator_view](accelerator-view-class.md) örneği oluşturmak için bir hazırlama Oluşturucu çağrıldığında bir parametre olarak geçirilen nesne `array` nesne.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İkinci [accelerator_view](accelerator-view-class.md) hazırlama oluşturucuya nesnesi geçirildi.  
  
##  <a name="get_cpu_access_type"></a> get_cpu_access_type 

 Bu dizi için izin verilen CPU access_type döndürür.  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="get_extent"></a> get_extent 

 Döndürür [ölçüde](extent-class.md) nesnesinin `array`.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `extent` Nesnesinin `array`.  
  
##  <a name="operator_vec"></a> işleç std::vector&lt;value_type&gt; 

 Kullanan `copy(*this, vector)` dizi std::vector nesnesine örtük olarak dönüştürmek için.  
  
```  
operator std::vector<value_type>() const restrict(cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `value_type`  
 Vektör öğelerini veri türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türünde bir nesne `vector<T>` dizisi içinde yer alan verilerin bir kopyasını içerir.  
  
##  <a name="operator_call"></a> operator() 

 Parametrelerle belirtilen öğenin değerini döndürür.  
  
```  
value_type& operator() (const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator() (const index<_Rank>& _Index) cons  t restrict(amp,cpu);
  
value_type& operator() (int _I0, int _I1) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1) const restrict(amp,cpu)  ;
  
value_type& operator() (int _I0, int _I1, int _I2) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1, int _I2) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator()(int _I) restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator()(int _I) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Öğe konumu.  
  
 `_I0`  
 Bu bölümde kökeni en önemli bileşenidir.  
  
 `_I1`  
 Bu bölümde kökeni İleri-için-çoğu-önemli bileşenidir.  
  
 `_I2`  
 Bu bölümde kökeni en az önemli bileşenidir.  
  
 `_I`  
 Öğe konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parametrelerle belirtilen öğe değeri.  
  
##  <a name="operator_at"></a> [] işleci 

 Belirtilen dizindeki öğeyi döndürür.  
  
```  
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator[]  
    (const index<_Rank>& _Index) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```  
    
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Dizini.  
  
 `_I`  
 Dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizindeki öğeyi.  
  
##  <a name="operator_eq"></a> işleç = 

 Belirtilen içeriğini kopyalar `array` nesnesi.  
  
```  
array& operator= (const array& _Other) restrict(cpu);  
   
array& operator= (array&& _Other) restrict(cpu);  
 
array& operator= (  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `array` Kopyalanacak nesne.  
  
 `_Src`  
 `array` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `array` nesnesi.  
  
##  <a name="rank"></a> RANK 

 Derecesini depolar `array`.  
  
```  
static const int rank = _Rank;  
```  
## <a name="reinterpret_as"></a> reinterpret_as 

İsteğe bağlı olarak farklı bir değer türü kaynak dizi daha olabilir bir tek boyutlu array_view aracılığıyla dizi reinterprets.

### <a name="syntax"></a>Sözdizimi
``` 
template <typename _Value_type2>  
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);  
  
template <typename _Value_type2>  
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);  
``` 
  
### <a name="parameters"></a>Parametreler  
`_Value_type2` Döndürülen veri veri türü.

### <a name="return-value"></a>Dönüş Değeri
Array_view veya dizisine, ElementType ve 1'e N azaltılmış derece T reinterpreted öğe türü olan göre const array_view nesnesi.

### <a name="remarks"></a>Açıklamalar
Bazen, doğrusal, tek boyutlu bir dizi farklı bir değer türü kaynak dizi daha büyük bir olasılıkla ise çok boyutlu bir dizi görüntülemek uygundur. Bunu başarmak için bu yöntemi kullanabilirsiniz.
**Uyarı** farklı bir değer türünü kullanarak bir dizi nesnesi Reinterpreting olan olmayabilecek işlemi. Bu işlevi dikkatli bir şekilde kullanmanızı öneririz. 

Aşağıdaki kod bir örnek sağlar.

```cpp  
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...; 
array_view<float,1> v = a.reinterpret_as<float>(); 

assert(v.extent == 3*a.extent);
```  
  
##  <a name="section"></a> Bölüm 

 Alt döndürür `array` belirtilen kaynağa ve bu, isteğe bağlı olarak, nesne belirtilen uzantı sahiptir.  
  
```  
array_view<value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const index<_Rank>& _Idx) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const index<_Rank>& _Idx) const restrict(amp,cpu);
  
array_view<value_type,1> section(
    int _I0,  
    int _E0) restrict(amp,cpu);
  
array_view<const value_type,1> section(
    int _I0,  
    int _E0) const restrict(amp,cpu);
  
array_view<value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) restrict(amp,cpu);
  
array_view<const value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);
  
array_view<value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) restrict(amp,cpu);
  
array_view<const value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_E0`  
 Bu bölümde kapsamını en önemli bileşenidir.  
  
 `_E1`  
 Bu bölümde kapsamını İleri-için-çoğu-önemli bileşenidir.  
  
 `_E2`  
 Bu bölümde kapsamını en az önemli bileşenidir.  
  
 `_Ext`  
 [Ölçüde](extent-class.md) bölüm kapsamını belirten nesne. Kaynak 0'dır.  
  
 `_Idx`  
 [Dizin](index-class.md) başlangıç konumunu belirten nesne. Alt ölçüde geri kalanı ' dir.  
  
 `_I0`  
 Bu bölümde kökeni en önemli bileşenidir.  
  
 `_I1`  
 Bu bölümde kökeni İleri-için-çoğu-önemli bileşenidir.  
  
 `_I2`  
 Bu bölümde kökeni en az önemli bileşenidir.  
  
 `_Rank`  
 Bölüm derecesini.  
  
 `_Section_extent`  
 [Ölçüde](extent-class.md) bölüm kapsamını belirten nesne.  
  
 `_Section_origin`  
 [Dizin](index-class.md) başlangıç konumunu belirten nesne.  
  
 `value_type`  
 Kopyalanan öğelerin veri türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Alt döndürür `array` belirtilen kaynağa ve bu, isteğe bağlı olarak, nesne belirtilen uzantı sahiptir. Sadece `index` nesne belirtilmediyse, alt öğeleri dizinleri büyük dizinler sahip tüm öğeleri ilişkili kılavuzunda içeren `index` nesnesi.  
  
##  <a name="view_as"></a> view_as 

 Bu dizi olarak reinterprets bir [array_view](array-view-class.md) , farklı bir sıra.  
  
```  
template <int _New_rank>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

 
template <int _New_rank>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_New_rank`  
 Derecesini `extent` nesnesini parametre olarak geçirildi.  
  
 `_View_extent`  
 Yeni oluşturmak için kullanılan ölçüde [array_view](array-view-class.md) nesnesi.  
  
 `value_type`  
 Veri türü hem özgün öğeleri `array` nesne ve döndürülen `array_view` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 [Array_view](array-view-class.md) oluşturulan nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
