---
title: future Sınıfı
ms.date: 11/04/2016
f1_keywords:
- future/std::future
- future/std::future::future
- future/std::future::get
- future/std::future::share
- future/std::future::valid
- future/std::future::wait
- future/std::future::wait_for
- future/std::future::wait_until
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
helpviewer_keywords:
- std::future [C++]
- std::future [C++], future
- std::future [C++], get
- std::future [C++], share
- std::future [C++], valid
- std::future [C++], wait
- std::future [C++], wait_for
- std::future [C++], wait_until
ms.openlocfilehash: e71c750ddeb198faa3ae9c5960b2668c376241ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370712"
---
# <a name="future-class"></a>future Sınıfı

Bir *eşzamanlı geri dönüş nesnesi*açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class future;
```

## <a name="remarks"></a>Açıklamalar

Her standart *asynchronous sağlayıcı* türü bu şablonun bir anlık bir ani bir nesne döndürür. Nesne, `future` ilişkili olduğu eşzamanlı sağlayıcıya yalnızca erişim sağlar. Aynı eşil sağlayıcıyla ilişkili birden çok eşzamanlı iade nesnesine ihtiyacınız varsa, `future` nesneyi [shared_future](../standard-library/shared-future-class.md) bir nesneye kopyalayın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Gelecek](#future)|Bir `future` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[get](#get)|İlişkili eşzamanlı durumda depolanan sonucu alır.|
|[paylaş](#share)|Nesneyi bir `shared_future`.|
|[Geçerli](#valid)|Nesnenin boş olup olmadığını belirtir.|
|[Bekle](#wait)|İlişkili asenkron durum hazır olana kadar geçerli iş parçacığı engeller.|
|[wait_for](#wait_for)|İlişkili eşzamanlı durum hazır olana veya belirtilen süre geçene kadar engeller.|
|[wait_until](#wait_until)|İlişkili eşzamanlı durum hazır olana veya belirli bir zaman alanına kadar engeller.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[gelecek::operator=](#op_eq)|İlişkili asenkron durumu belirtilen bir nesneden aktarın.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<gelecek>

**Ad alanı:** std

## <a name="futurefuture-constructor"></a><a name="future"></a>gelecek::gelecekteki Constructor

Bir `future` nesne inşa eder.

```cpp
future() noexcept;
future(future&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*\
Bir `future` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, ilişkili `future` asynchronous durumu olmayan bir nesne yi inşa eder.

İkinci oluşturucu bir `future` nesne inşa eder ve ilişkili asenkron durumu *Diğer'den*aktarıyor. *Diğer* artık ilişkili bir eşzamanlı durum vardır.

## <a name="futureget"></a><a name="get"></a>gelecek::get

İlişkili eşzamanlı durumda depolanan sonucu alır.

```cpp
Ty get();
```

### <a name="return-value"></a>Dönüş Değeri

Sonuç bir özel durumsa, yöntem onu yeniden atar. Aksi takdirde, sonuç döndürülür.

### <a name="remarks"></a>Açıklamalar

Sonucu almadan önce, ilişkili asynchronous durumu hazır olana kadar geçerli iş parçacığı engeller.

Kısmi uzmanlık için, `future<Ty&>`depolanan değer etkili bir geri dönüş değeri olarak asynchronous sağlayıcısına geçirilen nesneye bir başvurudur.

Uzmanlık için depolanan değer `future<void>`olmadığından, yöntem **geçersiz**döndürür.

Diğer uzmanlıklarda yöntem, iade değerini depolanan değerden taşır. Bu nedenle, bu yöntemi yalnızca bir kez arayın.

## <a name="futureoperator"></a><a name="op_eq"></a>gelecek::operator=

İlişkili bir eşzamanlı durumu belirtilen bir nesneden aktarın.

```cpp
future& operator=(future&& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `future` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Aktarımdan sonra, *Sağ* artık ilişkili bir eşzamanlı durum vardır.

## <a name="futureshare"></a><a name="share"></a>gelecek::paylaş

Nesneyi [shared_future](../standard-library/shared-future-class.md) bir nesneye dönüştürür.

```cpp
shared_future<Ty> share();
```

### <a name="return-value"></a>Dönüş Değeri

`shared_future(move(*this))`

## <a name="futurevalid"></a><a name="valid"></a>gelecek::geçerli

Nesnenin ilişkili bir asynchronous durumu olup olmadığını belirtir.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

nesnenin ilişkili bir eşzamanlı durumu varsa **doğru;** aksi takdirde, **yanlış**.

## <a name="futurewait"></a><a name="wait"></a>gelecek::bekle

İlişkili asynchronous durumu *hazır*olana kadar geçerli iş parçacığı engeller.

```cpp
void wait() const;
```

### <a name="remarks"></a>Açıklamalar

İlişkili bir eşzamanlı durum, yalnızca eşzamanlı sağlayıcısı bir iade değeri depolanmışsa veya bir özel durum depolarsa *hazırdır.*

## <a name="futurewait_for"></a><a name="wait_for"></a>gelecek::wait_for

İlişkili eşzamanlı durum *hazır* olana veya belirli bir zaman aralığı geçene kadar geçerli iş parçacığı engeller.

```cpp
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
İş parçacığının bloklar ettiği maksimum zaman aralığını belirten [bir kronometre::duration](../standard-library/duration-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Geri dönme nedenini gösteren [bir future_status.](../standard-library/future-enums.md#future_status)

### <a name="remarks"></a>Açıklamalar

İlişkili bir eşzamanlı durum, yalnızca eşzamanlı sağlayıcısı bir iade değeri depolanmışsa veya bir özel durum depolarsa hazırdır.

## <a name="futurewait_until"></a><a name="wait_until"></a>gelecek::wait_until

İlişkili eşzamanlı durum *hazır* olana veya belirli bir zaman noktasına gelene kadar geçerli iş parçacığı engeller.

```cpp
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Bir [kronometre:time_point](../standard-library/time-point-class.md) nesnesi, iş parçacığının engelini kaldırabileceği bir süre yi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Geri dönme nedenini gösteren [bir future_status.](../standard-library/future-enums.md#future_status)

### <a name="remarks"></a>Açıklamalar

İlişkili bir eşzamanlı durum, yalnızca eşzamanlı sağlayıcısı bir iade değeri depolanmışsa veya bir özel durum depolarsa *hazırdır.*

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<gelecek>](../standard-library/future.md)
