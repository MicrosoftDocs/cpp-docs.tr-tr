---
title: Future sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::future
- future/std::future::future
- future/std::future::get
- future/std::future::share
- future/std::future::valid
- future/std::future::wait
- future/std::future::wait_for
- future/std::future::wait_until
dev_langs:
- C++
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::future [C++]
- std::future [C++], future
- std::future [C++], get
- std::future [C++], share
- std::future [C++], valid
- std::future [C++], wait
- std::future [C++], wait_for
- std::future [C++], wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: e55f5d9759de0993f0202612e237bb778a195602
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106659"
---
# <a name="future-class"></a>future Sınıfı

Açıklayan bir *zaman uyumsuz dönüş nesnesi*.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class future;
```

## <a name="remarks"></a>Açıklamalar

Her standart *zaman uyumsuz sağlayıcıyı* Bu şablon örneği türü olan bir nesne döndürür. A `future` nesnesi ile ilişkili zaman uyumsuz sağlayıcıyı tek erişim sağlar. Aynı zaman uyumsuz sağlayıcı ile ilişkili birden çok zaman uyumsuz dönüş nesneleri gerekiyorsa, kopyalama `future` nesnesini bir [shared_future](../standard-library/shared-future-class.md) nesne.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Gelecekte](#future)|Oluşturur bir `future` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get](#get)|İlişkili zaman uyumsuz durumu içerisinde saklanan sonucu alır.|
|[Paylaş](#share)|Bir nesneye dönüştürür bir `shared_future`.|
|[valid](#valid)|Nesne boş değil olup olmadığını belirtir.|
|[bekleme](#wait)|İlişkili zaman uyumsuz durum hazır olana kadar geçerli iş parçacığını engeller.|
|[wait_for](#wait_for)|Blokları kadar ilişkili zaman uyumsuz durum hazır olana veya belirtilen zamana kadar geçen.|
|[wait_until](#wait_until)|Hazır veya belirli bir noktaya kadar zamanında ilişkili zaman uyumsuz duruma kadar engeller.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Future::operator =](#op_eq)|İlişkili zaman uyumsuz duruma, belirtilen bir nesneden aktarır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecek >

**Namespace:** std

## <a name="future"></a>  Future::Future Oluşturucusu

Oluşturur bir `future` nesne.

```cpp
future() noexcept;
future(future&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
A `future` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu yapıları bir `future` ilişkilendirilmiş zaman uyumsuz duruma sahip olmayan bir nesne.

İkinci oluşturucu yapıları bir `future` nesnesini ve ilişkili zaman uyumsuz durumu aktarır *diğer*. *Diğer* artık bir ilişkili zaman uyumsuz duruma sahip değil.

## <a name="get"></a>  Future::get

İlişkili zaman uyumsuz durumu içerisinde saklanan sonucu alır.

```cpp
Ty get();
```

### <a name="return-value"></a>Dönüş Değeri

Sonuç bir özel durum ise, yöntem, yeniden oluşturur. Aksi halde, sonuç döndürülür.

### <a name="remarks"></a>Açıklamalar

Sonuç almadan önce ilişkili zaman uyumsuz durum hazır olana kadar bu yöntem geçerli iş parçacığını engeller.

Kısmi özelleştirmesi için `future<Ty&>`, saklanan değer etkili bir şekilde bir dönüş değeri olarak zaman uyumsuz sağlayıcısına geçirilen nesne başvurudur.

Özelleştirme için kayıtlı hiçbir değer var olduğundan `future<void>`, yöntem döndürür **void**.

Diğer uzmanlıkları içinde yöntemin dönüş değeri depolanan değerden taşır. Bu nedenle, yalnızca bir kez bu yöntemi çağırın.

## <a name="op_eq"></a>  Future::operator =

Belirtilen bir nesneden bir ilişkili zaman uyumsuz durumu aktarır.

```cpp
future& operator=(future&& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
A `future` nesne.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Aktarım sonra *sağ* artık bir ilişkili zaman uyumsuz duruma sahip değil.

## <a name="share"></a>  Future::share

Bir nesneye dönüştürür bir [shared_future](../standard-library/shared-future-class.md) nesne.

```cpp
shared_future<Ty> share();
```

### <a name="return-value"></a>Dönüş Değeri

`shared_future(move(*this))`

## <a name="valid"></a>  Future::valid

Nesnenin ilişkili bir zaman uyumsuz duruma sahip olup olmadığını belirtir.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilişkili zaman uyumsuz durumu; nesne varsa, aksi takdirde, **false**.

## <a name="wait"></a>  Future::wait

İlişkili zaman uyumsuz duruma gelene kadar geçerli iş parçacığını engeller *hazır*.

```cpp
void wait() const;
```

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durumu *hazır* yalnızca zaman uyumsuz sağlayıcısını bir dönüş değeri depolanan veya bir özel durum depolanan varsa.

## <a name="wait_for"></a>  Future::wait_for

İlişkili zaman uyumsuz duruma gelene kadar geçerli iş parçacığını engeller *hazır* veya belirtilen zaman aralığı sona ermeden.

```cpp
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Parametreler

*Rel_time*<br/>
A [chrono::duration](../standard-library/duration-class.md) maksimum zaman aralığını belirten bir nesne, iş parçacığını engeller.

### <a name="return-value"></a>Dönüş Değeri

A [future_status](../standard-library/future-enums.md#future_status) döndüren nedenini gösterir.

### <a name="remarks"></a>Açıklamalar

Zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanan bir ilişkili zaman uyumsuz durum hazır olur.

## <a name="wait_until"></a>  Future::wait_until

İlişkili zaman uyumsuz duruma gelene kadar geçerli iş parçacığını engeller *hazır* veya belirtilen zaman noktası kadar sonra.

```cpp
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Parametreler

*Abs_time*<br/>
A [chrono::time_point](../standard-library/time-point-class.md) nesnesini geçmesi iş parçacığını engellemesini bir süreyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

A [future_status](../standard-library/future-enums.md#future_status) döndüren nedenini gösterir.

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durumu *hazır* yalnızca zaman uyumsuz sağlayıcısını bir dönüş değeri depolanan veya bir özel durum depolanan varsa.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<gelecek >](../standard-library/future.md)<br/>
