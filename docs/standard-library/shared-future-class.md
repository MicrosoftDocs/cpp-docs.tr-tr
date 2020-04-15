---
title: shared_future Sınıfı
ms.date: 11/04/2016
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
helpviewer_keywords:
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.openlocfilehash: 65ea01a9ced1ca69cd1b1526e7594c4b54387553
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336777"
---
# <a name="shared_future-class"></a>shared_future Sınıfı

Bir *eşzamanlı geri dönüş nesnesi*açıklar. [Gelecekteki](../standard-library/future-class.md) bir nesnenin aksine, *bir eşzamanlı sağlayıcı* herhangi bir `shared_future` sayıda nesneyle ilişkilendirilebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>Açıklamalar

Boş bir nesnenin `valid`üzerinde `operator=`, ve yıkıcı dışında herhangi `shared_future` bir yöntem *empty*aramayın.

`shared_future`nesneler eşitlenmez. Birden çok iş parçacığı aynı nesne üzerinde arama yöntemleri öngörülemeyen sonuçları olan bir veri yarışı tanıtır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Shared_future](#shared_future)|Bir `shared_future` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[get](#get)|*İlişkili eşzamanlı durumda*depolanan sonucu alır.|
|[Geçerli](#valid)|Nesnenin boş olup olmadığını belirtir.|
|[Bekle](#wait)|İlişkili asenkron durum hazır olana kadar geçerli iş parçacığı engeller.|
|[wait_for](#wait_for)|İlişkili eşzamanlı durum hazır olana veya belirtilen süre geçene kadar engeller.|
|[wait_until](#wait_until)|İlişkili eşzamanlı durum hazır olana veya belirli bir zaman alanına kadar engeller.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[shared_future::operator=](#op_eq)|Yeni ilişkili bir eşzamanlı durum atar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<gelecek>

**Ad alanı:** std

## <a name="shared_futureget"></a><a name="get"></a>shared_future::get

*İlişkili eşzamanlı durumda*depolanan sonucu alır.

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>Açıklamalar

Sonuç bir özel durumsa, yöntem onu yeniden atar. Aksi takdirde, sonuç döndürülür.

Sonucu almadan önce, ilişkili asynchronous durumu hazır olana kadar geçerli iş parçacığı engeller.

Kısmi uzmanlık için, `shared_future<Ty&>`depolanan değer etkili bir geri dönüş değeri olarak *asynchronous sağlayıcısına* geçirilen nesneye bir başvurudur.

Uzmanlık için depolanan değer `shared_future<void>`olmadığından, yöntem **geçersiz**döndürür.

## <a name="shared_futureoperator"></a><a name="op_eq"></a>shared_future::operator=

*İlişkili* bir eşzamanlı durumu belirtilen bir nesneden aktarın.

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `shared_future` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

İlk işleç *için, Sağ* artık işlemden sonra ilişkili bir eşzamanlı durum vardır.

İkinci yöntem *için, Sağ* ilişkili asynchronous durumunu korur.

## <a name="shared_futureshared_future-constructor"></a><a name="shared_future"></a>shared_future::shared_future Yapıcı

Bir `shared_future` nesne inşa eder.

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir [future](../standard-library/future-class.md) gelecek `shared_future` ya da nesne.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, ilişkili `shared_future` *asynchronous durumu*olmayan bir nesne yi inşa eder.

İkinci ve üçüncü kurucular `shared_future` bir nesne oluşturmak ve *sağ*ilişkili asynchronous durumu aktarın. *Sağ* artık ilişkili bir eşzamanlı durum vardır.

Dördüncü oluşturucu, `shared_future` *Sağ*ile aynı ilişkili asenkron duruma sahip bir nesne inşa eder.

## <a name="shared_futurevalid"></a><a name="valid"></a>shared_future::geçerli

Nesnenin ilişkili bir *asynchronous durumu*olup olmadığını belirtir.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

nesnenin ilişkili bir eşzamanlı durumu varsa **doğru;** aksi takdirde, **yanlış**.

## <a name="shared_futurewait"></a><a name="wait"></a>shared_future::bekle

*İlişkili asynchronous durumu* *hazır*olana kadar geçerli iş parçacığı engeller.

```cpp
void wait() const;
```

### <a name="remarks"></a>Açıklamalar

İlişkili bir eşzamanlı durum, yalnızca eşzamanlı sağlayıcısı bir iade değeri depolanmışsa veya bir özel durum depolarsa hazırdır.

## <a name="shared_futurewait_for"></a><a name="wait_for"></a>shared_future:wait_for

İlişkili eşzamanlı durum *hazır* olana veya belirli bir süre geçene kadar geçerli iş parçacığı engeller.

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
İş parçacığının bloklar ettiği maksimum zaman aralığını belirten [bir kronometre::duration](../standard-library/duration-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Geri dönme nedenini gösteren [bir future_status.](../standard-library/future-enums.md#future_status)

### <a name="remarks"></a>Açıklamalar

İlişkili bir eşzamanlı durum, yalnızca eşzamanlı sağlayıcısı bir iade değeri depolanmışsa veya bir özel durum depolarsa *hazırdır.*

## <a name="shared_futurewait_until"></a><a name="wait_until"></a>shared_future:wait_until

İlişkili eşzamanlı durum *hazır* olana veya belirli bir zaman noktasına gelene kadar geçerli iş parçacığı engeller.

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
Bir [kronometre:time_point](../standard-library/time-point-class.md) nesnesi, iş parçacığının engelini kaldırabileceği bir süre yi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Geri dönme nedenini gösteren [bir future_status.](../standard-library/future-enums.md#future_status)

### <a name="remarks"></a>Açıklamalar

İlişkili bir eşzamanlı durum, yalnızca eşzamanlı sağlayıcısı bir iade değeri depolanmışsa veya bir özel durum depolarsa hazırdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<gelecek>](../standard-library/future.md)
