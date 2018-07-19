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
ms.openlocfilehash: f27162b1dfc96b4797184b3fefc1ad8ecc464f55
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955000"
---
# <a name="sharedfuture-class"></a>shared_future Sınıfı

Açıklayan bir *zaman uyumsuz dönüş nesnesi*. Tersine ile bir [gelecekteki](../standard-library/future-class.md) nesnesi bir *zaman uyumsuz sağlayıcıyı* herhangi bir sayıda ile ilişkilendirilebilir `shared_future` nesneleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>Açıklamalar

Herhangi bir yöntemin dışındaki çağırmayın `valid`, `operator=`ve yok edici temel bir `shared_future` nesne bu *boş*.

`shared_future` nesneleri eşitlenmez. Birden fazla iş parçacığından aynı nesne üzerinde yöntemleri çağırmak, öngörülemeyen sonuçlara sahip bir veri yarış tanıtır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[shared_future](#shared_future)|Oluşturur bir `shared_future` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get](#get)|Depolanan sonucu alır *ilişkili zaman uyumsuz durumu*.|
|[valid](#valid)|Nesne boş değil olup olmadığını belirtir.|
|[bekleme](#wait)|İlişkili zaman uyumsuz durum hazır olana kadar geçerli iş parçacığını engeller.|
|[wait_for](#wait_for)|Blokları kadar ilişkili zaman uyumsuz durum hazır olana veya belirtilen zamana kadar geçen.|
|[wait_until](#wait_until)|Hazır veya belirli bir noktaya kadar zamanında ilişkili zaman uyumsuz duruma kadar engeller.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[shared_future::operator =](#op_eq)|Yeni bir ilişkili zaman uyumsuz durumu atar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecek >

**Namespace:** std

## <a name="get"></a>  shared_future::get

Depolanan sonucu alır *ilişkili zaman uyumsuz durumu*.

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>Açıklamalar

Sonuç bir özel durum ise, yöntem, yeniden oluşturur. Aksi halde, sonuç döndürülür.

Sonuç almadan önce ilişkili zaman uyumsuz durum hazır olana kadar bu yöntem geçerli iş parçacığını engeller.

Kısmi özelleştirmesi için `shared_future<Ty&>`, saklanan değer etkili bir şekilde geçildi nesnesine bir başvuru olduğundan *zaman uyumsuz sağlayıcıyı* dönüş değeri.

Özelleştirme için kayıtlı hiçbir değer var olduğundan `shared_future<void>`, yöntem döndürür **void**.

## <a name="op_eq"></a>  shared_future::operator =

Aktarımları bir *ilişkili zaman uyumsuz durumu* belirtilen bir nesneden.

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>Parametreler

*Sağ* A `shared_future` nesne.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

İlk işleç *sağ* artık işleminden sonra bir ilişkili zaman uyumsuz duruma sahip.

İkinci yöntem *sağ* ilişkili zaman uyumsuz durumu korur.

## <a name="shared_future"></a>  shared_future::shared_future Oluşturucusu

Oluşturur bir `shared_future` nesne.

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>Parametreler

*Sağ* A [gelecekteki](../standard-library/future-class.md) veya `shared_future` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu yapıları bir `shared_future` hiçbir nesne *ilişkili zaman uyumsuz durumu*.

İkinci ve üçüncü oluşturucular oluşturmak bir `shared_future` nesnesini ve ilişkili zaman uyumsuz durumu aktarım *sağ*. *Sağ* artık bir ilişkili zaman uyumsuz duruma sahip değil.

Dördüncü Oluşturucu yapıları bir `shared_future` nesnesi aynı ilişkilendirilmiş zaman uyumsuz duruma olarak *sağ*.

## <a name="valid"></a>  shared_future::valid

Nesne olup olmadığını belirten bir *ilişkili zaman uyumsuz durumu*.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilişkili zaman uyumsuz durumu; nesne varsa, aksi takdirde, **false**.

## <a name="wait"></a>  shared_future::wait

Kadar geçerli iş parçacığını engeller *ilişkili zaman uyumsuz durumu* olduğu *hazır*.

```cpp
void wait() const;
```

### <a name="remarks"></a>Açıklamalar

Zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanan bir ilişkili zaman uyumsuz durum hazır olur.

## <a name="wait_for"></a>  shared_future::wait_for

İlişkili zaman uyumsuz duruma gelene kadar geçerli iş parçacığını engeller *hazır* veya belirtilen süresi bitene kadar.

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Parametreler

*Rel_time* A [chrono::duration](../standard-library/duration-class.md) maksimum zaman aralığını belirten bir nesne, iş parçacığını engeller.

### <a name="return-value"></a>Dönüş Değeri

A [future_status](../standard-library/future-enums.md#future_status) döndüren nedenini gösterir.

### <a name="remarks"></a>Açıklamalar

İlişkili bir zaman uyumsuz durumu *hazır* yalnızca zaman uyumsuz sağlayıcısını bir dönüş değeri depolanan veya bir özel durum depolanan varsa.

## <a name="wait_until"></a>  shared_future::wait_until

İlişkili zaman uyumsuz duruma gelene kadar geçerli iş parçacığını engeller *hazır* veya belirtilen zaman noktası kadar sonra.

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Parametreler

*Abs_time* A [chrono::time_point](../standard-library/time-point-class.md) nesnesini geçmesi iş parçacığını engellemesini bir süreyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

A [future_status](../standard-library/future-enums.md#future_status) döndüren nedenini gösterir.

### <a name="remarks"></a>Açıklamalar

Zaman uyumsuz sağlayıcısını yalnızca varsa veya dönüş değeri depolanan bir özel durum depolanan bir ilişkili zaman uyumsuz durum hazır olur.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<gelecek >](../standard-library/future.md)<br/>
