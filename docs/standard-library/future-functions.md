---
title: '&lt;gelecekteki&gt; işlevler'
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
ms.openlocfilehash: 5435c3b9e10f151fc77c72b58c93510b6a867ce1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447323"
---
# <a name="ltfuturegt-functions"></a>&lt;gelecekteki&gt; işlevler

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[Kur](#swap)|

## <a name="async"></a>eş

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

|||
|-|-|
|*DFN*|Çağırmanın `decay_copy(forward<Fn>(fn))`sonucu.|
|*darg 'ler*|Çağrıların `decay_copy(forward<ArgsTypes>(args...))`sonuçları.|
|*Kalite*|Türü `result_of<Fn(ArgTypes...)>::type`.|

İlk şablon işlevi döndürülür `async(launch::any, fn, args...)`.

İkinci işlev, bir yürütmenin `future<Ty>` ayrı bir iş parçacığını yönetmek için, *ilişkili zaman uyumsuz durumu* , *DFN* ve *darg* değerleri ve bir iş parçacığı nesnesi ile birlikte bir sonuç tutan bir nesne döndürür.

Başlatma haricinde bir tür değilse,ikinciişlevaşırıyüklemeçözümünekatılmaz.`decay<Fn>::type`

Standart C++ , ilke başlatma:: Async olduğunda, işlev yeni bir iş parçacığı oluşturur. Ancak Microsoft Uygulama Şu anda uyumsuz. Bu işlem, bazı durumlarda yeni bir tane yerine geri dönüşümlü bir iş parçacığı sağlayabileceği Windows iş parçacığı ' ndan iş parçacıklarını edinir. Bu, `launch::async` ilkenin gerçekten olarak `launch::async|launch::deferred`uygulandığı anlamına gelir.  İş parçacığı temelli uygulamanın diğer bir uygulaması, iş parçacığı tamamlandığında iş parçacığı yerel değişkenlerinin yok edileceği garantisi değildir. İş parçacığı geri dönüştürülüp yeni bir çağrısına `async`sağlanmışsa, eski değişkenler yine de mevcut olacaktır. Bu nedenle, ile `async`iş parçacığı yerel değişkenleri kullanmanıza tavsiye ederiz.

*İlke* ise `launch::deferred`, işlev, *Ertelenen işlevi* tutarak ilişkili zaman uyumsuz durumunu işaretler ve döndürür. Zaman uyumsuz bir işlevin, ilişkili zaman uyumsuz durumunun etkin olmasını bekleyen ilk çağrısı, değerlendirerek `INVOKE(dfn, dargs..., Ty)`ertelenmiş işlevi çağırır.

Her durumda, `future` nesnenin ilişkili zaman uyumsuz durumu `INVOKE(dfn, dargs..., Ty)` tamamlanana kadar, bir özel durum oluşturarak ya da normal şekilde dönerek, tamamlanana kadar *başlamaya* ayarlanır. İlişkili zaman uyumsuz durumun sonucu, oluşturulursa bir özel durumdur veya değerlendirme tarafından döndürülen herhangi bir değerdir.

> [!NOTE]
> İle `future` `.get()` `.wait()` [](../standard-library/shared-future-class.md)başlatılan bir göreve eklenen bir for veya Last shared_future —, görev tamamlanmadıysa yıkıcı engeller; diğer bir deyişle, bu iş parçacığı henüz çağırmadıysa veya görev `std::async` çalışmaya devam ediyor. `future` Kaynağından`std::async` alınan bir, yerel kapsam dışına taşınırsa, bu dosyayı kullanan diğer kod, yıkıcının paylaşılan durumun hazırlanabileceği şekilde engelleyemeyeceği farkında olmalıdır.

Sözde işlev `INVOKE` , [ \<işlevsel >](../standard-library/functional.md)tanımlanmıştır.

## <a name="future_category"></a>future_category

Nesneler ile `future` ilişkili hataları karakterlendirir [error_category](../standard-library/error-category-class.md) nesnesine bir başvuru döndürür.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a>make_error_code

[Gelecekteki](../standard-library/future-class.md) hataları karakterleştiren [error_category](../standard-library/error-category-class.md) nesnesiyle birlikte bir [error_code](../standard-library/error-code-class.md) oluşturur.

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*Errno*\
Bildirilen hatayı tanımlayan bir [future_errc](../standard-library/future-enums.md#future_errc) değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a>make_error_condition

[Gelecekteki](../standard-library/future-class.md) hataları karakterleştiren [error_category](../standard-library/error-category-class.md) nesnesiyle birlikte bir [error_condition](../standard-library/error-condition-class.md) oluşturur.

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*Errno*\
Bildirilen hatayı tanımlayan bir [future_errc](../standard-library/future-enums.md#future_errc) değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>Kur

Bir `promise` nesnenin *ilişkili zaman uyumsuz durumunu* başka bir nesneyle değiş tokuş eder.

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

[\<gelecekte >](../standard-library/future.md)
