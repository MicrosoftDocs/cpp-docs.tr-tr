---
title: array_view sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- array_view
- AMP/array_view
- AMP/Concurrency::array_view::array_view
- AMP/Concurrency::array_view::copy_to
- AMP/Concurrency::array_view::data
- AMP/Concurrency::array_view::discard_data
- AMP/Concurrency::array_view::get_extent
- AMP/Concurrency::array_view::get_ref
- AMP/Concurrency::array_view::get_source_accelerator_view
- AMP/Concurrency::array_view::refresh
- AMP/Concurrency::array_view::reinterpret_as
- AMP/Concurrency::array_view::section
- AMP/Concurrency::array_view::synchronize
- AMP/Concurrency::array_view::synchronize_async
- AMP/Concurrency::array_view::synchronize_to
- AMP/Concurrency::array_view::synchronize_to_async
- AMP/Concurrency::array_view::view_as
- AMP/Concurrency::array_view::rank
- AMP/Concurrency::array_view::extent
- AMP/Concurrency::array_view::source_accelerator_view
- AMP/Concurrency::array_view::value_type
dev_langs:
- C++
helpviewer_keywords:
- array_view class
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e53b4927b102fc64a32f73ca5be78e71954b45f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="arrayview-class"></a>array_view Sınıfı
Başka bir kapsayıcıda tutulan verileri üzerinden N boyutlu bir görünümü gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <
    typename value_type,  
    int _Rank = 1  
>  
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
 
template <
    typename value_type,  
    int _Rank  
>  
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value_type`  
 Öğeleri veri türü `array_view` nesnesi.  
  
 `_Rank`  
 Derecesini `array_view` nesnesi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[array_view Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `array_view` sınıfı. İçin varsayılan oluşturucu yok yok `array<T,N>`. Tüm oluşturucular yalnızca CPU üzerinde çalıştırmak için kısıtlı ve Direct3D hedefte yürütülemez.|  
|[~ array_view yok Edicisi](#ctor)|Bozar `array_view` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[copy_to](#copy_to)|İçeriğini kopyalar `array_view` çağırarak belirtilen hedef nesnesine `copy(*this, dest)`.|  
|[Veri](#data)|İşaretçi için ham verileri döndüren `array_view`.|  
|[discard_data](#discard_data)|Bu görünüm için temel alınan geçerli verileri atar.|  
|[get_extent](#get_extent)|Array_view nesnesinin ölçüde döndürür.|  
|[get_ref](#get_ref)|Dizinli öğesine bir başvuru döndürür.|  
|[get_source_accelerator_view](#get_source_accelerator_view)|Döndürür [accelerator_view](accelerator-view-class.md) burada veri kaynağı `array_view` bulunur.|  
|[Yenileme](#refresh)|Bildirir `array_view` bağlı bellek dışında değiştirildi nesne `array_view` arabirimi. Bu yöntem çağrısı önbelleğe alınan tüm bilgileri eski işler.|  
|[reinterpret_as](#reinterpret_as)|Tüm öğeleri içeren tek boyutlu bir dizi döndürür `array_view` nesnesi.|  
|[section](#section)|Alt döndürür `array_view` belirtilen kaynağa ve bu, isteğe bağlı olarak, nesne belirtilen uzantı sahiptir.|  
|[synchronize](#synchronize)|İçin yapılan tüm değişiklikler eşitler `array_view` nesne kaynak verileri dön.|  
|[synchronize_async](#synchronize_async)|Zaman uyumsuz olarak yapılan herhangi bir değişiklik eşitler `array_view` nesne kaynak verileri dön.|  
|[synchronize_to](#synchronize_to)|İçin yapılan tüm değişiklikler eşitler `array_view` belirtilen nesneye [accelerator_view](accelerator-view-class.md).|  
|[synchronize_to_async](#synchronize_to_async)|Zaman uyumsuz olarak yapılan herhangi bir değişiklik eşitler `array_view` belirtilen nesneye [accelerator_view](accelerator-view-class.md).|  
|[view_as](#view_as)|Üreten bir `array_view` bu kullanarak farklı bir sıra nesnesinin `array_view` nesnesinin verileri.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator()](#operator_call)|Parametresi veya parametreler tarafından belirtilen öğenin değerini döndürür.|  
|[[] işleci](#operator_at)|Parametrelerle belirtilen öğeyi döndürür.|  
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `array_view` bunu nesnesine.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[sıra sabiti](#rank)|Derecesini depolar `array_view` nesnesi.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Kapsam](#extent)|Alır `extent` şeklini tanımlayan nesne `array_view` nesne.|  
|[source_accelerator_view](#source_accelerator_view)|Alır [accelerator_view](accelerator-view-class.md) burada veri kaynağı `array_view` bulunur|  
|[value_type](#value_type)|Değer türü `array_view` ve ilişkili dizi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `array_view` Sınıfı temsil eder, bulunan verileri görünüme bir [dizi](array-class.md) nesne veya alt bir `array` nesnesi.  
  
 Erişebileceğiniz `array_view` veri kaynağını (yerel) bulunduğu veya farklı bir Hızlandırıcı veya tutarlılık etki alanı nesnesi (uzaktan). Nesne uzaktan eriştiğinizde, görünümleri kopyalanır ve gerektiği şekilde önbelleğe alınır. Otomatik olarak önbelleğe alma, etkilerini dışında `array_view` nesneler benzer bir performans profili sahip `array` nesneleri. Bulunmaktadır küçük performans veri görünümleri aracılığıyla eriştiğinizde.  
  
 Üç uzaktan kullanım senaryoları şunlardır:  
  
-   Bir sistem bellek işaretçisi görünümüne yoluyla geçirilen bir [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) çağırmak için Hızlandırıcı ve Hızlandırıcı üzerinde erişilebilir.  
  
-   Hızlandırıcı üzerinde bulunan bir dizi görünümüne yoluyla geçirilen bir `parallel_for_each` çağırmak için başka bir Hızlandırıcı ve orada erişilir.  
  
-   Hızlandırıcı üzerinde bulunan bir dizi görünümüne CPU üzerinde erişilebilir.  
  
 Bu senaryoların herhangi birinde başvurulan görünümleri çalışma zamanı tarafından uzak bir konuma kopyalanır ve yapılan çağrılar tarafından değiştirilirse `array_view` nesnesi, yerel konuma kopyalanır. Çalışma zamanı değişiklikleri geri kopyalama işlemi en iyi duruma, yalnızca değiştirilen öğeler kopyalamak veya değişmeden bölümleri ayrıca kopyalamak. Çakışan `array_view` nesneleri bir veri kaynağı üzerinde uzak bir konumdaki tutarlılığını korumak için garanti edilmez.  
  
 Aynı veri kaynağı için birden çok iş parçacıklı herhangi bir erişim eşitlemeniz gerekir.  
  
 Çalışma zamanı verileri önbelleğe alma ile ilgili aşağıdaki garanti yapar `array_view` nesneler:  
  
-   Tüm iyi eşitlenmiş erişimin bir `array` nesne ve bir `array_view` nesnesinde bu program sırayla uyma seri olur-ilişki önce.  
  
-   Çakışan için tüm iyi eşitlenmiş erişimler `array_view` tek bir aynı Hızlandırıcı nesnelerde `array` nesne olan diğer aracılığıyla `array` nesnesi. Toplam anlamına oluşur-program sipariş obeys ilişki önce. Önbelleğe alma yoktur. Varsa `array_view` nesneler üzerinde farklı Hızlandırıcıları yürütme, erişim sırasını, bir yarış durumu oluşturma, tanımlı değil.  
  
 Oluştururken bir `array_view` sistem belleğini bir işaretçisi kullanılarak nesne görünümü değiştirmeniz gerekir `array_view` yalnızca nesnesi `array_view` işaretçi. Alternatif olarak, çağırmalısınız `refresh()` birinde `array_view` arka plandaki yerel bellek doğrudan yerine aracılığıyla değiştirilirse, sistem işaretçisine bağlı olan nesneleri `array_view` nesnesi.  
  
 Her iki işlem bildirir `array_view` arka plandaki yerel belleği dönüştürülür ve Hızlandırıcı üzerinde bulunan tüm kopyaları güncel nesne. Aşağıdaki yönergeleri izleyin, işaretçi tabanlı görünümleri verileri paralel diziler görünümlerine sağlanan için aynıdır.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Array_view_shape`  
  
 `_Array_view_base`  
  
 `array_view`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="dtor"></a> ~ array_view 

 Bozar `array_view` nesnesi.  
  
```  
~array_view()restrict(amp,cpu);
```  
  
##  <a name="ctor"></a> array_view 

 Yeni bir örneğini başlatır `array_view` sınıfı.  
  
```  
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view& _Other)restrict(amp,cpu);

 
explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    _Container& _Src) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _Container& _Src);

 
explicit array_view(
    int _E0,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const _Container& _Src) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    const _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const _Container& _Src);

 
array_view(
    int _E0,  
    const value_type* _Src)restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    const value_type* _Src) restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const value_type* _Src) restrict(amp,cpu);

 
```  
  
### <a name="parameters"></a>Parametreler  
 `_Arr_type`  
 İçinden verileri sağlanır C tarzı dizi öğesi türü.  
  
 `_Container`  
 Destekleyen doğrusal bir kapsayıcı belirtmelisiniz şablon bağımsız değişken `data()` ve `size()` üyeleri.  
  
 `_E0`  
 Bu bölümde kapsamını en önemli bileşenidir.  
  
 `_E1`  
 Bu bölümde kapsamını İleri-için-çoğu-önemli bileşenidir.  
  
 `_E2`  
 Bu bölümde kapsamını en az önemli bileşenidir.  
  
 `_Extent`  
 Bu her boyut içindeki kapsamı `array_view`.  
  
 `_Other`  
 Türünde bir nesne `array_view<T,N>` yeni başlatmak üzere `array_view`.  
  
 `_Size`  
 İçinden verileri sağlanır C türü bir dizi büyüklüğü.  
  
 `_Src`  
 Yeni diziye Kopyalanacak kaynak verileri için bir işaretçi.  
  
##  <a name="copy_to"></a> copy_to 

 İçeriğini kopyalar `array_view` çağırarak belirtilen hedef nesnesini `copy(*this, dest)`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const;

 
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>Parametreler  
 `_Dest`  
 Kopyalamak için nesne.  
  
##  <a name="data"></a> Veri 

 İşaretçi için ham verileri döndüren `array_view`.  
  
```  
value_type* data() const restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ham verileri için bir işaretçi `array_view`.  
  
##  <a name="discard_data"></a> discard_data 

 Bu görünüm için temel alınan geçerli verileri atar. Geçerli görünümü içeriğini bir hedefe kopyalama önlemek için kullanılan çalışma zamanı için bir en iyi duruma getirme ipucu budur `accelerator_view` üzerinde erişilen ve varolan içeriği gerekmiyorsa, kullanılması önerilir. Bu yöntem bir no-restrict(amp) bağlamında kullanıldığında op kullanılır  
  
```  
void discard_data() const restrict(cpu);
```  
  
##  <a name="extent"></a> Kapsam 

 Alır `extent` şeklini tanımlayan nesne `array_view` nesne.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="get_extent"></a> get_extent 

 Döndürür [ölçüde](extent-class.md) nesnesinin `array_view` nesnesi.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `extent` Nesnesinin `array_view` nesnesi  
  
##  <a name="get_ref"></a> get_ref 

 _Index tarafından dizine öğesi başvurusu alın. Array_view CPU üzerinde erişmek için diğer dizin işleçleri, bu yöntem bu array_view's içeriği CPU'ya örtük olarak eşitlenmez. Uzak bir konumdaki array_view erişme veya bu array_view içeren bir kopyalama işlemi gerçekleştirme sonra kullanıcılar bu yöntemi çağırmadan önce CPU'ya array_view açıkça eşitlemeye sorumludur. Bunun Sağlanamaması tanımsız davranışa neden olur.  
  
```  
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 _Index tarafından dizine öğesine başvuru  
  
##  <a name="get_source_accelerator_view"></a> get_source_accelerator_view 

 Accelerator_view array_view veri kaynağı bulunduğu döndürür. Array_view bir veri kaynağına sahip değilse bu API bir runtime_exception oluşturur.  
  
```  
accelerator_view get_source_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="operator_call"></a> operator() 

 Parametresi veya parametreler tarafından belirtilen öğenin değerini döndürür.  
  
```  
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Öğe konumu.  
  
 `_I0`  
 İlk boyuttaki dizini.  
  
 `_I1`  
 İkinci boyuttaki dizini.  
  
 `_I2`  
 Üçüncü boyuttaki dizini.  
  
 `_I`  
 Öğe konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parametresi veya parametreler tarafından belirtilen öğenin değerini.  
  
##  <a name="operator_at"></a> [] işleci 

 Parametrelerle belirtilen öğeyi döndürür.  
  
```  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

 
value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Dizini.  
  
 `_I`  
 Dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizininde bulunan öğe değerini veya bir `array_view` en önemli boyuta göre öngörülen.  
  
##  <a name="operator_eq"></a> işleç = 

 Belirtilen içeriğini kopyalar `array_view` bu bir nesne.  
  
```  
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

 
array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `array_view` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `array_view` nesnesi.  
  
##  <a name="rank"></a> RANK 

 Derecesini depolar `array_view` nesnesi.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="refresh"></a> Yenileme 

 Bildirir `array_view` bağlı bellek dışında değiştirildi nesne `array_view` arabirimi. Bu yöntem çağrısı önbelleğe alınan tüm bilgileri eski işler.  
  
```  
void refresh() const restrict(cpu);
```  
## <a name="reinterpret_as"></a> reinterpret_as 

Array_view olabilen bir seçenek olarak kaynak array_view daha farklı bir değer türü tek boyutlu bir array_view aracılığıyla reinterprets.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template <  
    typename _Value_type2  
>  
array_view< _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);  
  
template <  
    typename _Value_type2  
>  
array_view<const _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Value_type2`  
 Yeni veri türünü `array_view` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `array_view` nesnesi veya bir const `array_view` bunu temel alarak nesne `array_view`, gelen dönüştürülen bir öğe türüne sahip `T` için `_Value_type2`, ve gelen derecesini azaltılmış *N* 1.  
  
### <a name="remarks"></a>Açıklamalar  
 Bazen çok boyutlu bir dizi farklı bir değer türü kaynak dizi daha olabilir bir doğrusal, tek boyutlu dizi olarak görüntülemek uygundur. Bu üzerinde gerçekleştirebilirsiniz bir `array_view` bu yöntemi kullanarak.  
  
**Uyarı** Reinterpeting farklı bir değer türü kullanarak array_view nesne olan olmayabilecek işlemi. Bu işlevi dikkatli kullanılmalıdır.  
  
 Örnek buradadır:  
  
```cpp  
struct RGB { float r; float g; float b; };  
  
array<RGB,3>  a = ...;   
array_view<float,1> v = a.reinterpret_as<float>();   
  
assert(v.extent == 3*a.extent);  
```  
    
##  <a name="section"></a> Bölüm 

 Alt döndürür `array_view` belirtilen kaynağa ve bu, isteğe bağlı olarak, nesne belirtilen uzantı sahiptir.  
  
```  
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _E0) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);

 
array_view section(
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
  
### <a name="return-value"></a>Dönüş Değeri  
 Alt `array_view` belirtilen kaynağa ve bu, isteğe bağlı olarak, nesne belirtilen uzantı sahiptir. Sadece `index` nesne belirtilmediyse, alt öğeleri dizinleri büyük dizinler olan tüm ilişkili ölçüde öğeler içerir `index` nesnesi.  
  
##  <a name="source_accelerator_view"></a> source_accelerator_view 

 Bu array_view ile ilişkili kaynak accelerator_view alır.  
  
```  
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;  
```  
  
##  <a name="synchronize"></a> Eşitleme 

 İçin yapılan tüm değişiklikler eşitler `array_view` nesne kaynak verileri dön.  
  
```  
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize() const restrict(cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Access_type`  
 İstenen [access_type](concurrency-namespace-enums-amp.md#access_type) hedefte [accelerator_view](accelerator-view-class.md). Bu parametrenin varsayılan değeri olan `access_type_read`.  
  
##  <a name="synchronize_async"></a> synchronize_async 

 Zaman uyumsuz olarak yapılan herhangi bir değişiklik eşitler `array_view` nesne kaynak verileri dön.  
  
```  
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_async() const restrict(cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Access_type`  
 İstenen [access_type](concurrency-namespace-enums-amp.md#access_type) hedefte [accelerator_view](accelerator-view-class.md). Bu parametrenin varsayılan değeri olan `access_type_read`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlemin tamamlanmasını bekleyin alacağı gelecek.  
  
##  <a name="synchronize_to"></a> synchronize_to 

 Bu array_view belirtilen accelerator_view için yapılan tüm değişiklikleri eşitler.  
  
```  
void synchronize_to(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Accl_view`  
 Eşitlemek için hedef accelerator_view.  
  
 `_Access_type`  
 Hedef accelerator_view üzerinde istenen access_type. Bu parametre access_type_read varsayılan değerine sahip.  
  
##  <a name="synchronize_to_async"></a> synchronize_to_async 

 Zaman uyumsuz olarak bu array_view belirtilen accelerator_view için yapılan tüm değişiklikleri eşitler.  
  
```  
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Accl_view`  
 Eşitlemek için hedef accelerator_view.  
  
 `_Access_type`  
 Hedef accelerator_view üzerinde istenen access_type. Bu parametre access_type_read varsayılan değerine sahip.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlemin tamamlanmasını bekleyin alacağı gelecek.  
  
##  <a name="value_type"></a> value_type 

 Array_view ve ilişkili dizi değer türü.  
  
```  
typedef typenamevalue_type value_type;  
```  
  
##  <a name="view_as"></a> view_as 

 Bu reinterprets `array_view` olarak bir `array_view` , farklı bir sıra.  
  
```  
template <
    int _New_rank  
>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

 
template <
    int _New_rank  
>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_New_rank`  
 Yeni derecesini `array_view` nesnesi.  
  
 `_View_extent`  
 Yeniden şekillendirmek `extent`.  
  
 `value_type`  
 Veri türü hem özgün öğeleri [dizi](array-class.md) nesne ve döndürülen `array_view` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `array_view` Oluşturulan nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
