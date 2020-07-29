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
ms.openlocfilehash: ac52429919f83a90a87141399952e248e18e0862
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220944"
---
# <a name="future-class"></a>future Sınıfı

*Zaman uyumsuz bir dönüş nesnesi*tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class future;
```

## <a name="remarks"></a>Açıklamalar

Her standart *zaman uyumsuz sağlayıcı* , türü bu şablonun örneklenmesi olan bir nesne döndürür. Bir `future` nesnesi, ilişkili olduğu zaman uyumsuz sağlayıcıya tek erişim sağlar. Aynı zaman uyumsuz sağlayıcıyla ilişkili birden fazla zaman uyumsuz dönüş nesnesine ihtiyacınız varsa, `future` nesneyi [shared_future](../standard-library/shared-future-class.md) nesnesine kopyalayın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[yayımlanacak](#future)|Bir `future` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Al](#get)|İlişkili zaman uyumsuz durumda depolanan sonucu alır.|
|[paylaş](#share)|Nesnesini bir öğesine dönüştürür `shared_future` .|
|[geçerli](#valid)|Nesnenin boş olup olmadığını belirtir.|
|[bekleneceğini](#wait)|İlişkili zaman uyumsuz durum hazırlanana kadar geçerli iş parçacığını engeller.|
|[wait_for](#wait_for)|İlişkili zaman uyumsuz duruma kadar veya belirtilen süre geçene kadar engeller.|
|[wait_until](#wait_until)|İlişkili zaman uyumsuz durum hazırlanana veya belirli bir zaman noktasına kadar engeller.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Future:: operator =](#op_eq)|İlişkili zaman uyumsuz durumu belirtilen bir nesneden aktarır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<future>

**Ad alanı:** std

## <a name="futurefuture-constructor"></a><a name="future"></a>Future:: Future Oluşturucusu

Bir `future` nesnesi oluşturur.

```cpp
future() noexcept;
future(future&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bir `future` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `future` ilişkili zaman uyumsuz durumu olmayan bir nesne oluşturur.

İkinci Oluşturucu bir nesne oluşturur `future` ve ilişkili zaman uyumsuz durumu *diğer*öğesinden aktarır. *Artık ilişkili* bir zaman uyumsuz duruma sahip değildir.

## <a name="futureget"></a><a name="get"></a>Future:: Get

İlişkili zaman uyumsuz durumda depolanan sonucu alır.

```cpp
Ty get();
```

### <a name="return-value"></a>Dönüş Değeri

Sonuç bir özel durumdur, yöntemi onu yeniden atar. Aksi takdirde sonuç döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sonucu almadan önce, ilişkili zaman uyumsuz durum hazırlanana kadar geçerli iş parçacığını engeller.

Kısmi `future<Ty&>` özelleşme için, saklı değer, geri dönüş değeri olarak zaman uyumsuz Sağlayıcıya geçirilen nesneye bir başvuru sağlar.

Özelleştirme için depolanan değer olmadığından `future<void>` , yöntemi döndürür **`void`** .

Diğer uzmanlıklardan Yöntem, dönüş değerini saklı değerden taşımaktadır. Bu nedenle, bu yöntemi yalnızca bir kez çağırın.

## <a name="futureoperator"></a><a name="op_eq"></a>Future:: operator =

Belirtilen bir nesneden ilişkili bir zaman uyumsuz durumu aktarır.

```cpp
future& operator=(future&& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `future` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Aktarımdan *sonra, artık* ilişkili bir zaman uyumsuz duruma sahip değildir.

## <a name="futureshare"></a><a name="share"></a>Future:: Share

Nesneyi [shared_future](../standard-library/shared-future-class.md) nesnesine dönüştürür.

```cpp
shared_future<Ty> share();
```

### <a name="return-value"></a>Dönüş Değeri

`shared_future(move(*this))`

## <a name="futurevalid"></a><a name="valid"></a>geleceğe yönelik:: geçerli

Nesnenin ilişkili bir zaman uyumsuz duruma sahip olup olmadığını belirtir.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesnenin ilişkili bir zaman uyumsuz durumu varsa; Aksi takdirde, **`false`** .

## <a name="futurewait"></a><a name="wait"></a>daha sonra:: wait

İlişkili zaman uyumsuz durum *hazırlanana*kadar geçerli iş parçacığını engeller.

```cpp
void wait() const;
```

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durum *, yalnızca zaman* uyumsuz sağlayıcısı bir dönüş değeri depolamışsa veya bir özel durum depolamışsa kullanılabilir.

## <a name="futurewait_for"></a><a name="wait_for"></a>daha sonra:: wait_for

İlişkili zaman uyumsuz durum *hazırlanana* veya belirli bir zaman aralığı geçene kadar geçerli iş parçacığını engeller.

```cpp
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman hatası: iş parçacığının engellediği maksimum zaman aralığını belirten [:d uration](../standard-library/duration-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Dönme nedeninizi belirten bir [future_status](../standard-library/future-enums.md#future_status) .

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durum, yalnızca zaman uyumsuz sağlayıcısı bir dönüş değeri depolamışsa veya bir özel durum depolamışsa kullanılabilir.

## <a name="futurewait_until"></a><a name="wait_until"></a>daha sonra:: wait_until

İlişkili zaman uyumsuz durum *hazırlanana* veya belirtilen bir zaman noktasına gelene kadar geçerli iş parçacığını engeller.

```cpp
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
İş parçacığının engellemesini kaldırmak için geçen süreyi belirten bir zaman [hatası:: time_point](../standard-library/time-point-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Dönme nedeninizi belirten bir [future_status](../standard-library/future-enums.md#future_status) .

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durum *, yalnızca zaman* uyumsuz sağlayıcısı bir dönüş değeri depolamışsa veya bir özel durum depolamışsa kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
