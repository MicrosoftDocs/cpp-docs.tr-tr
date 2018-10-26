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
ms.openlocfilehash: 9023f042cd2c39966adb6a5fb4c71b5e24c3e9d1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068053"
---
# <a name="array-class"></a>array Sınıfı

Verileri bir hızlandırıcıya taşımakta kullanılan veri depolayıcıyı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <typename value_type, int _Rank>
friend class array;
```

#### <a name="parameters"></a>Parametreler

*value_type*<br/>
Veri öğesi türü.

*_Dizin*<br/>
Dizinin boyut.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Array Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `array` sınıfı.|
|[~ array yok Edicisi](#dtor)|Yok eder `array` nesne.|
### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[copy_to](#copy_to)|Dizinin içeriğini başka bir diziye kopyalar.|
|[Veri](#data)|Dizi öğesinin ham verisine bir işaretçi döndürür.|
|[get_accelerator_view](#get_accelerator_view)|Döndürür [accelerator_view](accelerator-view-class.md) dizinin ayrıldığı konumu temsil eden nesne. Bu özellik sadece CPU üzerinden erişilebilir.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|İkinci alır [accelerator_view](accelerator-view-class.md) örneklemek için bir hazırlama Oluşturucu çağrıldığında parametre olarak geçirilen nesne `array` nesne.|
|[get_cpu_access_type](#get_cpu_access_type)|Döndürür [access_type](concurrency-namespace-enums-amp.md#access_type) dizi. Bu yöntem sadece CPU üzerinden erişilebilir.|
|[get_extent](#get_extent)|Döndürür [uzantı](extent-class.md) dizi nesnesi.|
|[reinterpret_as](#reinterpret_as)|Tüm öğeleri içeren tek boyutlu bir dizi döndürür `array` nesne.|
|[section](#section)|Uzantıda alt bölümlerini döndürür `array` nesnesinin Belirtilen kaynak ve, isteğe bağlı olarak belirtilen kapsama sahip.|
|[view_as](#view_as)|Döndürür bir [array_view](array-view-class.md) nesnesinden oluşturulan nesne `array` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç std::vector&lt;value_type&gt;](#operator_vec)|Kullanan `copy(*this, vector)` örtük olarak bir std dizisine dönüştürmek için::[vektör](../../../standard-library/vector-class.md) nesne.|
|[operator()](#operator_call)|Parametreler ile belirtilen öğe değeri döndürür.|
|[operator]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `array` bu nesne içine.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıra sabiti](#rank)|Dizi boyut sayısını saklar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[accelerator_view](#accelerator_view)|Alır [accelerator_view](accelerator-view-class.md) dizinin ayrıldığı konumu temsil eden nesne. Bu özellik sadece CPU üzerinden erişilebilir.|
|[associated_accelerator_view](#associated_accelerator_view)|İkinci alır [accelerator_view](accelerator-view-class.md) örneklemek için bir hazırlama Oluşturucu çağrıldığında parametre olarak geçirilen nesne `array` nesne.|
|[cpu_access_type](#cpu_access_type)|Alır [access_type](concurrency-namespace-enums-amp.md#access_type) CPU, depolama dizisinin nasıl erişebileceğiniz temsil eder.|
|[Kapsam](#extent)|Dizi şeklini tanımlayan kapsamı alır.|

## <a name="remarks"></a>Açıklamalar

Türü `array<T,N>` temsil yoğun ve düzenli (pürüzsüz) *N*-Hızlandırıcı veya CPU gibi belirli bir konumda bulunan boyutlu bir dizi. Dizideki öğelerin veri türü `T`, hedef Hızlandırıcı ile uyumlu bir türde olması gerekir. Ancak, boyut `N`, (, dizi türü bir parçasıdır ve statik olarak belirlenir, dizinin kapsamı çalışma zamanıyla belirlenir ve sınıfıyla ifade `extent<N>`.

Bazı işlevler için özelleştirilmiş bir dizi boyutları, herhangi bir sayıda sahip olabilir ancak `array` biri derece, iki ve üç nesneleri. Bağımsız değişkenin boyutunu atlarsanız, varsayılan değer 1'dir.

Dizi verileri bellekte bitişik yerleştirilir. En az önemli boyutun birinde farklı öğeler bellekte bitişiktir.

Diziyi başka diziye kopyalandığında derin kopyalama yapıldığından diziler mantıksal olarak değer türü olarak kabul edilir. İki dizi asla aynı veri'ı seçin.

`array<T,N>` Türü, çeşitli senaryolarda kullanılır:

- Bir veri depolayıcı olarak Hızlandırıcı hesaplamalarında kullanılabilir.

- (Diğer diziler ve kopyalamak için kullanılabilir) bellek ana CPU üzerinde tutmak için bir veri depolayıcı olarak.

- Konak cihaz kopyaları hızlı bir aracı gibi davranan bir hazırlama nesnesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`array`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> ~ array

Yok eder `array` nesne.

```
~array() restrict(cpu);
```

##  <a name="accelerator_view"></a> accelerator_view

Alır [accelerator_view](accelerator-view-class.md) dizinin ayrıldığı konumu temsil eden nesne. Bu özellik sadece CPU üzerinden erişilebilir.

```
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;
```

##  <a name="ctor"></a> Dizi

Yeni bir örneğini başlatır [array sınıfı](array-class.md). Hiçbir varsayılan oluşturucu yok `array<T,N>`. Bütün oluşturucular yalnızca CPU üzerinde çalışır. Bir Direct3D hedef üzerinde çalıştırılamaz.

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

*_Associated_Av*<br/>
Dizinin hedef konumunu belirten bir accelerator_view.

*_Av*<br/>
Bir [accelerator_view](accelerator-view-class.md) dizinin konumunu belirten bir nesne.

*_Cpu_access_type*<br/>
İstenen [access_type](concurrency-namespace-enums-amp.md#access_type) CPU üzerindeki dizi. Bu parametrenin varsayılan değeri `access_type_auto` CPU bırakarak `access_type` belirlemesini çalışma zamanına. Gerçek CPU `access_type` dizi kullanarak sorgulanabilir `get_cpu_access_type` yöntemi.

*_Extent*<br/>
Dizinin her boyutundaki kapsam.

*_E0*<br/>
Bu bölümün kapsamının ikinci en önemli bileşeni.

*_E1*<br/>
Bu bölümün kapsamının sonraki-en-önemli bileşeni.

*_E2*<br/>
Bu bölümün kapsamının en az önemli bileşeni.

*_InputIterator*<br/>
Giriş yineleyicisinin türü.

*_Src*<br/>
Kopyalanacak nesneye için.

*_Src_first*<br/>
Kaynak kapsayıcı içine bir başlangıç yineleyicisi.

*_Src_last*<br/>
Kaynak kapsayıcı içine bir bitiş yineleyicisi.

*_Diğer*<br/>
Başka bir veri kaynağı.

*_Dizin*<br/>
Bölümün boyut sayısı.

*value_type*<br/>
Kopyalanan öğelerin veri türü.

##  <a name="associated_accelerator_view"></a> associated_accelerator_view

İkinci alır [accelerator_view](accelerator-view-class.md) örneklemek için bir hazırlama Oluşturucu çağrıldığında parametre olarak geçirilen nesne `array` nesne.

```
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

##  <a name="copy_to"></a> copy_to

İçeriğini kopyalar `array` diğerine `array`.

```
void copy_to(
    array<value_type, _Rank>& _Dest) const ;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;
```

### <a name="parameters"></a>Parametreler

*_Dest*<br/>
[Array_view](array-view-class.md) üstüne kopyalanacak nesne.

##  <a name="cpu_access_type"></a> cpu_access_type

Bu dizi için izin verilen CPU access_type alır.

```
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;
```

##  <a name="data"></a> Veri

Öğesinin ham verisine bir işaretçi döndürür `array`.

```
value_type* data() restrict(amp, cpu);

const value_type* data() const restrict(amp, cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin ham verisine bir işaretçi.

##  <a name="extent"></a> Kapsam

Alır [uzantı](extent-class.md) şeklini tanımlayan nesnesi `array`.

```
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

##  <a name="get_accelerator_view"></a> get_accelerator_view

Döndürür [accelerator_view](accelerator-view-class.md) konumu temsil eden bir nesne burada `array` nesne ayrılır. Bu özellik sadece CPU üzerinden erişilebilir.

```
Concurrency::accelerator_view get_accelerator_view() const;
```

### <a name="return-value"></a>Dönüş Değeri

`accelerator_view` Konumu temsil eden bir nesne burada `array` nesne ayrılır.

##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view

İkinci alır [accelerator_view](accelerator-view-class.md) örneklemek için bir hazırlama Oluşturucu çağrıldığında parametre olarak geçirilen nesne `array` nesne.

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

Döndürür [uzantı](extent-class.md) nesnesinin `array`.

```
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

`extent` Nesnesinin `array`.

##  <a name="operator_vec"></a> işleç std::vector&lt;value_type&gt;

Kullanan `copy(*this, vector)` örtük olarak dizi std::vector nesnesine dönüştürmek için.

```
operator std::vector<value_type>() const restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*value_type*<br/>
Vector öğelerinin veri türü.

### <a name="return-value"></a>Dönüş Değeri

Bir nesne türü `vector<T>` dizisinde bulunan verilerin bir kopyasını içerir.

##  <a name="operator_call"></a> operator()

Parametreler ile belirtilen öğe değeri döndürür.

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

*_Index*<br/>
Öğenin konumu.

*_I0*<br/>
Bu bölümün kaynağının ikinci en önemli bileşeni.

*_I1*<br/>
Bu bölümün kaynağının ikinci sonraki-en-önemli bileşeni.

*_I2*<br/>
Bu bölümün kaynağının ikinci en az önemli bileşeni.

*_I*<br/>
Öğenin konumu.

### <a name="return-value"></a>Dönüş Değeri

Parametreler ile belirtilen öğe değeri.

##  <a name="operator_at"></a> operator]

Belirtilen dizindeki öğeyi döndürür.

```
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);

const value_type& operator[]
    (const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Dizini.

*_I*<br/>
Dizini.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizindeki öğe.

##  <a name="operator_eq"></a> işleç =

Belirtilen içeriğini kopyalar `array` nesne.

```
array& operator= (const array& _Other) restrict(cpu);

array& operator= (array&& _Other) restrict(cpu);

array& operator= (
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`array` Kopyalanacak nesne.

*_Src*<br/>
`array` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `array` nesne.

##  <a name="rank"></a> boyut sayısı

Boyut sayısını tutar `array`.

```
static const int rank = _Rank;
```

## <a name="reinterpret_as"></a> reinterpret_as

İsteğe bağlı olarak farklı bir değer türü kaynak diziden sahip olabilecek tek boyutlu bir array_view dizi yeniden yorumlar.

### <a name="syntax"></a>Sözdizimi

```
template <typename _Value_type2>
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);

template <typename _Value_type2>
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Value_type2*<br/>
Döndürülen verileri veri türü.

### <a name="return-value"></a>Dönüş Değeri

Bir array_view veya dizisine, ElementType ve 1 ile N azaltılmış boyut bağlantısını düşürülen öğe türü ile göre const array_view nesnesi.

### <a name="remarks"></a>Açıklamalar

Bazen bir doğrusal, tek boyutlu dizi büyük olasılıkla kaynak diziden farklı bir değer türüne sahip olduğu gibi çok boyutlu bir dizi görüntülemek kullanışlıdır. Bunu başarmak için bu yöntemi kullanabilirsiniz.
**Uyarı** farklı bir değer türü kullanarak bir dizi nesnesi yeniden yorumlamak güvenli olmayabilecek olan güvensiz bir işlemi. Bu işlevleri dikkatli kullanmanızı öneririz.

Aşağıdaki kod örneği sağlar.

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

##  <a name="section"></a> Bölüm

Uzantıda alt bölümlerini döndürür `array` nesnesinin Belirtilen kaynak ve, isteğe bağlı olarak belirtilen kapsama sahip.

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

*value_type*<br/>
Kopyalanan öğelerin veri türü.

### <a name="return-value"></a>Dönüş Değeri

Uzantıda alt bölümlerini döndürür `array` nesnesinin Belirtilen kaynak ve, isteğe bağlı olarak belirtilen kapsama sahip. Yalnızca `index` nesnesi belirtildiğinde, Altbölüm ilişkili kılavuzundaki öğelerin dizinleri daha büyük dizinlere sahip tüm öğeleri içeren `index` nesne.

##  <a name="view_as"></a> view_as

Bu dizi olarak derecenin bir [array_view](array-view-class.md) bir.

```
template <int _New_rank>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

template <int _New_rank>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_New_rank*<br/>
Boyut sayısı `extent` nesnesi bir parametre olarak geçirilir.

*_View_extent*<br/>
Yeni oluşturmak için kullanılan uzantı [array_view](array-view-class.md) nesne.

*value_type*<br/>
Hem özgün öğelerin veri türü `array` nesne ve döndürülen `array_view` nesne.

### <a name="return-value"></a>Dönüş Değeri

[Array_view](array-view-class.md) oluşturulan nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
