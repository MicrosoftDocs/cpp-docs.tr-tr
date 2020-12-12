---
description: 'Daha fazla bilgi edinin: Duration sınıfı'
title: duration Sınıfı
ms.date: 03/27/2016
f1_keywords:
- chrono/std::chrono::duration
- chrono/std::chrono::duration::duration
- chrono/std::chrono::duration::count
- chrono/std::chrono::duration::max
- chrono/std::chrono::duration::min
- chrono/std::chrono::duration::zero
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
helpviewer_keywords:
- std::chrono [C++], duration
ms.openlocfilehash: 9a37d3682e70f840c6c32eed55eb52ce133ab6f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232739"
---
# <a name="duration-class"></a>duration Sınıfı

İki zaman noktası arasındaki geçen süre olan *zaman aralığını* tutan bir türü açıklar.

## <a name="syntax"></a>Syntax

```cpp
template <class Rep, class Period = ratio<1>>
class duration;
template <class Rep, class Period>
class duration;
template <class Rep, class Period1, class Period2>
class duration <duration<Rep, Period1>, Period2>;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni, `Rep` aralıktaki saat işaretleri sayısını tutmak için kullanılan türü açıklar. Şablon bağımsız değişkeni, `Period` her bir Tick 'in gösterdiği aralığın boyutunu açıklayan bir [oran](../standard-library/ratio.md) örneklemedir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|süre::p eriod typedef|Şablon parametresi için bir eş anlamlıyı temsil eder `Period` .|
|Duration:: rep typedef|Şablon parametresi için bir eş anlamlıyı temsil eder `Rep` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[süre](#duration)|Bir `duration` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[biriktirme](#count)|Zaman aralığındaki saat işaretleri sayısını döndürür.|
|[Biçimlendir](#max)|Statik. Şablon parametresinin izin verilen en büyük değerini döndürür `Ref` .|
|[Min](#min)|Statik. Şablon parametresinin izin verilen en küçük değerini döndürür `Ref` .|
|[sıfırlama](#zero)|Statik. Aslında `Rep` (0) değerini döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Duration:: operator-](#operator-)|`duration`Bir iç içe değer sayısı ile birlikte nesnenin bir kopyasını döndürür.|
|[Duration:: operator--](#operator--)|Depolanan değer sayısını azaltır.|
|[Duration:: operator =](#op_eq)|Depolanan değer sayısını belirtilen bir değere düşürür.|
|[Duration:: operator * =](#op_star_eq)|Depolanan değer sayısını belirtilen bir değerle çarpar.|
|[Duration:: operator/=](#op_div_eq)|Depolanan değer sayısını belirtilen nesnenin değer sayısına böler `duration` .|
|[Duration:: operator +](#op_add)|Döndürür **`*this`** .|
|[Duration:: operator + +](#op_add_add)|Depolanan değer sayısını artırır.|
|[Duration:: operator + =](#op_add_eq)|Belirtilen bir nesnenin değer sayısını `duration` depolanan değer sayısına ekler.|
|[Duration:: operator-=](#operator-_eq)|Belirtilen bir nesnenin değer sayısını `duration` depolanan değer sayısı 'ndan çıkartır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<chrono>

**Ad alanı:** std:: hatası

## <a name="durationcount"></a><a name="count"></a> Duration:: Count

Zaman aralığındaki saat işaretleri sayısını alır.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığındaki saat işaretleri sayısı.

## <a name="durationduration-constructor"></a><a name="duration"></a> süre::d uration Oluşturucusu

Bir `duration` nesnesi oluşturur.

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);

template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>Parametreler

*Rep2*\
Ölçek sayısını temsil eden bir aritmetik tür.

*Period2*\
`std::ratio`Saniye cinsinden değer dönemini temsil eden bir şablon özelleştirmesi.

*Sağ*\
Varsayılan dönemin işaret sayısı.

*Hecesi*\
*Period2* tarafından belirtilen dönem aralığı sayısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu başlatılmamış bir nesne oluşturur. Boş küme ayraçları kullanılarak değer başlatma, sıfır saat işaretleri zaman aralığını temsil eden bir nesne başlatır.

İkinci, bir şablon bağımsız değişken Oluşturucusu, varsayılan bir süre kullanarak *R* saat aralığı zaman aralığını temsil eden bir nesne oluşturur `std::ratio<1>` . Değer sayımlarının hepsini kapatmamak için, kayan nokta  `duration::rep` türü olarak değerlendirilemez olduğunda kayan nokta türü olarak değerlendirilemez bir gösterim türünden Rep2 bir duration nesnesi oluşturmak hatadır.

Üçüncü, iki şablon bağımsız değişken Oluşturucusu, *uzunluğu süre olan* zaman aralığı olan bir zaman aralığını temsil eden bir nesne oluşturur. Değer sayımlarının kesilmesinden kaçınmak için, türü, hedef *türü ile ilgili olan başka* bir Duration nesnesinden bir duration nesnesi oluşturmak hatadır.

Bir süre türü `D1` ,  `D2` `D2` kayan nokta türü olarak değerlendirilemez ve [ratio_divide \<D1::period, D2::period> :: Type::d en](../standard-library/ratio.md) 1 değilse, başka bir süre türü ile erişilebilir.

*Rep2* örtük olarak dönüştürülemediği `rep` ve `treat_as_floating_point<rep>` *doğru* veya `treat_as_floating_point<Rep2>` *yanlış tutan* değilse, ikinci Oluşturucu aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [<type_traits>](../standard-library/type-traits.md).

Dönüştürmede taşma yoksa ve `treat_as_floating_point<rep>` *true*, ya da 1 ' e `ratio_divide<Period2, period>::den` eşit tutar ve yanlış bir değer `treat_as_floating_point<Rep2>` *tutuyorsa*, üçüncü Oluşturucu aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [<type_traits>](../standard-library/type-traits.md).

## <a name="durationmax"></a><a name="max"></a> süre:: Max

Şablon parametre türünün değerleri için üst sınırı döndüren statik yöntem `Ref` .

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `duration(duration_values<rep>::max())` .

## <a name="durationmin"></a><a name="min"></a> süre:: dk

Şablon parametre türünün değerleri için alt sınır döndüren statik yöntem `Ref` .

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `duration(duration_values<rep>::min())` .

## <a name="durationoperator-"></a><a name="operator-"></a> Duration:: operator-

`duration`Bir iç içe değer sayısı ile birlikte nesnenin bir kopyasını döndürür.

```cpp
constexpr duration operator-() const;
```

## <a name="durationoperator--"></a><a name="operator--"></a> Duration:: operator--

Depolanan değer sayısını azaltır.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürülür **`*this`** .

İkinci yöntem, **`*this`** azaltmadan önce yapılan bir kopyasını döndürür.

## <a name="durationoperator"></a><a name="op_eq"></a> Duration:: operator =

Depolanan değer sayısını belirtilen bir değere düşürür.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

*DIV*\
İlk yönteminde, *div* bir değer sayısını temsil eder. İkinci yöntemde, *div* `duration` bir değer sayısı içeren bir nesnedir.

### <a name="return-value"></a>Dönüş Değeri

`duration`Modül işlemi gerçekleştirildikten sonra nesnesi.

## <a name="durationoperator"></a><a name="op_star_eq"></a> Duration:: operator * =

Depolanan değer sayısını belirtilen bir değerle çarpar.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>Parametreler

*Mult*\
Tarafından belirtilen türün değeri `duration::rep` .

### <a name="return-value"></a>Dönüş Değeri

`duration`Çarpma gerçekleştirildikten sonra nesnesi.

## <a name="durationoperator"></a><a name="op_div_eq"></a> Duration:: operator/=

Depolanan değer sayısını belirtilen değere böler.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>Parametreler

*DIV*\
Tarafından belirtilen türün değeri `duration::rep` .

### <a name="return-value"></a>Dönüş Değeri

`duration`Bölüm gerçekleştirildikten sonra nesnesi.

## <a name="durationoperator"></a><a name="op_add"></a> Duration:: operator +

Döndürür **`*this`** .

```cpp
constexpr duration operator+() const;
```

## <a name="durationoperator"></a><a name="op_add_add"></a> Duration:: operator + +

Depolanan değer sayısını artırır.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürülür **`*this`** .

İkinci yöntem, **`*this`** arttırmadan önce yapılan bir kopyasını döndürür.

## <a name="durationoperator"></a><a name="op_add_eq"></a> Duration:: operator + =

Belirtilen bir nesnenin değer sayısını `duration` depolanan değer sayısına ekler.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`duration`Ekleme gerçekleştirildikten sonra nesnesi.

## <a name="durationoperator-"></a><a name="operator-_eq"></a> Duration:: operator-=

Belirtilen bir nesnenin değer sayısını `duration` depolanan değer sayısı 'ndan çıkartır.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`duration`Çıkarma gerçekleştirildikten sonra nesnesi.

## <a name="durationzero"></a><a name="zero"></a> süre:: sıfır

`duration(duration_values<rep>::zero())` döndürür.

```cpp
static constexpr duration zero();
```

## <a name="durationoperator-mod"></a><a name="op_mod_eq"></a> Duration:: operator mod =

Depolanan değer sayısı mod div veya div. Count () değerini azaltır.

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

*DIV*\
Bir duration nesnesi ya da değer sayısını temsil eden bir değer olan bölen.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan değer sayısı mod div değerini azaltır ve * this döndürür. İkinci üye işlevi, depolanan değer sayısı mod div. Count () değerini azaltır ve \* bunu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)\
[duration_values Yapısı](../standard-library/duration-values-structure.md)
