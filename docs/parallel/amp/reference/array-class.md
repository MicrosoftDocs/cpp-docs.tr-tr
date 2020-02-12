---
title: array Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
ms.openlocfilehash: efea8dabb69a48e69d68a86110fdf9bc7664948b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127118"
---
# <a name="array-class"></a>array Sınıfı

Bir hızlandırıcıya veri taşımak için kullanılan bir veri kapsayıcısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename value_type, int _Rank>
friend class array;
```

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Verilerin öğe türü.

*_Rank*<br/>
Dizinin derecesi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[dizi Oluşturucusu](#ctor)|`array` sınıfının yeni bir örneğini başlatır.|
|[~ dizi yok edici](#dtor)|`array` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[copy_to](#copy_to)|Dizinin içeriğini başka bir diziye kopyalar.|
|[verileri](#data)|Dizinin ham verisine bir işaretçi döndürür.|
|[get_accelerator_view](#get_accelerator_view)|Dizinin ayrıldığı konumu temsil eden [accelerator_view](accelerator-view-class.md) nesnesini döndürür. Bu özelliğe yalnızca CPU üzerinde erişilebilir.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|`array` nesnesinin örneğini oluşturmak için bir hazırlama Oluşturucusu çağrıldığında parametre olarak geçirilen ikinci [accelerator_view](accelerator-view-class.md) nesnesini alır.|
|[get_cpu_access_type](#get_cpu_access_type)|Dizinin [access_type](concurrency-namespace-enums-amp.md#access_type) döndürür. Bu yönteme yalnızca CPU üzerinden erişilebilir.|
|[get_extent](#get_extent)|Dizinin [kapsam](extent-class.md) nesnesini döndürür.|
|[reinterpret_as](#reinterpret_as)|`array` nesnesindeki tüm öğeleri içeren tek boyutlu bir dizi döndürür.|
|[section](#section)|Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu `array` nesnesinin bir alt bölümünü döndürür.|
|[view_as](#view_as)|`array` nesnesinden oluşturulan [array_view](array-view-class.md) nesnesini döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator std:: vector&lt;value_type&gt;](#operator_vec)|Diziyi bir std::[Vector](../../../standard-library/vector-class.md) nesnesine örtük olarak dönüştürmek için `copy(*this, vector)` kullanır.|
|[operator ()](#operator_call)|Parametreler tarafından belirtilen öğe değerini döndürür.|
|[işleç\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[işleç =](#operator_eq)|Belirtilen `array` nesnesinin içeriğini buna kopyalar.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank)|Dizinin derecesini depolar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[accelerator_view](#accelerator_view)|Dizinin ayrıldığı konumu temsil eden [accelerator_view](accelerator-view-class.md) nesnesini alır. Bu özelliğe yalnızca CPU üzerinde erişilebilir.|
|[associated_accelerator_view](#associated_accelerator_view)|`array` nesnesinin örneğini oluşturmak için bir hazırlama Oluşturucusu çağrıldığında parametre olarak geçirilen ikinci [accelerator_view](accelerator-view-class.md) nesnesini alır.|
|[cpu_access_type](#cpu_access_type)|CPU 'nun dizinin depolamasına nasıl erişebileceğini temsil eden [access_type](concurrency-namespace-enums-amp.md#access_type) alır.|
|[genişliğini](#extent)|Dizinin şeklini tanımlayan kapsamı alır.|

## <a name="remarks"></a>Açıklamalar

Tür `array<T,N>`, Hızlandırıcı veya CPU gibi belirli bir konumda bulunan yoğun ve normal (pürüzlü olmayan) *N*boyutlu diziyi temsil eder. Dizideki öğelerin veri türü, hedef Hızlandırıcı ile uyumlu bir türde olması gereken `T`. Dizi `N`sırası statik olarak belirlendiği ve türün parçası olsa da, dizinin kapsamı çalışma zamanı tarafından belirlenir ve sınıf `extent<N>`kullanılarak ifade edilir.

Bir dizide herhangi bir sayıda boyut olabilir, ancak bazı işlevler bir, iki ve üç dereceli `array` nesne için özelleştirilmiş olur. Boyut bağımsız değişkenini atlarsanız varsayılan değer 1 ' dir.

Dizi verileri bellekte bitişik olarak düzenlenir. En az önemli boyutta bir öğe tarafından farklı olan öğeler bellekte bitişik olarak bulunur.

Diziler mantıksal olarak değer türleri olarak değerlendirilir, çünkü bir dizi başka bir diziye kopyalanırsa derin bir kopya gerçekleştirilir. İki dizi hiçbir şekilde aynı verileri göstermiyor.

`array<T,N>` türü çeşitli senaryolarda kullanılır:

- Bir hızlandırıcı üzerinde hesaplamalar için kullanılabilen bir veri kapsayıcısı olarak.

- Bir veri kapsayıcısı olarak ana bilgisayar CPU 'SU üzerinde (Diğer dizilere kopyalamak için kullanılabilir).

- Ana bilgisayardan cihaza kopyalarla hızlı bir aracı olarak görev yapacak hazırlama nesnesi olarak.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`array`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="dtor"></a>~ dizi

`array` nesnesini yok eder.

```cpp
~array() restrict(cpu);
```

## <a name="accelerator_view"></a>accelerator_view

Dizinin ayrıldığı konumu temsil eden [accelerator_view](accelerator-view-class.md) nesnesini alır. Bu özelliğe yalnızca CPU üzerinde erişilebilir.

```cpp
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;
```

## <a name="ctor"></a>dizide

[Dizi sınıfının](array-class.md)yeni bir örneğini başlatır. `array<T,N>`için varsayılan oluşturucu yok. Tüm oluşturucular yalnızca CPU üzerinde çalıştırılır. Direct3D hedefinde yürütülemez.

```cpp
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

*_Associated_Av*<br/>
Dizinin tercih edilen hedef konumunu belirten bir accelerator_view.

*_Av*<br/>
Dizinin konumunu belirten [accelerator_view](accelerator-view-class.md) nesnesi.

*_Cpu_access_type*<br/>
CPU üzerindeki dizi için istenen [access_type](concurrency-namespace-enums-amp.md#access_type) . Bu parametre, CPU `access_type` belirlemeyi çalışma zamanına bırakarak `access_type_auto` varsayılan değeri vardır. Dizinin gerçek CPU `access_type` `get_cpu_access_type` yöntemi kullanılarak sorgulanabilir.

*_Extent*<br/>
Dizinin her boyutundaki kapsam.

*_E0*<br/>
Bu bölümün kapsamının en önemli bileşeni.

*_E1*<br/>
Bu bölümün kapsamının en çok önemli bir bileşeni.

*_E2*<br/>
Bu bölümün kapsamının en az önemli bileşeni.

*_InputIterator*<br/>
Giriş yineleyicisinin türü.

*_Src*<br/>
Kopyalanacak nesneye.

*_Src_first*<br/>
Kaynak kapsayıcıya bir başlangıç yineleyicisi.

*_Src_last*<br/>
Kaynak kapsayıcıya bir bitiş yineleyicisi.

*_Other*<br/>
Diğer veri kaynağı.

*_Rank*<br/>
Bölümün derecesi.

*value_type*<br/>
Kopyalanmış öğelerin veri türü.

## <a name="associated_accelerator_view"></a>associated_accelerator_view

`array` nesnesinin örneğini oluşturmak için bir hazırlama Oluşturucusu çağrıldığında parametre olarak geçirilen ikinci [accelerator_view](accelerator-view-class.md) nesnesini alır.

```cpp
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

## <a name="copy_to"></a>copy_to

`array` içeriğini başka bir `array`kopyalar.

```cpp
void copy_to(
    array<value_type, _Rank>& _Dest) const ;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
Kopyalamanın [array_view](array-view-class.md) nesnesi.

## <a name="cpu_access_type"></a>cpu_access_type

Bu dizi için izin verilen CPU access_type alır.

```cpp
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;
```

## <a name="data"></a>verileri

`array`ham verisine bir işaretçi döndürür.

```cpp
value_type* data() restrict(amp, cpu);

const value_type* data() const restrict(amp, cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ham verilerine yönelik bir işaretçi.

## <a name="extent"></a>genişliğini

`array`şeklini tanımlayan [kapsam](extent-class.md) nesnesini alır.

```cpp
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

## <a name="get_accelerator_view"></a>get_accelerator_view

`array` nesnesinin ayrıldığı konumu temsil eden [accelerator_view](accelerator-view-class.md) nesnesini döndürür. Bu özelliğe yalnızca CPU üzerinde erişilebilir.

```cpp
Concurrency::accelerator_view get_accelerator_view() const;
```

### <a name="return-value"></a>Dönüş Değeri

`array` nesnesinin ayrıldığı konumu temsil eden `accelerator_view` nesnesi.

## <a name="get_associated_accelerator_view"></a>get_associated_accelerator_view

`array` nesnesinin örneğini oluşturmak için bir hazırlama Oluşturucusu çağrıldığında parametre olarak geçirilen ikinci [accelerator_view](accelerator-view-class.md) nesnesini alır.

```cpp
Concurrency::accelerator_view get_associated_accelerator_view() const ;
```

### <a name="return-value"></a>Dönüş Değeri

Hazırlama oluşturucusuna geçirilen ikinci [accelerator_view](accelerator-view-class.md) nesnesi.

## <a name="get_cpu_access_type"></a>get_cpu_access_type

Bu dizi için izin verilen CPU access_type döndürür.

```cpp
access_type get_cpu_access_type() const restrict(cpu);
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="get_extent"></a>get_extent

`array`'in [kapsam](extent-class.md) nesnesini döndürür.

```cpp
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

`array``extent` nesnesi.

## <a name="operator_vec"></a>operator std:: vector&lt;value_type&gt;

Diziyi bir std:: Vector nesnesine örtük olarak dönüştürmek için `copy(*this, vector)` kullanır.

```cpp
operator std::vector<value_type>() const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Vektör öğelerinin veri türü.

### <a name="return-value"></a>Dönüş Değeri

Dizide yer alan verilerin bir kopyasını içeren `vector<T>` türünde bir nesne.

## <a name="operator_call"></a>operator ()

Parametreler tarafından belirtilen öğe değerini döndürür.

```cpp
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

*_Index*<br/>
Öğenin konumu.

*_I0*<br/>
Bu bölümün kaynağının en önemli bileşeni.

*_I1*<br/>
Bu bölümün kaynağının en çok önemli bileşeni.

*_I2*<br/>
Bu bölümün kaynağının en az önemli bileşeni.

*_I*<br/>
Öğenin konumu.

### <a name="return-value"></a>Dönüş Değeri

Parametreler tarafından belirtilen öğe değeri.

## <a name="operator_at"></a>operator []

Belirtilen dizindeki öğeyi döndürür.

```cpp
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);

const value_type& operator[]
    (const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizin.

*_I*<br/>
Dizin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde olan öğe.

## <a name="operator_eq"></a>işleç =

Belirtilen `array` nesnesinin içeriğini kopyalar.

```cpp
array& operator= (const array& _Other) restrict(cpu);

array& operator= (array&& _Other) restrict(cpu);

array& operator= (
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalamanın `array` nesnesi.

*_Src*<br/>
Kopyalamanın `array` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `array` nesnesine bir başvuru.

## <a name="rank"></a>sırası

`array`derecesini depolar.

```cpp
static const int rank = _Rank;
```

## <a name="reinterpret_as"></a>reinterpret_as

İsteğe bağlı olarak, kaynak diziden farklı bir değer türüne sahip olabilecek tek boyutlu bir array_view diziyi yeniden yorumlar.

### <a name="syntax"></a>Sözdizimi

```cpp
template <typename _Value_type2>
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);

template <typename _Value_type2>
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Value_type2*<br/>
Döndürülen verilerin veri türü.

### <a name="return-value"></a>Dönüş Değeri

Öğe türü, T 'den ElementType 'e ve sıra N ' den 1 ' e indirgenecek şekilde, diziyi temel alan bir array_view veya const array_view nesnesi.

### <a name="remarks"></a>Açıklamalar

Bazen çok boyutlu bir diziyi, büyük olasılıkla kaynak diziden farklı bir değer türü olan doğrusal, tek boyutlu bir dizi gibi görüntülemek uygun olabilir. Bunu elde etmek için bu yöntemi kullanabilirsiniz.
**Dikkat** edin Farklı bir değer türü kullanarak bir dizi nesnesini yeniden yorumlama, güvenli olmayabilecek bir işlemdir. Bu işlevi dikkatle kullanmanızı öneririz.

Aşağıdaki kod bir örnek sağlar.

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

## <a name="section"></a>kısmı

Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu `array` nesnesinin bir alt bölümünü döndürür.

```cpp
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

*value_type*<br/>
Kopyalanmış öğelerin veri türü.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen kaynak ve isteğe bağlı olarak belirtilen kapsamın bulunduğu `array` nesnesinin bir alt bölümünü döndürür. Yalnızca `index` nesnesi belirtildiğinde alt bölüm, ilişkili kılavuzdaki, `index` nesnesindeki öğelerin dizinlerinden daha büyük dizinlere sahip olan tüm öğeleri içerir.

## <a name="view_as"></a>view_as

Bu diziyi farklı bir derece [array_view](array-view-class.md) olarak yeniden yorumlar.

```cpp
template <int _New_rank>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

template <int _New_rank>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_New_rank*<br/>
`extent` nesnesinin bir parametre olarak geçirildiği derecesi.

*_View_extent*<br/>
Yeni [array_view](array-view-class.md) nesnesini oluşturmak için kullanılan uzantı.

*value_type*<br/>
Hem özgün `array` nesnesindeki hem de döndürülen `array_view` nesnesindeki öğelerin veri türü.

### <a name="return-value"></a>Dönüş Değeri

Oluşturulan [array_view](array-view-class.md) nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
