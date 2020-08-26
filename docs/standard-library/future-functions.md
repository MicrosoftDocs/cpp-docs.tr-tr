---
title: '&lt;gelecekteki &gt; işlevler'
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
ms.openlocfilehash: d419984243d3970533f30814fe0ff451199afb34
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837976"
---
# <a name="ltfuturegt-functions"></a>&lt;gelecekteki &gt; işlevler

[eş](#async)\
[future_category](#future_category)\
[make_error_code](#make_error_code)\
[make_error_condition](#make_error_condition)\
[Kur](#swap)|

## <a name="async"></a><a name="async"></a> eş

*Zaman uyumsuz sağlayıcıyı*temsil eder.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Bir [başlatma](../standard-library/future-enums.md#launch) değeri.

### <a name="remarks"></a>Açıklamalar

Kısaltmaların tanımları:

|Kısaltma|Açıklama|
|-|-|
|*DFN*|Çağırmanın sonucu `decay_copy(forward<Fn>(fn))` .|
|*darg 'ler*|Çağrıların sonuçları `decay_copy(forward<ArgsTypes>(args...))` .|
|*Kalite*|Türü `result_of<Fn(ArgTypes...)>::type` .|

İlk şablon işlevi döndürülür `async(launch::any, fn, args...)` .

İkinci işlev, bir `future<Ty>` yürütmenin ayrı bir iş parçacığını yönetmek için, *ilişkili zaman uyumsuz durumu* , *DFN* ve *darg* değerleri ve bir iş parçacığı nesnesi ile birlikte bir sonuç tutan bir nesne döndürür.

`decay<Fn>::type`Başlatma haricinde bir tür değilse, ikinci işlev aşırı yükleme çözümüne katılmaz.

C++ standardı, ilke başlatma:: Async olduğunda, işlevin yeni bir iş parçacığı oluşturduğunu belirtir. Ancak Microsoft Uygulama Şu anda uyumsuz. Bu işlem, bazı durumlarda yeni bir tane yerine geri dönüşümlü bir iş parçacığı sağlayabileceği Windows iş parçacığı ' ndan iş parçacıklarını edinir. Bu, `launch::async` ilkenin gerçekten olarak uygulandığı anlamına gelir `launch::async|launch::deferred` .  İş parçacığı temelli uygulamanın diğer bir uygulaması, iş parçacığı tamamlandığında iş parçacığı yerel değişkenlerinin yok edileceği garantisi değildir. İş parçacığı geri dönüştürülüp yeni bir çağrısına sağlanmışsa `async` , eski değişkenler yine de mevcut olacaktır. Bu nedenle, ile iş parçacığı yerel değişkenleri kullanmanıza tavsiye ederiz `async` .

*İlke* ise `launch::deferred` , işlev, *Ertelenen işlevi* tutarak ilişkili zaman uyumsuz durumunu işaretler ve döndürür. Zaman uyumsuz bir işlevin, ilişkili zaman uyumsuz durumunun etkin olmasını bekleyen ilk çağrısı, değerlendirerek ertelenmiş işlevi çağırır `INVOKE(dfn, dargs..., Ty)` .

Her durumda, nesnenin ilişkili zaman uyumsuz durumu `future` tamamlanana kadar *ready* `INVOKE(dfn, dargs..., Ty)` , bir özel durum oluşturarak ya da normal şekilde dönerek, tamamlanana kadar başlamaya ayarlanır. İlişkili zaman uyumsuz durumun sonucu, oluşturulursa bir özel durumdur veya değerlendirme tarafından döndürülen herhangi bir değerdir.

> [!NOTE]
> Bir `future` veya ile başlatılan bir göreve eklenen son [shared_future](../standard-library/shared-future-class.md)için `std::async` , yok edicisi, görev tamamlanmazsa engeller; diğer bir deyişle, bu iş parçacığı henüz çağırmadıysa `.get()` veya `.wait()` görev hala çalışıyorsa engeller. `future`Kaynağından alınan bir, `std::async` yerel kapsam dışına taşınırsa, bu dosyayı kullanan diğer kod, yıkıcının paylaşılan durumun hazırlanabileceği şekilde engelleyemeyeceği farkında olmalıdır.

Sözde işlev `INVOKE` ' de tanımlanmıştır [\<functional>](../standard-library/functional.md) .

## <a name="future_category"></a><a name="future_category"></a> future_category

Nesneler ile ilişkili hataları karakterlendirir [error_category](../standard-library/error-category-class.md) nesnesine bir başvuru döndürür `future` .

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a><a name="make_error_code"></a> make_error_code

[Gelecekte](../standard-library/future-class.md) hatalara sahip [error_category](../standard-library/error-category-class.md) nesnesiyle birlikte bir [error_code](../standard-library/error-code-class.md) oluşturur.

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*Errno*\
Bildirilen hatayı tanımlayan bir [future_errc](../standard-library/future-enums.md#future_errc) değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a><a name="make_error_condition"></a> make_error_condition

[Gelecekte](../standard-library/future-class.md) hatalara sahip [error_category](../standard-library/error-category-class.md) nesnesiyle birlikte bir [error_condition](../standard-library/error-condition-class.md) oluşturur.

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*Errno*\
Bildirilen hatayı tanımlayan bir [future_errc](../standard-library/future-enums.md#future_errc) değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a><a name="swap"></a> Kur

Bir nesnenin *ilişkili zaman uyumsuz durumunu* `promise` başka bir nesneyle değiş tokuş eder.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Tarafta*\
Sol `promise` nesne.

*Right*\
Doğru `promise` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[\<future>](../standard-library/future.md)
