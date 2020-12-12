---
description: 'Hakkında daha fazla bilgi edinin: array_view sınıfı'
title: array_view Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- array_view class
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
ms.openlocfilehash: 170eb51a437fd56b9b9e74bb22e5b84d3478b4bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247884"
---
# <a name="array_view-class"></a>array_view Sınıfı

Başka bir kapsayıcıda tutulan verilerin üzerinde N boyutlu bir görünümü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
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

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Nesnedeki öğelerin veri türü `array_view` .

*_Rank*<br/>
`array_view`Nesnenin sıralaması.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[array_view Oluşturucusu](#ctor)|`array_view` sınıfının yeni bir örneğini başlatır. İçin varsayılan Oluşturucu yoktur `array<T,N>` . Tüm oluşturucular yalnızca CPU üzerinde çalışacak şekilde kısıtlanır ve bir Direct3D hedefi üzerinde yürütülemez.|
|[~ array_view yok edici](#ctor)|Nesneyi yok eder `array_view` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[copy_to](#copy_to)|`array_view`Çağırarak nesnenin içeriğini belirtilen hedefe kopyalar `copy(*this, dest)` .|
|[data](#data)|Ham verilerine yönelik bir işaretçi döndürür `array_view` .|
|[discard_data](#discard_data)|Bu görünümü temel alan geçerli verileri atar.|
|[get_extent](#get_extent)|Array_view nesnesinin kapsam nesnesini döndürür.|
|[get_ref](#get_ref)|Dizinli öğeye bir başvuru döndürür.|
|[get_source_accelerator_view](#get_source_accelerator_view)|Veri kaynağının bulunduğu [accelerator_view](accelerator-view-class.md) döndürür `array_view` .|
|[yenileyebilir](#refresh)|Nesnesine, `array_view` ilişkili belleğinin arabirim dışında değiştirildiğini bildirir `array_view` . Bu yönteme yapılan bir çağrı, tüm önbelleğe alınan bilgileri eski işler.|
|[reinterpret_as](#reinterpret_as)|Nesnedeki tüm öğeleri içeren tek boyutlu bir dizi döndürür `array_view` .|
|[kısmı](#section)|`array_view`Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu nesnenin alt bölümünü döndürür.|
|[synchronize](#synchronize)|Nesnesinde yapılan tüm değişiklikleri `array_view` kaynak verilerine geri eşitler.|
|[synchronize_async](#synchronize_async)|Nesnesinde yapılan tüm değişiklikleri zaman uyumsuz `array_view` olarak kaynak verilerine geri eşitler.|
|[synchronize_to](#synchronize_to)|Nesnede yapılan tüm değişiklikleri `array_view` belirtilen [accelerator_view](accelerator-view-class.md)eşitler.|
|[synchronize_to_async](#synchronize_to_async)|Nesne üzerinde yapılan değişiklikleri zaman uyumsuz `array_view` olarak belirtilen [accelerator_view](accelerator-view-class.md)eşitler.|
|[view_as](#view_as)|`array_view`Bu nesnenin verilerini kullanarak farklı bir dereceye sahip bir nesne oluşturur `array_view` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator ()](#operator_call)|Parametresi veya parametreleri tarafından belirtilen öğenin değerini döndürür.|
|[işlecinde\[\]](#operator_at)|Parametreler tarafından belirtilen öğeyi döndürür.|
|[işleç =](#operator_eq)|Belirtilen `array_view` nesnenin içeriğini buna kopyalar.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank)|Nesnenin derecesini depolar `array_view` .|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[genişliğini](#extent)|`extent`Nesnenin şeklini tanımlayan nesneyi alır `array_view` .|
|[source_accelerator_view](#source_accelerator_view)|Veri kaynağının [bulunduğu accelerator_view](accelerator-view-class.md) alır `array_view`|
|[value_type](#value_type)|`array_view`Ve bağlantılı dizinin değer türü.|

## <a name="remarks"></a>Açıklamalar

Sınıfı, bir `array_view` [dizi](array-class.md) nesnesinde veya bir nesnenin alt bölümünde bulunan verilere ilişkin bir görünümü temsil eder `array` .

`array_view`Kaynak verilerin bulunduğu nesneye (yerel olarak) veya farklı bir Hızlandırıcı ya da bir tutarlı etki alanına (uzaktan) erişebilirsiniz. Nesneye uzaktan eriştiğinizde, görünümler, gerektiği şekilde kopyalanır ve önbelleğe alınır. Otomatik önbelleğe almanın etkileri haricinde `array_view` nesneler, nesnelere benzer bir performans profiline sahiptir `array` . Verilerle görünümler aracılığıyla eriştiğinizde küçük bir performans cezası vardır.

Üç uzaktan kullanım senaryosu vardır:

- Bir Hızlandırıcı 'ya [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) çağrısı ve hızlandırıcıda erişilen bir araç tarafından bir sistem belleği işaretçisine bir görünüm geçirilir.

- Hızlandırıcı üzerinde bulunan bir dizi için bir görünüm, `parallel_for_each` başka bir hızlandırıcının çağrısı yoluyla geçirilir ve buna erişilir.

- Bir hızlandırıcıda bulunan bir diziye yönelik bir görünüme CPU üzerinden erişilir.

Bu senaryolardan herhangi birinde, başvurulan görünümler çalışma zamanı tarafından uzak konuma kopyalanır ve nesneye yapılan çağrılar tarafından değiştirilirse `array_view` , yerel konuma geri kopyalanır. Çalışma zamanı değişiklikleri geri kopyalama sürecini iyileştirebilirler, yalnızca değiştirilen öğeleri kopyalayabilir ya da değişmeyen bölümleri kopyalayabilir. `array_view`Bir veri kaynağındaki çakışan nesnelerin, uzak bir konumda bilgi tutarlılığını sürdürmek garanti edilmez.

Aynı veri kaynağına herhangi bir çok iş parçacıklı erişimi eşitlemeniz gerekir.

Çalışma zamanı, nesnelerdeki verilerin önbelleğe alınmasına ilişkin aşağıdaki garantisi verir `array_view` :

- Bir nesne ve program sırasındaki bir nesne için tüm iyi eşitlenmiş erişimler `array` , `array_view` bir seri durumunda (ilişki öncesinde) bir seri hale gelir.

- `array_view`Tek bir nesne üzerinde aynı hızlandırıcıda bulunan örtüşen nesnelere yönelik tüm iyi eşitlenmiş `array` erişimler, nesne üzerinden diğer ad sağlar `array` . Bu kişiler, bir toplam meydana gelir ve program sırasına udan önce ilişkiye göre yapılır. Önbelleğe alma yok. `array_view`Nesneler farklı Hızlandırıcılar üzerinde yürütüle, erişim sırası tanımsızdır ve bir yarış durumu oluşturur.

`array_view`Sistem belleğindeki bir işaretçi kullanarak bir nesne oluşturduğunuzda, Görünüm `array_view` nesnesini yalnızca işaretçi aracılığıyla değiştirmeniz gerekir `array_view` . Alternatif olarak, `refresh()` `array_view` temel alınan yerel bellek, nesne yerine doğrudan değiştirilmişse, sistem işaretçisine eklenen nesnelerden birini çağırmanız gerekir `array_view` .

İki eylem, `array_view` nesneyi temeldeki yerel belleğin değiştirildiğini ve hızlandırıcıda bulunan tüm kopyaların güncel olduğunu bildirir. Bu yönergeleri izlerseniz, işaretçi tabanlı görünümler, veri paralel dizilerinin görünümlerine göre belirtilenlerle aynıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Array_view_shape`

`_Array_view_base`

`array_view`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="array_view"></a><a name="dtor"></a> ~ array_view

Nesneyi yok eder `array_view` .

```cpp
~array_view()restrict(amp,cpu);
```

## <a name="array_view"></a><a name="ctor"></a> array_view

`array_view` sınıfının yeni bir örneğini başlatır.

```cpp
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

*_Arr_type*<br/>
Verilerin sağlandığı bir C stili dizinin öğe türü.

*_Container*<br/>
Ve üyelerini destekleyen doğrusal bir kapsayıcı belirtmesi gereken bir şablon bağımsız `data()` değişkeni `size()` .

*_E0*<br/>
Bu bölümün kapsamının en önemli bileşeni.

*_E1*<br/>
Bu bölümün kapsamının en çok önemli bir bileşeni.

*_E2*<br/>
Bu bölümün kapsamının en az önemli bileşeni.

*_Extent*<br/>
Bu boyutun her boyutunun kapsamı `array_view` .

*_Other*<br/>
Yeni ' nin başlatıldığı türdeki nesne `array_view<T,N>` `array_view` .

*_Size*<br/>
Verilerin sağlandığı C stili dizinin boyutu.

*_Src*<br/>
Yeni diziye Kopyalanacak kaynak verilere yönelik bir işaretçi.

## <a name="copy_to"></a><a name="copy_to"></a> copy_to

`array_view`Çağırarak nesnenin içeriğini belirtilen hedef nesneye kopyalar `copy(*this, dest)` .

```cpp
void copy_to(
    array<value_type, _Rank>& _Dest) const;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Kopyalanacak nesne.

## <a name="data"></a><a name="data"></a> verileri

Ham verilerine yönelik bir işaretçi döndürür `array_view` .

```cpp
value_type* data() const restrict(amp,
    cpu);

const value_type* data() const restrict(amp,
    cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Ham verilerinin bir işaretçisi `array_view` .

## <a name="discard_data"></a><a name="discard_data"></a> discard_data

Bu görünümü temel alan geçerli verileri atar. Bu, görünümün geçerli içeriğinin eriştiği hedefe kopyalanmasını önlemek için kullanılan çalışma zamanına yönelik bir iyileştirme ipucdur `accelerator_view` ve var olan içerik gerekmiyorsa kullanımı önerilir. Bu yöntem bir restrict (amp) bağlamında kullanıldığında op değildir

```cpp
void discard_data() const restrict(cpu);
```

## <a name="extent"></a><a name="extent"></a> genişliğini

`extent`Nesnenin şeklini tanımlayan nesneyi alır `array_view` .

```cpp
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

## <a name="get_extent"></a><a name="get_extent"></a> get_extent

Nesnenin [kapsam](extent-class.md) nesnesini döndürür `array_view` .

```cpp
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```

### <a name="return-value"></a>Dönüş Değeri

`extent` `array_view` Nesnenin nesnesi

## <a name="get_ref"></a><a name="get_ref"></a> get_ref

_Index tarafından dizinlenen öğeye bir başvuru alın. CPU üzerindeki array_view erişmek için diğer dizin oluşturma işleçlerinin aksine, bu yöntem bu array_view içeriğini CPU 'ya örtük olarak eşitlemez. Uzak bir konumdaki array_view erişildikten veya bu array_view ilişkili bir kopyalama işlemi gerçekleştirdikten sonra, bu yöntemi çağırmadan önce array_view CPU 'ya açıkça eşitlemeden sorumludur. Bunun yapılmaması, tanımsız davranışa neden olur.

```cpp
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizin.

### <a name="return-value"></a>Dönüş Değeri

_Index tarafından dizinlenen öğeye başvuru

## <a name="get_source_accelerator_view"></a><a name="get_source_accelerator_view"></a> get_source_accelerator_view

Array_view veri kaynağının bulunduğu accelerator_view döndürür. Array_view bir veri kaynağına sahip değilse, bu API bir runtime_exception oluşturur

```cpp
accelerator_view get_source_accelerator_view() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator"></a><a name="operator_call"></a> operator ()

Parametresi veya parametreleri tarafından belirtilen öğenin değerini döndürür.

```cpp
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

*_Index*<br/>
Öğenin konumu.

*_I0*<br/>
İlk boyuttaki dizin.

*_I1*<br/>
İkinci boyuttaki dizin.

*_I2*<br/>
Üçüncü boyuttaki dizin.

*_I*<br/>
Öğenin konumu.

### <a name="return-value"></a>Dönüş Değeri

Parametresi veya parametreleri tarafından belirtilen öğenin değeri.

## <a name="operator"></a><a name="operator_at"></a> operator []

Parametreler tarafından belirtilen öğeyi döndürür.

```cpp
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizin.

*_I*<br/>
Dizin.

### <a name="return-value"></a>Dönüş Değeri

Dizindeki öğenin değeri veya `array_view` en önemli boyutta bir tahmin.

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Belirtilen `array_view` nesnenin içeriğini buna kopyalar.

```cpp
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
`array_view`Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu nesneye bir başvuru `array_view` .

## <a name="rank"></a><a name="rank"></a> sırası

Nesnenin derecesini depolar `array_view` .

```cpp
static const int rank = _Rank;
```

## <a name="refresh"></a><a name="refresh"></a> yenileyebilir

Nesnesine, `array_view` ilişkili belleğinin arabirim dışında değiştirildiğini bildirir `array_view` . Bu yönteme yapılan bir çağrı, tüm önbelleğe alınan bilgileri eski işler.

```cpp
void refresh() const restrict(cpu);
```

## <a name="reinterpret_as"></a><a name="reinterpret_as"></a> reinterpret_as

Array_view, bir seçenek olarak kaynak array_view farklı bir değer türüne sahip olabilen tek boyutlu bir array_view üzerinden yeniden yorumlar.

### <a name="syntax"></a>Sözdizimi

```cpp
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

*_Value_type2*<br/>
Yeni nesnenin veri türü `array_view` .

### <a name="return-value"></a>Dönüş Değeri

Bir `array_view` nesne veya `array_view` öğesine dayalı bir const nesnesi `array_view` , öğe türü ' den `T` ' e dönüştürülüp `_Value_type2` ve *N* ' den 1 ' e indirilir.

### <a name="remarks"></a>Açıklamalar

Bazen çok boyutlu bir diziyi, kaynak diziden farklı bir değer türüne sahip olabilecek doğrusal, tek boyutlu bir dizi olarak görüntülemek yararlıdır. Bu yöntemi kullanarak bunu bir üzerinde elde edebilirsiniz `array_view` .

**Uyarı** Array_view nesnesini farklı bir değer türü kullanarak yeniden yorumlamak güvenli olmayabilecek bir işlemdir. Bu işlev dikkatli kullanılmalıdır.

Aşağıda bir örnek verilmiştir:

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

## <a name="section"></a><a name="section"></a> kısmı

`array_view`Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu nesnenin alt bölümünü döndürür.

```cpp
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

*_E0*<br/>
Bu bölümün kapsamının en önemli bileşeni.

*_E1*<br/>
Bu bölümün kapsamının en çok önemli bir bileşeni.

*_E2*<br/>
Bu bölümün kapsamının en az önemli bileşeni.

*_Ext*<br/>
Bölüm kapsamını belirten [uzantı](extent-class.md) nesnesi. Kaynak 0 ' dır.

*_Idx*<br/>
Kaynak konumunu belirten [Dizin](index-class.md) nesnesi. Alt bölüm, kapsamın geri kalanı olur.

*_I0*<br/>
Bu bölümün kaynağının en önemli bileşeni.

*_I1*<br/>
Bu bölümün kaynağının en çok önemli bileşeni.

*_I2*<br/>
Bu bölümün kaynağının en az önemli bileşeni.

*_Rank*<br/>
Bölümün derecesi.

*_Section_extent*<br/>
Bölüm kapsamını belirten [uzantı](extent-class.md) nesnesi.

*_Section_origin*<br/>
Kaynak konumunu belirten [Dizin](index-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`array_view`Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu nesnenin alt bölümü. Yalnızca `index` nesne belirtildiğinde alt bölüm, ilişkili kapsamın nesne içindeki öğelerin dizinlerinden daha büyük dizinlere sahip olan tüm öğeleri içerir `index` .

## <a name="source_accelerator_view"></a><a name="source_accelerator_view"></a> source_accelerator_view

Bu array_view ilişkilendirildiği kaynak accelerator_view alır.

```cpp
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;
```

## <a name="synchronize"></a><a name="synchronize"></a> yapacak

Nesnesinde yapılan tüm değişiklikleri `array_view` kaynak verilerine geri eşitler.

```cpp
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize() const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Access_type*<br/>
Hedef [accelerator_view](accelerator-view-class.md)amaçlanan [access_type](concurrency-namespace-enums-amp.md#access_type) . Bu parametrenin varsayılan değeri vardır `access_type_read` .

## <a name="synchronize_async"></a><a name="synchronize_async"></a> synchronize_async

Nesnesinde yapılan tüm değişiklikleri zaman uyumsuz `array_view` olarak kaynak verilerine geri eşitler.

```cpp
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_async() const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Access_type*<br/>
Hedef [accelerator_view](accelerator-view-class.md)amaçlanan [access_type](concurrency-namespace-enums-amp.md#access_type) . Bu parametrenin varsayılan değeri vardır `access_type_read` .

### <a name="return-value"></a>Dönüş Değeri

İşlemin tamamlanmasını beklemek için bir sonraki.

## <a name="synchronize_to"></a><a name="synchronize_to"></a> synchronize_to

Bu array_view yapılan tüm değişiklikleri belirtilen accelerator_view eşitler.

```cpp
void synchronize_to(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Accl_view*<br/>
Hedef accelerator_view eşitlenecek.

*_Access_type*<br/>
Hedef accelerator_view istenen access_type. Bu parametrenin varsayılan değeri access_type_read vardır.

## <a name="synchronize_to_async"></a><a name="synchronize_to_async"></a> synchronize_to_async

Bu array_view yapılan değişiklikleri zaman uyumsuz olarak belirtilen accelerator_view eşitler.

```cpp
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Accl_view*<br/>
Hedef accelerator_view eşitlenecek.

*_Access_type*<br/>
Hedef accelerator_view istenen access_type. Bu parametrenin varsayılan değeri access_type_read vardır.

### <a name="return-value"></a>Dönüş Değeri

İşlemin tamamlanmasını beklemek için bir sonraki.

## <a name="value_type"></a><a name="value_type"></a> value_type

Array_view ve bağlantılı dizinin değer türü.

```cpp
typedef typenamevalue_type value_type;
```

## <a name="view_as"></a><a name="view_as"></a> view_as

Bunu `array_view` `array_view` farklı bir derece olarak yeniden yorumlar.

```cpp
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

*_New_rank*<br/>
Yeni `array_view` nesnenin sıralaması.

*_View_extent*<br/>
Yeniden şekillendirme `extent` .

*value_type*<br/>
Hem özgün [dizi](array-class.md) nesnesi hem de döndürülen nesne içindeki öğelerin veri türü `array_view` .

### <a name="return-value"></a>Dönüş Değeri

`array_view`Oluşturulan nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
