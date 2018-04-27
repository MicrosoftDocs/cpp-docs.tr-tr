---
title: '&lt;Gelecekteki&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
caps.latest.revision: 11
manager: ghogen
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: e796420f285685c448b3422fe68f0a93daa13fdf
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltfuturegt-functions"></a>&lt;Gelecekteki&gt; işlevleri

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[Değiştirme](#swap)|

## <a name="async"></a>  Zaman uyumsuz

Temsil eden bir *zaman uyumsuz sağlayıcısı*.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Parametreler

`policy` A [başlatma](../standard-library/future-enums.md#launch) değeri.

### <a name="remarks"></a>Açıklamalar

Kısaltmalar tanımları:

|||
|-|-|
|*dfn*|Arama sonucu `decay_copy(forward<Fn>(fn))`.|
|*dargs*|Çağrı sonuçları `decay_copy(forward<ArgsTypes>(args...))`.|
|*Ty*|Türü `result_of<Fn(ArgTypes...)>::type`.|

İlk şablon işlevi döndürür `async(launch::any, fn, args...)`.

İkinci işlevi döndürür bir `future<Ty>` nesnesindeki *zaman uyumsuz durum ilişkili* değerlerini birlikte bir sonuç tutan *dfn* ve *dargs* ve bir iş parçacığı ayrı bir iş parçacığı yürütme yönetmek için nesnesi.

Sürece `decay<Fn>::type` bir tür başlatma dışında ikinci işlev aşırı yük çözüm katılmıyor.

Varsa `policy` olan `launch::any`, işlevi seçebilirsiniz `launch::async` veya `launch::deferred`. Bu uygulama, işlevini kullanıyor `launch::async`.

Varsa `policy` olan `launch::async`, işlevi değerlendiren bir iş parçacığı oluşturan `INVOKE(dfn, dargs..., Ty)`. İş parçacığı için sonuçları beklemeden oluşturduktan sonra işlevi döndürür. Sistem yeni bir iş parçacığı başlatamıyor, işlevi döndürürse bir [system_error](../standard-library/system-error-class.md) hata kodunu olan `resource_unavailable_try_again`.

Varsa `policy` olan `launch::deferred`, işlevi ilişkili zaman uyumsuz durumuna tutan olarak işaretler bir *işlevi ertelenmiş* ve döndürür. İlk yürürlükte hazır olmasını ilişkili zaman uyumsuz durumu için bekleyeceği zaman aşımına olmayan işlevi ertelenmiş işlevi değerlendirerek çağırır `INVOKE(dfn, dargs..., Ty)`.

Tüm durumlarda ilişkili zaman uyumsuz durumu `future` nesne ayarlı değil *hazır* değerlendirmesi kadar `INVOKE(dfn, dargs..., Ty)` , bir özel durum atma ya da normal olarak döndüren tamamlar. Bir durum oluştu, özel bir durum veya değerlendirme tarafından döndürülen herhangi bir değer ilişkili zaman uyumsuz durum sonucudur.

> [!NOTE]
> İçin bir `future`— ya da son [shared_future](../standard-library/shared-future-class.md)— kullanmaya göreve bağlı `std::async`, yıkıcı blokları görevi tamamlanmadıysa; bu iş parçacığı henüz arama diğer bir deyişle, onu engeller `.get()` veya `.wait()` ve görev hala çalışıyor. Varsa bir `future` alınan `std::async` taşındığı yerel kapsamı dışında kullandığı başka bir kod kendi yıkıcı paylaşılan durum hazır olmasını engelleyebilir farkında olmalıdır.

Sözde işlevi `INVOKE` tanımlanan [ \<işlevsel >](../standard-library/functional.md).

## <a name="future_category"></a>  future_category

Bir başvuru döndürür [error_category](../standard-library/error-category-class.md) ilişkili hataları belirtir nesne `future` nesneleri.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a>  make_error_code

Oluşturur bir [error_code](../standard-library/error-code-class.md) ile birlikte [error_category](../standard-library/error-category-class.md) belirtir nesne [gelecekteki](../standard-library/future-class.md) hataları.

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

`Errno` A [future_errc](../standard-library/future-enums.md#future_errc) bildirilen hatayı tanımlayan bir değer.

### <a name="return-value"></a>Dönüş Değeri

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a>  make_error_condition

Oluşturur bir [error_condition](../standard-library/error-condition-class.md) ile birlikte [error_category](../standard-library/error-category-class.md) belirtir nesne [gelecekteki](../standard-library/future-class.md) hataları.

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

`Errno` A [future_errc](../standard-library/future-enums.md#future_errc) bildirilen hatayı tanımlayan bir değer.

### <a name="return-value"></a>Dönüş Değeri

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>  Değiştirme

Alışverişleri *zaman uyumsuz durum ilişkili* bir `promise` , başka bir nesne.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

`Left` Sol `promise` nesnesi.

`Right` Sağa `promise` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[\<sonraki >](../standard-library/future.md)<br/>
