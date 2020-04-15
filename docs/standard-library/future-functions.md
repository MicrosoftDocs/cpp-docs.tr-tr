---
title: '&lt;gelecekteki&gt; fonksiyonlar'
ms.date: 11/04/2016
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: 16c26212cac13602e981f42d8333518da90615fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370670"
---
# <a name="ltfuturegt-functions"></a>&lt;gelecekteki&gt; fonksiyonlar

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[Takas](#swap)|

## <a name="async"></a><a name="async"></a>Zaman uyumsuz

Bir *eşzamanlı sağlayıcıtemsil*eder.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Parametreler

*Ilkesi*\
[Fırlatma](../standard-library/future-enums.md#launch) değeri.

### <a name="remarks"></a>Açıklamalar

Kısaltmaların tanımları:

|||
|-|-|
|*dfn*|Aramanın `decay_copy(forward<Fn>(fn))`sonucu.|
|*dargs*|Aramaların `decay_copy(forward<ArgsTypes>(args...))`sonuçları.|
|*Ty*|Türü `result_of<Fn(ArgTypes...)>::type`.|

İlk şablon işlevi `async(launch::any, fn, args...)`döndürür.

İkinci işlev, `future<Ty>` ilişkili *asenkron durumu* *dfn* ve *dargs* değerleri ile birlikte bir sonuç tutan bir nesne ve yürütme ayrı bir iş parçacığı yönetmek için bir iş parçacığı nesnesi döndürür.

Başlatma `decay<Fn>::type` dışında bir tür olmadığı sürece, ikinci işlev aşırı yük çözünürlüğüne katılmaz.

C++ standardı, ilke başlatılırsa::async, işlevin yeni bir iş parçacığı oluşturduğunu belirtir. Ancak Microsoft uygulaması şu anda uygun değildir. İş parçacıklarını, bazı durumlarda yeni bir iş yerine geri dönüştürülmüş bir iş parçacığı sağlayabilecek olan Windows ThreadPool'dan edinir. Bu, ilkenin `launch::async` aslında `launch::async|launch::deferred`.  ThreadPool tabanlı uygulamanın bir diğer sonucu da iş parçacığı tamamlandığında iş parçacığı yerel değişkenlerinin yok olacağının garantisi olmamasıdır. İş parçacığı geri dönüştürülür ve yeni `async`bir çağrı sağlanırsa, eski değişkenler hala var olacaktır. Bu nedenle iş parçacığı yerel değişkenleri kullanmamanızı `async`öneririz.

*İlke* `launch::deferred`ise, işlev ertelenmiş bir işlev tutarak ilişkili asynchronous durumunu işaretler ve *döndürür.* İlişkili asenkron durumunun etkin olarak hazır olmasını bekleyen zamansız işlevlere yapılan ilk çağrı, ertelenmiş `INVOKE(dfn, dargs..., Ty)`işlevi değerlendirerek çağırır.

Her durumda, nesnenin `future` ilişkili eşzamanlı durumu, bir özel durum atılarak veya normal olarak döndürülerek, değerlendirme `INVOKE(dfn, dargs..., Ty)` tamamlanana kadar *hazır* olarak ayarlanmaz. İlişkili eşzamanlı durum sonucu bir atıldığında veya değerlendirme tarafından döndürülen herhangi bir değer bir özel durumdur.

> [!NOTE]
> Bir `future`—veya son [shared_future](../standard-library/shared-future-class.md)için (bu, görev tamamlanmadıysa yıkıcı bloklar) ile `std::async`başlatılan bir göreve eklenir; diğer bir şey, bu iş parçacığı `.get()` `.wait()` henüz aramadı veya görev hala çalışıyorsa engeller. Elde `future` edilen `std::async` bir yerel kapsam dışına taşınırsa, onu kullanan diğer kod, yıkıcının paylaşılan durumun hazır olması için engelolabileceğini bilmelidir.

Sözde fonksiyon `INVOKE` [ \<fonksiyonel>](../standard-library/functional.md)tanımlanır.

## <a name="future_category"></a><a name="future_category"></a>future_category

Nesnelerle `future` ilişkili hataları karakterize eden [error_category](../standard-library/error-category-class.md) nesneye bir başvuru verir.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a><a name="make_error_code"></a>make_error_code

[Gelecekteki](../standard-library/future-class.md) hataları karakterize eden [error_category](../standard-library/error-category-class.md) nesneyle birlikte bir [error_code](../standard-library/error-code-class.md) oluşturur.

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*Errno*\
Bildirilen hatayı tanımlayan [future_errc](../standard-library/future-enums.md#future_errc) değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a><a name="make_error_condition"></a>make_error_condition

[Gelecekteki](../standard-library/future-class.md) hataları karakterize eden [error_category](../standard-library/error-category-class.md) nesnesi ile birlikte bir [error_condition](../standard-library/error-condition-class.md) oluşturur.

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*Errno*\
Bildirilen hatayı tanımlayan [future_errc](../standard-library/future-enums.md#future_errc) değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a><a name="swap"></a>Takas

Bir `promise` nesnenin *ilişkili eşzamanlı durumunu* diğerininkiyle değiştirir.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `promise` nesne.

*Doğru*\
Doğru `promise` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[\<gelecek>](../standard-library/future.md)
