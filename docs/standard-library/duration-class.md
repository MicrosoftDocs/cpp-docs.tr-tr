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
ms.openlocfilehash: 49c68b1650ced36ebcf949ae2594508480e15136
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413807"
---
# <a name="duration-class"></a>duration Sınıfı

Tutan bir türü açıklar bir *zaman aralığı*, iki zaman noktası arasında geçen süre olan.

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

Şablon bağımsız değişkeni `Rep` aralığındaki saat tıklarının sayısını tutmak için kullanılan türü açıklar. Şablon bağımsız değişkeni `Period` örneklemesiyse [oranı](../standard-library/ratio.md) her bir onayın temsil ettiği aralığın boyutunu açıklayan.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|Typedef Duration::Period|Şablon parametresi için eş anlamlısını temsil `Period`.|
|Typedef Duration::Rep|Şablon parametresi için eş anlamlısını temsil `Rep`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Süresi](#duration)|Oluşturur bir `duration` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Sayısı](#count)|Zaman aralığındaki saat tıklarının sayısını döndürür.|
|[en fazla](#max)|Statik. Şablon parametresinin izin verilen en büyük değerini döndürür `Ref`.|
|[Min](#min)|Statik. Şablon parametresinin izin verilen en düşük değeri döndürür `Ref`.|
|[Sıfır](#zero)|Statik. Aslında döndürür `Rep`(0).|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Duration::operator-](#operator-)|Bir kopyasını döndürür `duration` bir tık sayısıyla birlikte nesne.|
|[Duration::operator--](#operator--)|Depolanan işaret sayısını azaltır.|
|[Duration::operator =](#op_eq)|Depolanan işaret sayısını belirtilen bir ölçek değeriyle düşürür.|
|[Duration::operator * =](#op_star_eq)|Depolanan işaret sayısını belirtilen bir değerle çarpar.|
|[Duration::operator / =](#op_div_eq)|Bölen tarafından belirtilen bir işaret sayısını depolanan işaret sayısını `duration` nesne.|
|[Duration::operator +](#op_add)|Döndürür `*this`.|
|[Duration::operator ++](#op_add_add)|Depolanan işaret sayısını artırır.|
|[Duration::operator +=](#op_add_eq)|İşaret sayısını belirtilen ekler `duration` depolanan işaret sayısını için nesne.|
|[Duration::operator-=](#operator-_eq)|İşaret sayısını belirtilen çıkarır `duration` depolanan işaret sayısını nesne.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="count"></a>  Duration::Count

Zaman aralığındaki saat tıklarının sayısını alır.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığındaki saat tıklarının sayısını.

## <a name="duration"></a>  Duration::Duration Oluşturucusu

Oluşturur bir `duration` nesne.

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);

template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>Parametreler

*Rep2*<br/>
Tıklarının sayısını temsil eden bir aritmetik türü.

*Period2*<br/>
A `std::ratio` birimlerindeki dönemini saniye temsil etmek için şablon uzmanlığı.

*R*<br/>
Varsayılan dönem sayısı.

*Süre*<br/>
Tarafından belirtilen dönem tıklarının sayısını *Period2*.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, başlatılmamış bir nesne oluşturur. Değer başlatma boş ayraçlar kullanılarak sıfır saat vuruşu zaman aralığını temsil eden bir nesneyi başlatır.

Oluşturucu bir nesne oluşturan bir şablon bağımsız değişkeni, ikinci temsil eden bir zaman aralığını *R* saat vuruşu bir varsayılan süre kullanarak `std::ratio<1>`. Yuvarlama işaret sayılarını önlemek için temsil türünden bir süre nesnesi oluşturmak için bir hata olduğunu *Rep2* , kabul kayan nokta türü `duration::rep` bir kayan nokta türü olarak değerlendirilemediğinde.

Üçüncü iki şablon bağımsız değişken Oluşturucu uzunluğunu tarafından belirtilen zaman aralığı olan bir zaman aralığını temsil eden bir nesne oluşturur. *süre*. İşaret sayılarının kesilmesini önlemek için türü olan başka bir süre nesnesinden bir süre nesnesi oluşturmak için bir hata olduğunu *incommensurable* hedef türüne sahip.

Süre türü `D1` olduğu *incommensurable* başka bir süre türü ile `D2` varsa `D2` bir kayan nokta türü olarak işlenemiyorsa ve [kıyaslanamaz\<D1::period, D2:: süre >:: type::den](../standard-library/ratio.md) 1 değil.

Sürece *Rep2* örtük olarak dönüştürülebilir `rep` ve her iki `treat_as_floating_point<rep>` *korumadıkça* veya `treat_as_floating_point<Rep2>` *yanlışlığını korumadıkça*, ikinci oluşturucu aşırı yükleme çözünürlüğü içinde yer almaz. Daha fazla bilgi için [< type_traits >](../standard-library/type-traits.md).

Taşma, dönüştürme işleminden sürece ve `treat_as_floating_point<rep>` *korumadıkça*, veya her ikisini de `ratio_divide<Period2, period>::den` eşittir 1 ve `treat_as_floating_point<Rep2>` *yanlışlığını korumadıkça*, üçüncü oluşturucu içinde yer almaz aşırı yükleme çözümlemesi. Daha fazla bilgi için [< type_traits >](../standard-library/type-traits.md).

## <a name="max"></a>  Duration::Max

Şablon parametre türü değerlerinin üst sınırını döndüren statik yöntem `Ref`.

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında döndürür `duration(duration_values<rep>::max())`.

## <a name="min"></a>  Duration::Min

Şablon parametre türü değerlerinin alt sınırını döndüren statik yöntem `Ref`.

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında döndürür `duration(duration_values<rep>::min())`.

## <a name="operator-"></a>  Duration::operator-

Bir kopyasını döndürür `duration` bir tık sayısıyla birlikte nesne.

```cpp
constexpr duration operator-() const;
```

## <a name="operator--"></a>  Duration::operator--

Depolanan işaret sayısını azaltır.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürür `*this`.

İkinci yöntem bir kopyasını döndürür `*this` azaltma önce yapılır.

## <a name="op_eq"></a>  Duration::operator =

Depolanan işaret sayısını belirtilen bir ölçek değeriyle düşürür.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

*div*<br/>
İlk yöntem için *Div* işaret sayısını temsil eder. İkinci yöntem *Div* olduğu bir `duration` bir onay sayısı içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

`duration` Sonra nesne işlemi gerçekleştirildikten.

## <a name="op_star_eq"></a>  Duration::operator * =

Depolanan işaret sayısını belirtilen bir değerle çarpar.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>Parametreler

*Mult*<br/>
Tarafından belirtilen türün bir değeri `duration::rep`.

### <a name="return-value"></a>Dönüş Değeri

`duration` Çarpma işlemi gerçekleştirildikten sonra nesne.

## <a name="op_div_eq"></a>  Duration::operator / =

Depolanan işaret sayısını belirtilen değere böler.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>Parametreler

*div*<br/>
Tarafından belirtilen türün bir değeri `duration::rep`.

### <a name="return-value"></a>Dönüş Değeri

`duration` Bölme işlemi gerçekleştirildikten sonra nesne.

## <a name="op_add"></a>  Duration::operator +

Döndürür `*this`.

```cpp
constexpr duration operator+() const;
```

## <a name="op_add_add"></a>  Duration::operator ++

Depolanan işaret sayısını artırır.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürür `*this`.

İkinci yöntem bir kopyasını döndürür `*this` artışı önce yapılan.

## <a name="op_add_eq"></a>  Duration::operator +=

İşaret sayısını belirtilen ekler `duration` depolanan işaret sayısını için nesne.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

`duration` Toplama işlemi gerçekleştirildikten sonra nesne.

## <a name="operator-_eq"></a>  Duration::operator-=

İşaret sayısını belirtilen çıkarır `duration` depolanan işaret sayısını nesne.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Süre*<br/>
A `duration` nesne.

### <a name="return-value"></a>Dönüş Değeri

`duration` Çıkarma işlemi gerçekleştirildikten sonra nesne.

## <a name="zero"></a>  Duration::Zero

Döndürür `duration(duration_values<rep>::zero())`.

```cpp
static constexpr duration zero();
```

## <a name="op_mod_eq"></a>  Duration::operator mod =

Div veya Div.count() modül depolanan işaret sayısını azaltır.

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

*div*<br/>
Bir süre nesnesi ya da işaret sayıları temsil eden bir değer bölen.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi Div modül depolanan işaret sayısını azaltır ve döndürür * bu. İkinci üye işlevi Div.count() modül depolanan işaret sayısını azaltır ve döndürür \*bu.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
[duration_values Yapısı](../standard-library/duration-values-structure.md)<br/>
