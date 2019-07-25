---
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
ms.openlocfilehash: 4c537b7dfdd23ba641438e0caf6306cf5549b2d7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454302"
---
# <a name="duration-class"></a>duration Sınıfı

İki zaman noktası arasındaki geçen süre olan *zaman aralığını*tutan bir türü açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep, class Period = ratio<1>>
class duration;
template <class Rep, class Period>
class duration;
template <class Rep, class Period1, class Period2>
class duration <duration<Rep, Period1>, Period2>;
```

## <a name="remarks"></a>Açıklamalar

Şablon bağımsız değişkeni `Rep` , aralıktaki saat işaretleri sayısını tutmak için kullanılan türü açıklar. Şablon bağımsız değişkeni `Period` , her bir Tick 'in gösterdiği aralığın boyutunu açıklayan bir [oran](../standard-library/ratio.md) örneklemedir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|süre::p eriod typedef|Şablon parametresi `Period`için bir eş anlamlıyı temsil eder.|
|Duration:: rep typedef|Şablon parametresi `Rep`için bir eş anlamlıyı temsil eder.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Süresi](#duration)|Bir `duration` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[biriktirme](#count)|Zaman aralığındaki saat işaretleri sayısını döndürür.|
|[max](#max)|Se. Şablon parametresinin `Ref`izin verilen en büyük değerini döndürür.|
|[min](#min)|Se. Şablon parametresinin `Ref`izin verilen en küçük değerini döndürür.|
|[sıfırlama](#zero)|Se. Aslında (0) `Rep`değerini döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Duration:: operator-](#operator-)|Bir iç içe değer sayısı `duration` ile birlikte nesnenin bir kopyasını döndürür.|
|[Duration:: operator--](#operator--)|Depolanan değer sayısını azaltır.|
|[Duration:: operator =](#op_eq)|Depolanan değer sayısını belirtilen bir değere düşürür.|
|[Duration:: operator * =](#op_star_eq)|Depolanan değer sayısını belirtilen bir değerle çarpar.|
|[Duration:: operator/=](#op_div_eq)|Depolanan değer sayısını belirtilen `duration` nesnenin değer sayısına böler.|
|[Duration:: operator +](#op_add)|Döndürür `*this`.|
|[Duration:: operator + +](#op_add_add)|Depolanan değer sayısını artırır.|
|[Duration:: operator + =](#op_add_eq)|Belirtilen `duration` bir nesnenin değer sayısını depolanan değer sayısına ekler.|
|[Duration:: operator-=](#operator-_eq)|Belirtilen `duration` bir nesnenin değer sayısını depolanan değer sayısı 'ndan çıkartır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<> hatası

**Ad alanı:** std:: hatası

## <a name="count"></a>Duration:: Count

Zaman aralığındaki saat işaretleri sayısını alır.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığındaki saat işaretleri sayısı.

## <a name="duration"></a>süre::d uration Oluşturucusu

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
Saniye `std::ratio` cinsinden değer dönemini temsil eden bir şablon özelleştirmesi.

*R*\
Varsayılan dönemin işaret sayısı.

*Hecesi*\
*Period2*tarafından belirtilen dönem aralığı sayısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu başlatılmamış bir nesne oluşturur. Boş küme ayraçları kullanılarak değer başlatma, sıfır saat işaretleri zaman aralığını temsil eden bir nesne başlatır.

İkinci, bir şablon bağımsız değişken Oluşturucusu, varsayılan bir süre `std::ratio<1>`kullanarak *R* saat aralığı zaman aralığını temsil eden bir nesne oluşturur. Değer sayımlarının hepsini kapatmamak için, kayan nokta türü olarak değerlendirilemez olduğunda `duration::rep` kayan nokta türü olarak değerlendirilemez bir gösterim türünden *Rep2* bir duration nesnesi oluşturmak hatadır.

Üçüncü, iki şablon bağımsız değişken Oluşturucusu, uzunluğu süre olan zaman aralığı olan bir zaman aralığını temsil eden bir nesne *oluşturur.* Değer sayımlarının kesilmesinden kaçınmak için, türü, hedef *türü ile ilgili* olan başka bir Duration nesnesinden bir duration nesnesi oluşturmak hatadır.

Bir zaman türü `D1` , *kayan* nokta türü olarak değerlendirilemez `D2` ve [ratio_divide\<D1::p eriod, D2::p eriod >:: Type::d en](../standard-library/ratio.md) , 1 değil, `D2` başka bir süre türüyle erişilebilir.

*Rep2* örtük olarak dönüştürülemediği `rep` ve `treat_as_floating_point<rep>` *doğru* veya `treat_as_floating_point<Rep2>` *yanlış tutan*değilse, ikinci Oluşturucu aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [< type_traits >](../standard-library/type-traits.md).

Dönüştürmede taşma `treat_as_floating_point<rep>`yoksa ve *true*, `ratio_divide<Period2, period>::den` ya da 1 ' e eşit tutar ve  `treat_as_floating_point<Rep2>`yanlış bir değer tutuyorsa, üçüncü Oluşturucu aşırı yükleme çözümüne katılmaz. Daha fazla bilgi için bkz. [< type_traits >](../standard-library/type-traits.md).

## <a name="max"></a>süre:: Max

Şablon parametre türünün `Ref`değerleri için üst sınırı döndüren statik yöntem.

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `duration(duration_values<rep>::max())`.

## <a name="min"></a>süre:: dk

Şablon parametre türünün `Ref`değerleri için alt sınır döndüren statik yöntem.

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döndürür `duration(duration_values<rep>::min())`.

## <a name="operator-"></a>Duration:: operator-

Bir iç içe değer sayısı `duration` ile birlikte nesnenin bir kopyasını döndürür.

```cpp
constexpr duration operator-() const;
```

## <a name="operator--"></a>Duration:: operator--

Depolanan değer sayısını azaltır.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürülür `*this`.

İkinci yöntem, azaltmadan önce yapılan `*this` bir kopyasını döndürür.

## <a name="op_eq"></a>Duration:: operator =

Depolanan değer sayısını belirtilen bir değere düşürür.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

*DIV*\
İlk yönteminde, *div* bir değer sayısını temsil eder. İkinci yöntemde, *div* bir değer sayısı içeren `duration` bir nesnedir.

### <a name="return-value"></a>Dönüş Değeri

Modül işlemi gerçekleştirildikten sonra nesnesi.`duration`

## <a name="op_star_eq"></a>Duration:: operator * =

Depolanan değer sayısını belirtilen bir değerle çarpar.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>Parametreler

*Mult*\
Tarafından `duration::rep`belirtilen türün değeri.

### <a name="return-value"></a>Dönüş Değeri

Çarpma gerçekleştirildikten sonra nesnesi. `duration`

## <a name="op_div_eq"></a>Duration:: operator/=

Depolanan değer sayısını belirtilen değere böler.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>Parametreler

*DIV*\
Tarafından `duration::rep`belirtilen türün değeri.

### <a name="return-value"></a>Dönüş Değeri

Bölüm gerçekleştirildikten sonra nesnesi. `duration`

## <a name="op_add"></a>Duration:: operator +

Döndürür `*this`.

```cpp
constexpr duration operator+() const;
```

## <a name="op_add_add"></a>Duration:: operator + +

Depolanan değer sayısını artırır.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürülür `*this`.

İkinci yöntem, arttırmadan önce yapılan `*this` bir kopyasını döndürür.

## <a name="op_add_eq"></a>Duration:: operator + =

Belirtilen `duration` bir nesnenin değer sayısını depolanan değer sayısına ekler.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

Ekleme gerçekleştirildikten sonra nesnesi. `duration`

## <a name="operator-_eq"></a>Duration:: operator-=

Belirtilen `duration` bir nesnenin değer sayısını depolanan değer sayısı 'ndan çıkartır.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Hecesi*\
A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

Çıkarma gerçekleştirildikten sonra nesnesi. `duration`

## <a name="zero"></a>süre:: sıfır

Döndürür `duration(duration_values<rep>::zero())`.

```cpp
static constexpr duration zero();
```

## <a name="op_mod_eq"></a>Duration:: operator mod =

Depolanan değer sayısı mod div veya div. Count () değerini azaltır.

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

*DIV*\
Bir duration nesnesi ya da değer sayısını temsil eden bir değer olan bölen.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi, depolanan değer sayısı mod div değerini azaltır ve * this döndürür. İkinci üye işlevi, depolanan değer sayısı mod div. Count () değerini azaltır ve bunu \*döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<> hatası](../standard-library/chrono.md)\
[duration_values Yapısı](../standard-library/duration-values-structure.md)
