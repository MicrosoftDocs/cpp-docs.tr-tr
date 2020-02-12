---
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
ms.openlocfilehash: 2aef75eedcde2a2064fe12815d9afd21fee2c293
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127143"
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
`array_view` nesnesindeki öğelerin veri türü.

*_Rank*<br/>
`array_view` nesnesinin sıralaması.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[array_view Oluşturucusu](#ctor)|`array_view` sınıfının yeni bir örneğini başlatır. `array<T,N>`için varsayılan oluşturucu yok. Tüm oluşturucular yalnızca CPU üzerinde çalışacak şekilde kısıtlanır ve bir Direct3D hedefi üzerinde yürütülemez.|
|[~ array_view yok edici](#ctor)|`array_view` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[copy_to](#copy_to)|`array_view` nesnesinin içeriğini `copy(*this, dest)`çağırarak belirtilen hedefe kopyalar.|
|[verileri](#data)|`array_view`ham verisine bir işaretçi döndürür.|
|[discard_data](#discard_data)|Bu görünümü temel alan geçerli verileri atar.|
|[get_extent](#get_extent)|Array_view nesnesinin kapsam nesnesini döndürür.|
|[get_ref](#get_ref)|Dizinli öğeye bir başvuru döndürür.|
|[get_source_accelerator_view](#get_source_accelerator_view)|`array_view` veri kaynağının bulunduğu [accelerator_view](accelerator-view-class.md) döndürür.|
|[yenileyebilir](#refresh)|`array_view` nesnesine, ilişkili belleğinin `array_view` arabirimi dışında değiştirildiğini bildirir. Bu yönteme yapılan bir çağrı, tüm önbelleğe alınan bilgileri eski işler.|
|[reinterpret_as](#reinterpret_as)|`array_view` nesnesindeki tüm öğeleri içeren tek boyutlu bir dizi döndürür.|
|[section](#section)|Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu `array_view` nesnesinin bir alt bölümünü döndürür.|
|[synchronize](#synchronize)|`array_view` nesnesinde yapılan tüm değişiklikleri kaynak verilerine geri eşitler.|
|[synchronize_async](#synchronize_async)|`array_view` nesnesi üzerinde yapılan değişiklikleri zaman uyumsuz olarak kaynak verilere geri eşitler.|
|[synchronize_to](#synchronize_to)|`array_view` nesnesinde yapılan tüm değişiklikleri belirtilen [accelerator_view](accelerator-view-class.md)eşitler.|
|[synchronize_to_async](#synchronize_to_async)|`array_view` nesnesinde yapılan tüm değişiklikleri zaman uyumsuz olarak belirtilen [accelerator_view](accelerator-view-class.md)eşitler.|
|[view_as](#view_as)|Bu `array_view` nesnesinin verilerini kullanarak farklı bir derecenin `array_view` nesnesini oluşturur.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator ()](#operator_call)|Parametresi veya parametreleri tarafından belirtilen öğenin değerini döndürür.|
|[işleç\[\]](#operator_at)|Parametreler tarafından belirtilen öğeyi döndürür.|
|[işleç =](#operator_eq)|Belirtilen `array_view` nesnesinin içeriğini buna kopyalar.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank)|`array_view` nesnesinin derecesini depolar.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[genişliğini](#extent)|`array_view` nesnesinin şeklini tanımlayan `extent` nesnesini alır.|
|[source_accelerator_view](#source_accelerator_view)|`array_view` veri kaynağının bulunduğu [accelerator_view](accelerator-view-class.md) alır|
|[value_type](#value_type)|`array_view` ve bağlantılı dizinin değer türü.|

## <a name="remarks"></a>Açıklamalar

`array_view` sınıfı, bir [dizi](array-class.md) nesnesinde veya bir `array` nesnesinin alt bölümünde bulunan verilere ilişkin bir görünümü temsil eder.

Kaynak verilerin bulunduğu `array_view` nesnesine (yerel olarak) veya farklı bir Hızlandırıcı ya da bir tutarlı etki alanına (uzaktan) erişebilirsiniz. Nesneye uzaktan eriştiğinizde, görünümler, gerektiği şekilde kopyalanır ve önbelleğe alınır. Otomatik önbelleğe almanın etkileri hariç `array_view` nesneleri, `array` nesnelerle benzer bir performans profiline sahiptir. Verilerle görünümler aracılığıyla eriştiğinizde küçük bir performans cezası vardır.

Üç uzaktan kullanım senaryosu vardır:

- Bir Hızlandırıcı 'ya [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) çağrısı ve hızlandırıcıda erişilen bir araç tarafından bir sistem belleği işaretçisine bir görünüm geçirilir.

- Hızlandırıcı üzerinde bulunan bir dizi için bir görünüm, başka bir hızlandırıcının `parallel_for_each` çağrısı aracılığıyla geçirilir ve bunlara erişilir.

- Bir hızlandırıcıda bulunan bir diziye yönelik bir görünüme CPU üzerinden erişilir.

Bu senaryolardan herhangi birinde, başvurulan görünümler çalışma zamanı tarafından uzak konuma kopyalanır ve `array_view` nesnesine yapılan çağrılar tarafından değiştirilirse, yerel konuma geri kopyalanır. Çalışma zamanı değişiklikleri geri kopyalama sürecini iyileştirebilirler, yalnızca değiştirilen öğeleri kopyalayabilir ya da değişmeyen bölümleri kopyalayabilir. Bir veri kaynağındaki çakışan `array_view` nesneleri, uzak bir konumda bilgi tutarlılığını sürdürmek için garanti edilmez.

Aynı veri kaynağına herhangi bir çok iş parçacıklı erişimi eşitlemeniz gerekir.

Çalışma zamanı, `array_view` nesnelerinde verilerin önbelleğe alınmasına ilişkin aşağıdaki garantisi verir:

- Bir `array` nesnesine ve bu nesne sırasındaki bir `array_view` nesnesine tüm iyi eşitlenmiş erişimler, ilişki öncesinde bir seri hale gelir.

- Tek bir `array` nesnesi üzerinde aynı hızlandırıcıda bulunan örtüşen `array_view` nesnelerine yönelik tüm iyi eşitlenmiş erişimler `array` nesnesi aracılığıyla başka bir ad alanına eklenir. Bu kişiler, bir toplam meydana gelir ve program sırasına udan önce ilişkiye göre yapılır. Önbelleğe alma yok. `array_view` nesneler farklı Hızlandırıcılar üzerinde yürütüle, erişim sırası tanımsızdır ve bir yarış durumu oluşturur.

Sistem belleğindeki bir işaretçi kullanarak bir `array_view` nesnesi oluşturduğunuzda, görünüm `array_view` nesnesini yalnızca `array_view` işaretçisi aracılığıyla değiştirmeniz gerekir. Alternatif olarak, temel alınan yerel bellek `array_view` nesnesi yerine doğrudan değiştirilmişse, sistem işaretçisine bağlı `array_view` nesnelerinden birinde `refresh()` çağırmanız gerekir.

Her iki eylem de `array_view` nesnesine temeldeki yerel belleğin değiştirildiğini ve hızlandırıcıda bulunan tüm kopyaların güncel olduğunu bildirir. Bu yönergeleri izlerseniz, işaretçi tabanlı görünümler, veri paralel dizilerinin görünümlerine göre belirtilenlerle aynıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Array_view_shape`

`_Array_view_base`

`array_view`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="dtor"></a>~ array_view

`array_view` nesnesini yok eder.

```cpp
~array_view()restrict(amp,cpu);
```

## <a name="ctor"></a>array_view

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
`data()` ve `size()` üyelerini destekleyen doğrusal bir kapsayıcı belirtmesi gereken bir şablon bağımsız değişkeni.

*_E0*<br/>
Bu bölümün kapsamının en önemli bileşeni.

*_E1*<br/>
Bu bölümün kapsamının en çok önemli bir bileşeni.

*_E2*<br/>
Bu bölümün kapsamının en az önemli bileşeni.

*_Extent*<br/>
Bu `array_view`her boyuttaki kapsam.

*_Other*<br/>
Yeni `array_view`başlatılacak `array_view<T,N>` türünde bir nesne.

*_Size*<br/>
Verilerin sağlandığı C stili dizinin boyutu.

*_Src*<br/>
Yeni diziye Kopyalanacak kaynak verilere yönelik bir işaretçi.

## <a name="copy_to"></a>copy_to

`array_view` nesnesinin içeriğini, `copy(*this, dest)`çağırarak belirtilen hedef nesneye kopyalar.

```cpp
void copy_to(
    array<value_type, _Rank>& _Dest) const;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Kopyalanacak nesne.

## <a name="data"></a>verileri

`array_view`ham verisine bir işaretçi döndürür.

```cpp
value_type* data() const restrict(amp,
    cpu);

const value_type* data() const restrict(amp,
    cpu);
```

### <a name="return-value"></a>Dönüş Değeri

`array_view`ham verilerine yönelik bir işaretçi.

## <a name="discard_data"></a>discard_data

Bu görünümü temel alan geçerli verileri atar. Bu, görünümün geçerli içeriğini üzerinde erişildiği bir hedef `accelerator_view` kopyalamayı önlemek için kullanılan çalışma zamanına yönelik bir iyileştirme ipucdur ve var olan içerik gerekmiyorsa kullanımı önerilir. Bu yöntem bir restrict (amp) bağlamında kullanıldığında op değildir

```cpp
void discard_data() const restrict(cpu);
```

## <a name="extent"></a>genişliğini

`array_view` nesnesinin şeklini tanımlayan `extent` nesnesini alır.

```cpp
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

## <a name="get_extent"></a>get_extent

`array_view` nesnesinin [kapsam](extent-class.md) nesnesini döndürür.

```cpp
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```

### <a name="return-value"></a>Dönüş Değeri

`array_view` nesnesinin `extent` nesnesi

## <a name="get_ref"></a>get_ref

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

## <a name="get_source_accelerator_view"></a>get_source_accelerator_view

Array_view veri kaynağının bulunduğu accelerator_view döndürür. Array_view bir veri kaynağına sahip değilse, bu API bir runtime_exception oluşturur

```cpp
accelerator_view get_source_accelerator_view() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="operator_call"></a>operator ()

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

## <a name="operator_at"></a>operator []

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

Dizindeki öğenin değeri veya en önemli boyutta bir `array_view` yansıtılmıştır.

## <a name="operator_eq"></a>işleç =

Belirtilen `array_view` nesnesinin içeriğini buna kopyalar.

```cpp
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalamanın `array_view` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `array_view` nesnesine bir başvuru.

## <a name="rank"></a>sırası

`array_view` nesnesinin derecesini depolar.

```cpp
static const int rank = _Rank;
```

## <a name="refresh"></a>yenileyebilir

`array_view` nesnesine, ilişkili belleğinin `array_view` arabirimi dışında değiştirildiğini bildirir. Bu yönteme yapılan bir çağrı, tüm önbelleğe alınan bilgileri eski işler.

```cpp
void refresh() const restrict(cpu);
```

## <a name="reinterpret_as"></a>reinterpret_as

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
Yeni `array_view` nesnesinin veri türü.

### <a name="return-value"></a>Dönüş Değeri

`array_view` nesne veya bu `array_view`temel alan bir const `array_view` nesnesi, öğe türü `T` ' den `_Value_type2`' a dönüştürülür ve sıra *N* ' den 1 ' e indirilir.

### <a name="remarks"></a>Açıklamalar

Bazen çok boyutlu bir diziyi, kaynak diziden farklı bir değer türüne sahip olabilecek doğrusal, tek boyutlu bir dizi olarak görüntülemek yararlıdır. Bu yöntemi kullanarak bunu bir `array_view` elde edebilirsiniz.

**Uyarı** Array_view nesnesini farklı bir değer türü kullanarak yeniden yorumlamak güvenli olmayabilecek bir işlemdir. Bu işlev dikkatli kullanılmalıdır.

Örnek buradadır:

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

## <a name="section"></a>kısmı

Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu `array_view` nesnesinin bir alt bölümünü döndürür.

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

Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu `array_view` nesnesinin bir alt bölümü. Yalnızca `index` nesnesi belirtildiğinde alt bölüm, ilişkili kapsamın, `index` nesnesindeki öğelerin dizinlerinden daha büyük dizinlere sahip olan tüm öğeleri içerir.

## <a name="source_accelerator_view"></a>source_accelerator_view

Bu array_view ilişkilendirildiği kaynak accelerator_view alır.

```cpp
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;
```

## <a name="synchronize"></a>yapacak

`array_view` nesnesinde yapılan tüm değişiklikleri kaynak verilerine geri eşitler.

```cpp
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize() const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Access_type*<br/>
Hedef [accelerator_view](accelerator-view-class.md)amaçlanan [access_type](concurrency-namespace-enums-amp.md#access_type) . Bu parametrenin varsayılan değeri `access_type_read`vardır.

## <a name="synchronize_async"></a>synchronize_async

`array_view` nesnesi üzerinde yapılan değişiklikleri zaman uyumsuz olarak kaynak verilere geri eşitler.

```cpp
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_async() const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Access_type*<br/>
Hedef [accelerator_view](accelerator-view-class.md)amaçlanan [access_type](concurrency-namespace-enums-amp.md#access_type) . Bu parametrenin varsayılan değeri `access_type_read`vardır.

### <a name="return-value"></a>Dönüş Değeri

İşlemin tamamlanmasını beklemek için bir sonraki.

## <a name="synchronize_to"></a>synchronize_to

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

## <a name="synchronize_to_async"></a>synchronize_to_async

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

## <a name="value_type"></a>value_type

Array_view ve bağlantılı dizinin değer türü.

```cpp
typedef typenamevalue_type value_type;
```

## <a name="view_as"></a>view_as

Bu `array_view` farklı bir derece `array_view` olarak yeniden yorumlar.

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
Yeni `array_view` nesnesinin sıralaması.

*_View_extent*<br/>
Yeniden şekillendirme `extent`.

*value_type*<br/>
Hem özgün [dizi](array-class.md) nesnesi hem de döndürülen `array_view` nesnesi içindeki öğelerin veri türü.

### <a name="return-value"></a>Dönüş Değeri

Oluşturulan `array_view` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
