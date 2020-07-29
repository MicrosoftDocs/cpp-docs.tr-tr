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
ms.openlocfilehash: dcc1f4bf1ce25890945f1d9e207f2363122c0ad2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217499"
---
# <a name="shared_future-class"></a>shared_future Sınıfı

*Zaman uyumsuz bir dönüş nesnesi*tanımlar. [Gelecekteki](../standard-library/future-class.md) bir nesnenin aksine, *zaman uyumsuz bir sağlayıcı* herhangi bir sayıda `shared_future` nesneyle ilişkilendirilebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>Açıklamalar

`valid` `operator=` Boş bir nesne üzerindeki,, ve yıkıcının dışında herhangi bir yöntemi çağırmayın `shared_future` . *empty*

`shared_future`nesneler eşitlenmemiş. Birden çok iş parçacığından aynı nesne üzerindeki yöntemlerin çağrılması öngörülemeyen sonuçlara sahip bir veri Race tanıtır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[shared_future](#shared_future)|Bir `shared_future` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Al](#get)|*İlişkili zaman uyumsuz durumda*depolanan sonucu alır.|
|[geçerli](#valid)|Nesnenin boş olup olmadığını belirtir.|
|[bekleneceğini](#wait)|İlişkili zaman uyumsuz durum hazırlanana kadar geçerli iş parçacığını engeller.|
|[wait_for](#wait_for)|İlişkili zaman uyumsuz duruma kadar veya belirtilen süre geçene kadar engeller.|
|[wait_until](#wait_until)|İlişkili zaman uyumsuz durum hazırlanana veya belirli bir zaman noktasına kadar engeller.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[shared_future:: operator =](#op_eq)|Yeni bir ilişkili zaman uyumsuz durum atar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<future>

**Ad alanı:** std

## <a name="shared_futureget"></a><a name="get"></a>shared_future:: Get

*İlişkili zaman uyumsuz durumda*depolanan sonucu alır.

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>Açıklamalar

Sonuç bir özel durumdur, yöntemi onu yeniden atar. Aksi takdirde sonuç döndürülür.

Bu yöntem, sonucu almadan önce, ilişkili zaman uyumsuz durum hazırlanana kadar geçerli iş parçacığını engeller.

Kısmi `shared_future<Ty&>` özelleşme için, saklı değer, geri dönüş değeri olarak *zaman uyumsuz sağlayıcıya* geçirilen nesneye bir başvuru sağlar.

Özelleştirme için depolanan değer olmadığından `shared_future<void>` , yöntemi döndürür **`void`** .

## <a name="shared_futureoperator"></a><a name="op_eq"></a>shared_future:: operator =

Belirtilen bir nesneden *ilişkili bir zaman uyumsuz durumu* aktarır.

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `shared_future` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

İlk operatör için, artık işlemden sonra ilişkili bir zaman uyumsuz duruma *sahip değildir.*

İkinci yöntemde, ilişkili zaman uyumsuz durumunu *sağ* sürdürür.

## <a name="shared_futureshared_future-constructor"></a><a name="shared_future"></a>shared_future:: shared_future Oluşturucusu

Bir `shared_future` nesnesi oluşturur.

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>Parametreler

*Right*\
[Gelecek](../standard-library/future-class.md) veya `shared_future` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `shared_future` *ilişkili zaman uyumsuz durumu*olmayan bir nesne oluşturur.

İkinci ve üçüncü oluşturucular bir nesne oluşturur `shared_future` ve ilişkili zaman uyumsuz durumu *sağdan*aktarır. *Artık ilişkili* bir zaman uyumsuz duruma sahip değil.

Dördüncü Oluşturucu, `shared_future` ilişkili zaman uyumsuz duruma sahip bir nesneyi *sağ*olarak oluşturur.

## <a name="shared_futurevalid"></a><a name="valid"></a>shared_future:: geçerli

Nesnenin *ilişkili bir zaman uyumsuz duruma*sahip olup olmadığını belirtir.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesnenin ilişkili bir zaman uyumsuz durumu varsa; Aksi takdirde, **`false`** .

## <a name="shared_futurewait"></a><a name="wait"></a>shared_future:: wait

*İlişkili zaman uyumsuz durum* *hazırlanana*kadar geçerli iş parçacığını engeller.

```cpp
void wait() const;
```

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durum, yalnızca zaman uyumsuz sağlayıcısı bir dönüş değeri depolamışsa veya bir özel durum depolamışsa kullanılabilir.

## <a name="shared_futurewait_for"></a><a name="wait_for"></a>shared_future:: wait_for

İlişkili zaman uyumsuz durum *hazırlanana* veya belirli bir süre geçene kadar geçerli iş parçacığını engeller.

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Parametreler

*Rel_time*\
Bir zaman hatası: iş parçacığının engellediği maksimum zaman aralığını belirten [:d uration](../standard-library/duration-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Dönme nedeninizi belirten bir [future_status](../standard-library/future-enums.md#future_status) .

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durum *, yalnızca zaman* uyumsuz sağlayıcısı bir dönüş değeri depolamışsa veya bir özel durum depolamışsa kullanılabilir.

## <a name="shared_futurewait_until"></a><a name="wait_until"></a>shared_future:: wait_until

İlişkili zaman uyumsuz durum *hazırlanana* veya belirtilen bir zaman noktasına gelene kadar geçerli iş parçacığını engeller.

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Parametreler

*Abs_time*\
İş parçacığının engellemesini kaldırmak için geçen süreyi belirten bir zaman [hatası:: time_point](../standard-library/time-point-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Dönme nedeninizi belirten bir [future_status](../standard-library/future-enums.md#future_status) .

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durum, yalnızca zaman uyumsuz sağlayıcısı bir dönüş değeri depolamışsa veya bir özel durum depolamışsa kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
