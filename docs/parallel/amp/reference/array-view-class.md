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
ms.openlocfilehash: 8c78d95afbadb0d3612dcdbca1714ae8c3a06454
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426347"
---
# <a name="arrayview-class"></a>array_view Sınıfı

Bir N boyutlu görünüm üzerinden başka bir kapsayıcı içinde tutulan veriyi temsil eder.

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

*value_type*<br/>
Öğelerin veri türü `array_view` nesne.

*_Dizin*<br/>
Boyut sayısı `array_view` nesne.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[array_view Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `array_view` sınıfı. Hiçbir varsayılan oluşturucu yok `array<T,N>`. Bütün oluşturucular yalnızca CPU üzerinde çalışacak şekilde kısıtlanır ve bir Direct3D hedef üzerinde çalıştırılamaz.|
|[~ array_view yok Edicisi](#ctor)|Yok eder `array_view` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[copy_to](#copy_to)|İçeriğini kopyalar `array_view` çağırarak belirtilen hedef nesneye `copy(*this, dest)`.|
|[Veri](#data)|Öğesinin ham verisine bir işaretçi döndürür `array_view`.|
|[discard_data](#discard_data)|Bu görünümün temelindeki geçerli veriyi atar.|
|[get_extent](#get_extent)|Array_view nesnesinin kapsam nesnesini döndürür.|
|[get_ref](#get_ref)|Dizinlenmiş öğeye bir başvuru döndürür.|
|[get_source_accelerator_view](#get_source_accelerator_view)|Döndürür [accelerator_view](accelerator-view-class.md) burada veri kaynağını `array_view` bulunur.|
|[Yenileme](#refresh)|Bildirir `array_view` ilişkili belleği dışında değiştirilmiş nesne `array_view` arabirimi. Bu yönteme bir çağrı, eski tüm önbelleğe alınan bilgileri işler.|
|[reinterpret_as](#reinterpret_as)|Tüm öğeleri içeren tek boyutlu bir dizi döndürür `array_view` nesne.|
|[section](#section)|Uzantıda alt bölümlerini döndürür `array_view` nesnesinin Belirtilen kaynak ve, isteğe bağlı olarak belirtilen kapsama sahip.|
|[synchronize](#synchronize)|İçin yapılan bütün değişiklikleri eşitler `array_view` nesnesine kaynak verisine.|
|[synchronize_async](#synchronize_async)|Zaman uyumsuz olarak yapılan tüm değişiklikleri eşitler `array_view` nesnesine kaynak verisine.|
|[synchronize_to](#synchronize_to)|İçin yapılan bütün değişiklikleri eşitler `array_view` belirtilen nesneye [accelerator_view](accelerator-view-class.md).|
|[synchronize_to_async](#synchronize_to_async)|Zaman uyumsuz olarak yapılan tüm değişiklikleri eşitler `array_view` belirtilen nesneye [accelerator_view](accelerator-view-class.md).|
|[view_as](#view_as)|Üreten bir `array_view` bu kullanarak farklı boyut sayısına nesnesinin `array_view` nesnenin veri.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator()](#operator_call)|Parametre veya parametreler tarafından belirtilen öğenin değerini döndürür.|
|[operator]](#operator_at)|Parametreler ile belirtilen öğeyi döndürür.|
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `array_view` bu nesne içine.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıra sabiti](#rank)|Boyut sayısını tutar `array_view` nesne.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Kapsam](#extent)|Alır `extent` şeklini tanımlayan nesnesi `array_view` nesne.|
|[source_accelerator_view](#source_accelerator_view)|Alır [accelerator_view](accelerator-view-class.md) burada veri kaynağını `array_view` bulunur|
|[value_type](#value_type)|Değer türü `array_view` ve bağlı dizinin.|

## <a name="remarks"></a>Açıklamalar

`array_view` Sınıfı temsil eder bir görünüm, bulunan verileri bir [dizi](array-class.md) nesne veya alt bir `array` nesne.

Erişebildiğiniz `array_view` kaynak veriler (yerel) bulunduğu veya farklı bir Hızlandırıcı üzerinden veya modellenmiş etki alanından bir nesne (uzaktan). Nesneye uzaktan eriştiğinizde, görünümler kopyalanır ve gerektiği şekilde önbelleğe alınır. Otomatik olarak önbelleğe alma etkileri dışında `array_view` nesneleri, benzer bir performans profiline sahiptir `array` nesneleri. Görünümlerini verilere erişirken küçük bir performans cezası yoktur.

Uzaktan kullanımda üç senaryo vardır:

- Sistem bellek işaretçisine görünüme yoluyla geçirilen bir [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) çağırmak için bir Hızlandırıcı ve Hızlandırıcı üzerinden erişilir.

- Bir Hızlandırıcı üzerinde bulunan bir dizi için bir görünüm aracılığıyla geçirilen bir `parallel_for_each` çağırmak için başka bir Hızlandırıcı ve erişilir.

- Bir Hızlandırıcı üzerinde bulunan bir dizi görünümüne CPU üzerinden erişilir.

Bu senaryolardan herhangi birinde, başvurulan görünümler çalışma zamanı tarafından uzak bir konuma kopyalanır ve yapılan çağrılar tarafından değiştirilirse `array_view` nesne, yerel konumuna geri kopyalanır. Çalışma zamanı değişiklikleri geri kopyalama işlemini iyileştirebilir, yalnızca değişen öğeleri kopyalayabilir veya değişmeyen bölümleri de kopyalayabilir. Çakışan `array_view` nesneler bir veri kaynağı üzerinde uzak bir konumdan bilgi tutarlılığını korumak için garanti edilmez.

Aynı veri kaynağı için herhangi bir çok iş parçacıklı erişimi eşitlemeniz gerekir.

Çalışma zamanı verileri önbelleğe alma ile ilgili olarak aşağıdakileri garantiler `array_view` nesneler:

- Tüm iyi senkronize erişimin bir `array` nesnesi ve bir `array_view` nesnesi üzerinden program sırasına erişimler olur-ilişki önce.

- Çakışan tüm iyi senkronize erişimlerinin `array_view` aynı Hızlandırıcı üzerinde nesnelerde `array` nesnesi aracılığıyla başka isim verilir olan `array` nesne. Bunlar toplam anlamına oluşur-önce program sırasına ilişkiden ilişkidir. Önbelleksizlik yoktur. Varsa `array_view` nesneleri farklı Hızlandırıcılar üzerinde yürütülürken, erişim sırası, bir yarış durumu oluşturma, tanımsız olur.

Oluştururken bir `array_view` Sistem belleğinde bir işaretçi kullanarak nesne değiştirmeniz gerekir `array_view` nesnesi yalnızca `array_view` işaretçi. Alternatif olarak, çağırmalıdır `refresh()` birinde `array_view` alttaki doğal bellek doğrudan yerine aracılığıyla değiştirilirse, sistem işaretçisine bağlı olan nesneleri `array_view` nesne.

İki eylem sonucunda `array_view` alttaki doğal bellek değiştirilir ve Hızlandırıcı üzerinde bulunan herhangi bir kopyanın tarihi geçmiş nesnesi. Aşağıdaki yönergeleri izlerseniz, işaretçi temelli görünümler paralel veri dizileri görünümlerine sağlanan aynıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_Array_view_shape`

`_Array_view_base`

`array_view`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> ~ array_view

Yok eder `array_view` nesne.

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

*_Arr_type*<br/>
İçinden verilerin sağlandığı bir C tarzı dizinin öğe türü.

*_Container*<br/>
Destekleyen doğrusal kapsayıcıyı belirtmelisiniz bir şablon bağımsız değişkeni `data()` ve `size()` üyeleri.

*_E0*<br/>
Bu bölümün kapsamının ikinci en önemli bileşeni.

*_E1*<br/>
Bu bölümün kapsamının sonraki-en-önemli bileşeni.

*_E2*<br/>
Bu bölümün kapsamının en az önemli bileşeni.

*_Extent*<br/>
Bu her boyutundaki kapsam `array_view`.

*_Diğer*<br/>
Bir nesne türü `array_view<T,N>` yeni başlatmak üzere `array_view`.

*_Boyut*<br/>
İçinden verilerin sağlandığı bir C tarzı dizinin boyutu.

*_Src*<br/>
Yeni bir diziye Kopyalanacak kaynak verileri için bir işaretçi.

##  <a name="copy_to"></a> copy_to

İçeriğini kopyalar `array_view` nesnesini çağırarak belirtilen hedef nesneye `copy(*this, dest)`.

```
void copy_to(
    array<value_type, _Rank>& _Dest) const;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Üstüne kopyalanacak nesne.

##  <a name="data"></a> Veri

Öğesinin ham verisine bir işaretçi döndürür `array_view`.

```
value_type* data() const restrict(amp,
    cpu);

const value_type* data() const restrict(amp,
    cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Öğesinin ham verisine bir işaretçi `array_view`.

##  <a name="discard_data"></a> discard_data

Bu görünümün temelindeki geçerli veriyi atar. Bu görünüm geçerli içeriğini bir hedefe kopyalanmasını engellemek için çalışma zamanı bir iyileştirme ipucudur, `accelerator_view` üzerinden erişilen ve varolan içeriği gerek duyulmuyorsa kullanımı tavsiye edilir. Bu yöntemi bir restrict(amp) bağlamında kullanıldığında İşlemsiz.

```
void discard_data() const restrict(cpu);
```

##  <a name="extent"></a> Kapsam

Alır `extent` şeklini tanımlayan nesnesi `array_view` nesne.

```
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

##  <a name="get_extent"></a> get_extent

Döndürür [uzantı](extent-class.md) nesnesinin `array_view` nesne.

```
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```

### <a name="return-value"></a>Dönüş Değeri

`extent` Nesnesinin `array_view` nesnesi

##  <a name="get_ref"></a> get_ref

_Index tarafından dizinlenen öğeye bir başvuru alın. CPU üzerindeki array_view öğesine erişmek için diğer dizin işleçlerinden farklı olarak, bu yöntem bu array_view öğesinin içeriğine CPU'yu örtülü olarak eşitlemez. Uzak konumdaki array_view erişme veya bu array_view içeren kopyalama işlemini gerçekleştirdikten sonra kullanıcılar bu yöntemi çağırmadan önce array_view öğesini CPU açıkça eşitlemeye sorumludur. Bunun yapılmaması, tanımsız davranışa neden olur.

```
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizini.

### <a name="return-value"></a>Dönüş Değeri

_Index tarafından dizinlenen öğeye başvuru

##  <a name="get_source_accelerator_view"></a> get_source_accelerator_view

Array_view veri kaynağının bulunduğu accelerator_view döndürür. Array_view bir veri kaynağına sahip değilse, bu API bir runtime_exception atar.

```
accelerator_view get_source_accelerator_view() const;

```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="operator_call"></a> operator()

Parametre veya parametreler tarafından belirtilen öğenin değerini döndürür.

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

Parametre veya parametreler tarafından belirtilen öğe değeri.

##  <a name="operator_at"></a> operator]

Parametreler ile belirtilen öğeyi döndürür.

```
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizini.

*_I*<br/>
Dizini.

### <a name="return-value"></a>Dönüş Değeri

Dizindeki öğenin değerini veya bir `array_view` en önemli boyutta öngörülmüş.

##  <a name="operator_eq"></a> işleç =

Belirtilen içeriğini kopyalar `array_view` buna nesne.

```
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`array_view` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `array_view` nesne.

##  <a name="rank"></a> boyut sayısı

Boyut sayısını tutar `array_view` nesne.

```
static const int rank = _Rank;
```

##  <a name="refresh"></a> Yenileme

Bildirir `array_view` ilişkili belleği dışında değiştirilmiş nesne `array_view` arabirimi. Bu yönteme bir çağrı, eski tüm önbelleğe alınan bilgileri işler.

```
void refresh() const restrict(cpu);
```
## <a name="reinterpret_as"></a> reinterpret_as

Array_view, olabilen bir seçenek olarak kaynak array_view'dan bir farklı bir değer türü olan tek boyutlu bir array_view aracılığıyla yeniden yorumlar.

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

*_Value_type2*<br/>
Yeni veri türünü `array_view` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir `array_view` nesne veya const `array_view` bunu temel alarak nesne `array_view`, öğesinden öğe türü ile `T` için `_Value_type2`, ve düşürülen *N* 1.

### <a name="remarks"></a>Açıklamalar

Bazen çok boyutlu bir kaynak diziden farklı değer türüne sahip olabilecek bir doğrusal, tek boyutlu dizi olarak görüntülemek kullanışlıdır. Bu şirket elde edebileceğiniz bir `array_view` bu yöntemi kullanarak.

**Uyarı** bir array_view nesnesini farklı bir değer türü kullanarak yeniden yorumlamak güvenli olmayabilecek bir işlem olduğu. Bu işlev dikkatli kullanılmalıdır.

Örnek buradadır:

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

##  <a name="section"></a> Bölüm

Uzantıda alt bölümlerini döndürür `array_view` nesnesinin Belirtilen kaynak ve, isteğe bağlı olarak belirtilen kapsama sahip.

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

*_E0*<br/>
Bu bölümün kapsamının ikinci en önemli bileşeni.

*_E1*<br/>
Bu bölümün kapsamının sonraki-en-önemli bileşeni.

*_E2*<br/>
Bu bölümün kapsamının en az önemli bileşeni.

*_Ext*<br/>
[Uzantı](extent-class.md) nesnesi bölümün kapsamını belirtir. Kaynak 0'dır.

*_Idx*<br/>
[Dizin](index-class.md) başlangıç konumunu belirten bir nesne. Altbölüm kapsamın geri kalan ' dir.

*_I0*<br/>
Bu bölümün kaynağının ikinci en önemli bileşeni.

*_I1*<br/>
Bu bölümün kaynağının ikinci sonraki-en-önemli bileşeni.

*_I2*<br/>
Bu bölümün kaynağının ikinci en az önemli bileşeni.

*_Dizin*<br/>
Bölümün boyut sayısı.

*_Section_extent*<br/>
[Uzantı](extent-class.md) nesnesi bölümün kapsamını belirtir.

*_Section_origin*<br/>
[Dizin](index-class.md) başlangıç konumunu belirten bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Uzantıda alt bölümlerini `array_view` nesnesinin Belirtilen kaynak ve, isteğe bağlı olarak belirtilen kapsama sahip. Yalnızca `index` nesnesi belirtildiğinde, Altbölüm ilgili kapsam öğeleri dizinleri daha büyük dizinlere sahip tüm öğeleri içeren `index` nesne.

##  <a name="source_accelerator_view"></a> source_accelerator_view

Bu array_view ile ilişkili kaynak accelerator_view alır.

```
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;
```

##  <a name="synchronize"></a> Eşitleme

İçin yapılan bütün değişiklikleri eşitler `array_view` nesnesine kaynak verisine.

```
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize() const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Access_type*<br/>
Hedeflenen [access_type](concurrency-namespace-enums-amp.md#access_type) hedef [accelerator_view](accelerator-view-class.md). Bu parametrenin varsayılan değeri `access_type_read`.

##  <a name="synchronize_async"></a> synchronize_async

Zaman uyumsuz olarak yapılan tüm değişiklikleri eşitler `array_view` nesnesine kaynak verisine.

```
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_async() const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Access_type*<br/>
Hedeflenen [access_type](concurrency-namespace-enums-amp.md#access_type) hedef [accelerator_view](accelerator-view-class.md). Bu parametrenin varsayılan değeri `access_type_read`.

### <a name="return-value"></a>Dönüş Değeri

Gelecek alacağı işlemin tamamlanmasını bekleyin.

##  <a name="synchronize_to"></a> synchronize_to

Belirtilen Hızlandırıcı görünümü bu array_view yapılan bütün değişiklikleri eşitler.

```
void synchronize_to(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Accl_view*<br/>
Eşitlenecek hedef accelerator_view.

*_Access_type*<br/>
Hedef accelerator_view üzerindeki istenen access_type. Bu parametre bir varsayılan değeri: access_type_read sahiptir.

##  <a name="synchronize_to_async"></a> synchronize_to_async

Zaman uyumsuz olarak belirtilen Hızlandırıcı görünümü bu array_view yapılan bütün değişiklikleri eşitler.

```
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Accl_view*<br/>
Eşitlenecek hedef accelerator_view.

*_Access_type*<br/>
Hedef accelerator_view üzerindeki istenen access_type. Bu parametre bir varsayılan değeri: access_type_read sahiptir.

### <a name="return-value"></a>Dönüş Değeri

Gelecek alacağı işlemin tamamlanmasını bekleyin.

##  <a name="value_type"></a> value_type

Array_view ve bağlı dizinin değer türü.

```
typedef typenamevalue_type value_type;
```

##  <a name="view_as"></a> view_as

Bu derecenin `array_view` olarak bir `array_view` bir.

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

*_New_rank*<br/>
Yeni Boyut `array_view` nesne.

*_View_extent*<br/>
Yeniden şekillendiren `extent`.

*value_type*<br/>
Hem özgün öğelerin veri türü [dizi](array-class.md) nesne ve döndürülen `array_view` nesne.

### <a name="return-value"></a>Dönüş Değeri

`array_view` Oluşturulan nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
