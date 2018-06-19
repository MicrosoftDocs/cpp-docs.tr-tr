---
title: Duration sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::duration
- chrono/std::chrono::duration::duration
- chrono/std::chrono::duration::count
- chrono/std::chrono::duration::max
- chrono/std::chrono::duration::min
- chrono/std::chrono::duration::zero
dev_langs:
- C++
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::chrono [C++], duration
ms.workload:
- cplusplus
ms.openlocfilehash: fe02890ce8d8dcde099f4b91b23c770b2e36c96d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847952"
---
# <a name="duration-class"></a>duration Sınıfı

Tutan bir türünü açıklayan bir *zaman aralığı*, iki zaman noktası arasında geçen süre olduğu.

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

Şablon bağımsız değişken `Rep` zaman aralığını saat sayısı tutmak için kullanılan türünü açıklar. Şablon bağımsız değişken `Period` bir, oluşturulmadan [oranı](../standard-library/ratio.md) her değer çizgisi temsil eden aralığın boyutunu açıklar.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|Duration::Period Typedef|Şablon parametresi için bir eş anlamlı temsil eden `Period`.|
|Duration::Rep Typedef|Şablon parametresi için bir eş anlamlı temsil eden `Rep`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Süre](#duration)|Oluşturan bir `duration` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Sayısı](#count)|Zaman aralığı içinde saat vuruşlarını sayısını döndürür.|
|[max](#max)|Statik. Şablon parametresi izin verilen en büyük değerini döndürür `Ref`.|
|[Min](#min)|Statik. Şablon parametresi izin verilen en düşük değer döndürür `Ref`.|
|[Sıfır](#zero)|Statik. Uygulamada döndürür `Rep`(0).|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Duration::operator-](#operator-)|Bir kopyasını döndürür `duration` çevrilerek tık sayısı ile birlikte nesnesi.|
|[Duration::operator--](#operator--)|Azaltır depolanan değer çizgilerinin sayısı.|
|[Duration::operator =](#op_eq)|Belirtilen bir değeri modulo depolanan değer çizgisi sayısını indirir.|
|[Duration::operator * =](#op_star_eq)|Saklı tık sayısı belirtilen bir değerle çarpar.|
|[Duration::operator / =](#op_div_eq)|Belirtilen değer çizgisi sayısını tarafından depolanan değer sayısı böler `duration` nesnesi.|
|[Duration::operator +](#op_add)|Döndürür `*this`.|
|[Duration::operator ++](#op_add_add)|Depolanan değer çizgisi sayısını artırır.|
|[Duration::operator +=](#op_add_eq)|Belirtilen değer çizgisi sayısını ekler `duration` saklı tık sayısı nesnesine.|
|[Duration::operator-=](#operator-_eq)|Belirtilen değer çizgisi sayısını çıkartır `duration` saklı tık sayısı nesnesinden.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="count"></a>  Duration::Count

Zaman aralığı içinde saat vuruşlarını sayısını alır.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığı içinde saat vuruşlarını sayısı.

## <a name="duration"></a>  Duration::Duration Oluşturucusu

Oluşturan bir `duration` nesnesi.

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);


template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>Parametreler

`Rep2` Onay işareti sayısını temsil eden bir aritmetik türü.

`Period2` A `std::ratio` şablonu uzmanlık saniye birimlerindeki onay süreyi temsil eder.

`R` Varsayılan dönem sayısı.

`Dur` Tarafından belirtilen dönem sayısı `Period2`.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu başlatılmamış bir nesne oluşturur. Değer başlatma boş küme ayraçları kullanarak bir zaman aralığı sıfır saat vuruşlarını temsil eden bir nesne başlatır.

Bir şablon bağımsız değişken Oluşturucu bir nesne oluşturur, ikinci temsil eden bir zaman aralığı `R` saati bir varsayılan süre kullanarak çizgilerine `std::ratio<1>`. Gösterimi türünden süresi nesnesi oluşturmak için bir hata olmasından yuvarlama işaret sayıları, önlemek için `Rep2` , kabul bir kayan nokta ne zaman yazın `duration::rep` kayan noktalı bir tür olarak kabul edemez.

Üçüncü iki şablon bağımsız değişken Oluşturucu uzunluğunu tarafından belirtilen zaman aralığı olan bir zaman aralığı temsil eden bir nesne oluşturur `Dur`. İşaret sayıları kesilmesi önlemek için türü olan başka bir süre nesnesinden süresi nesnesi oluşturmak için bir hata olduğundan *incommensurable* hedef türüne sahip.

Bir süre türü `D1` olan *incommensurable* başka bir süre türüyle `D2` varsa `D2` kayan noktalı bir tür olarak kabul ve [ratio_divide\<D1::period, D2:: Dönem >:: type::den](../standard-library/ratio.md) 1 değil.

Sürece `Rep2` örtük olarak parametresinin `rep` ve her iki `treat_as_floating_point<rep>` *doğru kalıp* veya `treat_as_floating_point<Rep2>` *false tutan*, ikinci oluşturucu içinde katılmıyor aşırı yükleme çözümü. Daha fazla bilgi için bkz: [< type_traits >](../standard-library/type-traits.md).

Taşma dönüştürme işleminden sürece ve `treat_as_floating_point<rep>` *geçerlidir*, veya her ikisini de `ratio_divide<Period2, period>::den` 1'e eşittir ve `treat_as_floating_point<Rep2>` *false tutan*, üçüncü oluşturucusu içinde katılmıyor aşırı yükleme çözümü. Daha fazla bilgi için bkz: [< type_traits >](../standard-library/type-traits.md).

## <a name="max"></a>  Duration::Max

Şablon parametresi türü değerleri için üst sınır döndüren statik yöntem `Ref`.

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamada döndürür `duration(duration_values<rep>::max())`.

## <a name="min"></a>  Duration::Min

Şablon parametresi türü değerleri için alt sınır döndüren statik yöntem `Ref`.

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamada döndürür `duration(duration_values<rep>::min())`.

## <a name="duration__operator-"></a>  Duration::operator-

Bir kopyasını döndürür `duration` çevrilerek tık sayısı ile birlikte nesnesi.

```cpp
constexpr duration operator-() const;
```

## <a name="duration__operator--"></a>  Duration::operator--

Azaltır depolanan değer çizgilerinin sayısı.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürür `*this`.

İkinci yöntem kopyasını döndürür `*this` önce azaltma yapılır.

## <a name="op_eq"></a>  Duration::operator =

Belirtilen bir değeri modulo depolanan değer çizgisi sayısını indirir.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

`Div` İlk yöntem için `Div` değer çizgisi sayısını temsil eder. İkinci yöntem için `Div` olan bir `duration` tık sayısı içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

`duration` Sonra nesne işlemi gerçekleştirilir.

## <a name="op_star_eq"></a>  Duration::operator * =

Saklı tık sayısı belirtilen bir değerle çarpar.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>Parametreler

`Mult` Tarafından belirtilen türde bir değer `duration::rep`.

### <a name="return-value"></a>Dönüş Değeri

`duration` Çarpma gerçekleştirildikten sonra nesnesi.

## <a name="op_div_eq"></a>  Duration::operator / =

Depolanan değer çizgisi sayısını belirtilen değere böler.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>Parametreler

`Div` Tarafından belirtilen türde bir değer `duration::rep`.

### <a name="return-value"></a>Dönüş Değeri

`duration` Bölme işlemi yapıldıktan sonra nesnesi.

## <a name="op_add"></a>  Duration::operator +

Döndürür `*this`.

```cpp
constexpr duration operator+() const;
```

## <a name="op_add_add"></a>  Duration::operator ++

Depolanan değer çizgisi sayısını artırır.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem döndürür `*this`.

İkinci yöntem kopyasını döndürür `*this` önce artışı yapılan.

## <a name="op_add_eq"></a>  Duration::operator +=

Belirtilen değer çizgisi sayısını ekler `duration` saklı tık sayısı nesnesine.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

`Dur` A `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`duration` Eklenmesi gerçekleştirildikten sonra nesnesi.

## <a name="duration__operator-_eq"></a>  Duration::operator-=

Belirtilen değer çizgisi sayısını çıkartır `duration` saklı tık sayısı nesnesinden.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parametreler

`Dur` A `duration` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`duration` Çıkarma işlemi yapıldıktan sonra nesnesi.

## <a name="zero"></a>  Duration::Zero

Döndürür `duration(duration_values<rep>::zero())`.

```cpp
static constexpr duration zero();
```

## <a name="op_mod_eq"></a>  Duration::operator mod =

Div veya Div.count() modulo depolanan değer çizgisi sayısını indirir.

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parametreler

`Div` Bir süre nesnesi ya da işaret sayıları temsil eden bir değer bölen.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi Div modulo depolanan değer çizgisi sayısını azaltır ve döndürür * bu. İkinci üye işlevi Div.count() modulo depolanan değer çizgisi sayısını azaltır ve döndürür \*bu.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
[duration_values Yapısı](../standard-library/duration-values-structure.md)<br/>
