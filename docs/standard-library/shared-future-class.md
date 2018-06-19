---
title: shared_future sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
dev_langs:
- C++
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 2ac125b068de5111a2b98800956c12a0c979737f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859670"
---
# <a name="sharedfuture-class"></a>shared_future Sınıfı

Açıklayan bir *zaman uyumsuz dönüş nesnesi*. Tersine ile bir [gelecekteki](../standard-library/future-class.md) nesne, bir *zaman uyumsuz sağlayıcısı* herhangi bir sayıda ile ilişkilendirilebilir `shared_future` nesneleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>Açıklamalar

Herhangi bir yöntem dışında çağırmayın `valid`, `operator=`ve üzerinde yıkıcı bir `shared_future` nesne bu *boş*.

`shared_future` nesneleri eşitlenmez. Aynı nesne üzerinde birden çok iş parçacığından yöntemleri çağırma öngörülemeyen sonuçlara sahip bir veri yarış tanıtır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[shared_future](#shared_future)|Oluşturan bir `shared_future` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get](#get)|Depolanan sonucu alır *zaman uyumsuz durum ilişkili*.|
|[valid](#valid)|Nesne boş değil olup olmadığını belirtir.|
|[bekleme](#wait)|Zaman uyumsuz işlemin ilişkili durumu hazır olana kadar geçerli iş parçacığının engeller.|
|[wait_for](#wait_for)|İlişkili zaman uyumsuz durum kadar blokları hazır veya belirtilen zamana kadar geçen.|
|[wait_until](#wait_until)|Blokları ilişkili zaman uyumsuz durum kadar sürede hazır veya belirli bir noktaya kadar olur.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[shared_future::operator =](#op_eq)|Yeni bir ilişkili zaman uyumsuz durum atar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecekteki >

**Namespace:** std

## <a name="get"></a>  shared_future::get

Depolanan sonucu alır *zaman uyumsuz durum ilişkili*.

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>Açıklamalar

Sonuç bir özel durum ise, yöntem, yeniden oluşturur. Aksi takdirde, sonuç döndürülür.

Sonuç almadan önce ilişkili zaman uyumsuz durumu hazır olana kadar bu yöntem geçerli iş parçacığının engeller.

Kısmi uzmanlığı için `shared_future<Ty&>`, depolanan değer etkili bir şekilde geçirilmedi nesneye bir başvurusu olan *zaman uyumsuz sağlayıcısı* dönüş değeri olarak.

Özelleştirme için depolanan değer var olduğundan `shared_future<void>`, yöntem `void`.

## <a name="op_eq"></a>  shared_future::operator =

Aktarımları bir *zaman uyumsuz durum ilişkili* belirtilen bir nesneden.

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>Parametreler

`Right` A `shared_future` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

İlk operatöre `Right` ilişkili bir zaman uyumsuz durum sonra işlemi artık sahip değil.

İkinci yöntem için `Right` ilişkili zaman uyumsuz durumunu korur.

## <a name="shared_future"></a>  shared_future::shared_future Oluşturucusu

Oluşturan bir `shared_future` nesnesi.

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>Parametreler

`Right` A [gelecekteki](../standard-library/future-class.md) veya `shared_future` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu yapıları bir `shared_future` hiçbir nesne *zaman uyumsuz durum ilişkili*.

İkinci ve üçüncü oluşturucular oluşturmak bir `shared_future` nesne ve ilişkili zaman uyumsuz durumundan aktarım `Right`. `Right` artık ilişkili bir zaman uyumsuz durum yok.

Dördüncü Oluşturucusu yapıları bir `shared_future` aynı olan nesneyi ilişkili olarak zaman uyumsuz durum `Right`.

## <a name="valid"></a>  shared_future::valid

Nesne sahip olup olmadığını belirten bir *zaman uyumsuz durum ilişkili*.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

`true` nesnenin ilişkili bir zaman uyumsuz durum varsa; Aksi takdirde `false`.

## <a name="wait"></a>  shared_future::wait

Geçerli iş parçacığının kadar engeller *zaman uyumsuz durum ilişkili* olan *hazır*.

```cpp
void wait() const;
```

### <a name="remarks"></a>Açıklamalar

Zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanan ilişkili bir zaman uyumsuz durum hazırdır.

## <a name="wait_for"></a>  shared_future::wait_for

İlişkili zaman uyumsuz durum olana kadar geçerli iş parçacığının engeller *hazır* veya belirli bir süre geçti kadar.

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Parametreler

`Rel_time` A [chrono::duration](../standard-library/duration-class.md) en büyük zaman aralığını belirtir nesnesi, iş parçacığı engeller.

### <a name="return-value"></a>Dönüş Değeri

A [future_status](../standard-library/future-enums.md#future_status) döndürmek için nedenini gösterir.

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durum *hazır* zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanır.

## <a name="wait_until"></a>  shared_future::wait_until

İlişkili zaman uyumsuz durum olana kadar geçerli iş parçacığının engeller *hazır* veya belirtilen zaman noktası kadar sonra.

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Parametreler

`Abs_time` A [chrono::time_point](../standard-library/time-point-class.md) nesne geçmesi iş parçacığı engellemesini süreyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

A [future_status](../standard-library/future-enums.md#future_status) döndürmek için nedenini gösterir.

### <a name="remarks"></a>Açıklamalar

Zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanan ilişkili bir zaman uyumsuz durum hazırdır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<sonraki >](../standard-library/future.md)<br/>
