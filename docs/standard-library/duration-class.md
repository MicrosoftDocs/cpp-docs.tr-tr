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
ms.openlocfilehash: 3669935bf094f476ca24a8170a0388dff29e0a0c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368761"
---
# <a name="duration-class"></a>duration Sınıfı

İki zaman noktası arasında geçen bir zaman aralığı olan bir *tür*açıklar.

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

Şablon bağımsız `Rep` değişkeni, saat işaretçisi sayısını aralıkta tutmak için kullanılan türü açıklar. Şablon bağımsız `Period` değişkeni, her kenenin temsil ettiği aralığın boyutunu açıklayan [bir oran](../standard-library/ratio.md) anlık lamasıdır.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|süre::period Typedef|Şablon parametresi `Period`ile eş anlamlısını temsil eder.|
|süre::rep Typedef|Şablon parametresi `Rep`ile eş anlamlısını temsil eder.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Süre](#duration)|Bir `duration` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Sayısı](#count)|Zaman aralığındasaat işaretçisi sayısını verir.|
|[Max](#max)|Statik. Şablon parametresinin `Ref`izin verilen maksimum değerini verir.|
|[Dk](#min)|Statik. Şablon parametresinin `Ref`izin verilebilen en düşük değerini verir.|
|[sıfır](#zero)|Statik. Sonuç olarak, `Rep`(0) döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[süre::operatör-](#operator-)|Nesnenin `duration` bir kopyasını, inkar edilen onay sayısıyla birlikte döndürür.|
|[süre::operatör--](#operator--)|Depolanan kene sayısını eriter.|
|[süre::operator=](#op_eq)|Depolanan onay sayısı modulo belirli bir değeri azaltır.|
|[süre::operator*=](#op_star_eq)|Depolanan kene sayısını belirli bir değerle çarpar.|
|[süre::operator/=](#op_div_eq)|Depolanan kene sayısını, belirli `duration` bir nesnenin onay sayısına böler.|
|[süre::operatör+](#op_add)|`*this` döndürür.|
|[süre::operator++](#op_add_add)|Depolanan kene sayısını artımlar.|
|[süre::operator+=](#op_add_eq)|Depolanan kene sayısına belirtilen `duration` nesnenin onay sayısını ekler.|
|[süre::operatör-=](#operator-_eq)|Depolanan kene sayısından `duration` belirli bir nesnenin onay sayısını çıkarır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono>

**Ad alanı:** std::chrono

## <a name="durationcount"></a><a name="count"></a>süre::say

Zaman aralığındaki saat işaretçilerinin sayısını alır.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığındaki saat sayısı işareteder.

## <a name="durationduration-constructor"></a><a name="duration"></a>süre::duration Constructor

Bir `duration` nesne inşa eder.

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);

template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>Parametreler

*Rep2*\
Kene sayısını temsil eden bir aritmetik türü.

*Dönem2*\
Kene `std::ratio` dönemini saniye birimleri cinsinden temsil edecek şablon uzmanlığı.

*R*\
Varsayılan dönemin kene sayısı.

*Dur*\
*Period2'ye*göre belirtilen dönemin kene sayısı2.

### <a name="remarks"></a>Açıklamalar

Varsayılan oluşturucu, baş harfe getirilmemiş bir nesne oluşturuyor. Boş ayraçlar kullanarak değer başlatma sıfır saat kene bir zaman aralığı temsil eden bir nesne başharf.

İkinci, bir şablon bağımsız değişken oluşturucu varsayılan bir dönem kullanarak *R* saat kene bir zaman aralığı temsil eden bir nesne inşa `std::ratio<1>`eder. Onay sayısının yuvarlanmasını önlemek için, kayan nokta türü olarak kabul edilemediği zaman kayan nokta `duration::rep` türü olarak kabul edilebilen bir gösterim türü *Temsilcisi2'den* bir süre nesnesi oluşturmak bir hatadır.

Üçüncü, iki şablon bağımsız değişken oluşturucu, uzunluğu *Dur*tarafından belirtilen zaman aralığı olan bir zaman aralığını temsil eden bir nesne inşa eder. Onay işareti sayısının kesilmesini önlemek için, türü hedef türüyle *birlikte ölçülemez* başka bir süre nesnesinden bir süre nesnesi oluşturmak bir hatadır.

Bir süre `D1` türü, kayan nokta türü `D2` `D2` olarak kabul edilemiyorsa ve [\<D1::period, D2::period>::type::den](../standard-library/ratio.md) 1 değildir ratio_divide, başka bir süre türüyle *ölçülemez.*

*Rep2* dolaylı olarak dönüştürülebilir `rep` ve `treat_as_floating_point<rep>`ya `treat_as_floating_point<Rep2>`doğru tutar ya da yanlış *tutar* *sürece,* ikinci yapıcı aşırı yük çözünürlüğü katılmaz. Daha fazla bilgi için [<type_traits>](../standard-library/type-traits.md)bakın.

Dönüşümde taşma yapılmazsa ve `treat_as_floating_point<rep>`her ikisi `ratio_divide<Period2, period>::den` de geçerli `treat_as_floating_point<Rep2>` *değilse*veya her ikisi de 1'e eşit sayılmadığı ve *yanlış tuttuğu sürece,* üçüncü oluşturucu aşırı yük çözünürlüğüne katılmaz. Daha fazla bilgi için [<type_traits>](../standard-library/type-traits.md)bakın.

## <a name="durationmax"></a><a name="max"></a>süre::max

Şablon parametre türü `Ref`değerleri için üst sınırı döndüren statik yöntem.

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döner. `duration(duration_values<rep>::max())`

## <a name="durationmin"></a><a name="min"></a>süre::dk

Şablon parametre türü `Ref`değerleri için alt sınırı döndüren statik yöntem.

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Dönüş Değeri

Aslında, döner. `duration(duration_values<rep>::min())`

## <a name="durationoperator-"></a><a name="operator-"></a>süre::operatör-

Nesnenin `duration` bir kopyasını, inkar edilen onay sayısıyla birlikte döndürür.

```cpp
constexpr duration operator-() const;
```

## <a name="durationoperator--"></a><a name="operator--"></a>süre::operatör--

Depolanan kene sayısını eriter.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem `*this`döndürür.

İkinci yöntem, kararnameden `*this` önce yapılan bir kopyasını döndürür.

## <a name="durationoperator"></a><a name="op_eq"></a>süre::operator=

Depolanan onay sayısı modulo belirli bir değeri azaltır.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

*Div*\
İlk yöntem için *Div* bir kene sayısını temsil eder. İkinci yöntem için *Div,* kene sayısı içeren bir `duration` nesnedir.

### <a name="return-value"></a>Dönüş Değeri

Modulo işlemi yapıldıktan sonra `duration` nesne.

## <a name="durationoperator"></a><a name="op_star_eq"></a>süre::operator*=

Depolanan kene sayısını belirli bir değerle çarpar.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>Parametreler

*Mult*\
`duration::rep`Tarafından belirtilen türün değeri.

### <a name="return-value"></a>Dönüş Değeri

Çarpma `duration` işleminden sonra nesne gerçekleştirilir.

## <a name="durationoperator"></a><a name="op_div_eq"></a>süre::operator/=

Depolanan onay sayısını belirli bir değere böler.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>Parametreler

*Div*\
`duration::rep`Tarafından belirtilen türün değeri.

### <a name="return-value"></a>Dönüş Değeri

Bölme `duration` yapıldıktan sonra nesne.

## <a name="durationoperator"></a><a name="op_add"></a>süre::operatör+

`*this` döndürür.

```cpp
constexpr duration operator+() const;
```

## <a name="durationoperator"></a><a name="op_add_add"></a>süre::operator++

Depolanan kene sayısını artımlar.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem `*this`döndürür.

İkinci yöntem, artıştan `*this` önce yapılan bir kopyasını döndürür.

## <a name="durationoperator"></a><a name="op_add_eq"></a>süre::operator+=

Depolanan kene sayısına belirtilen `duration` nesnenin onay sayısını ekler.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Dur*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Ekleme `duration` yapıldıktan sonra nesne.

## <a name="durationoperator-"></a><a name="operator-_eq"></a>süre::operatör-=

Depolanan kene sayısından `duration` belirli bir nesnenin onay sayısını çıkarır.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

*Dur*\
Bir `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Çıkarma `duration` yapıldıktan sonra nesne.

## <a name="durationzero"></a><a name="zero"></a>süre::sıfır

`duration(duration_values<rep>::zero())` döndürür.

```cpp
static constexpr duration zero();
```

## <a name="durationoperator-mod"></a><a name="op_mod_eq"></a>süre::operatör mod=

Depolanan onay sayısını azaltır modulo Div veya Div.count().

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

*Div*\
Bir süre nesnesi veya kene sayar temsil eden bir değer olan bölen.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi depolanan onay sayısı modulo Div azaltır ve * bu döndürür. İkinci üye işlev, depolanan onay sayısı modulo Div.count() azaltır ve bunu döndürür. \*

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)\
[duration_values Yapısı](../standard-library/duration-values-structure.md)
