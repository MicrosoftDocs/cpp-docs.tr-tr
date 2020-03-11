---
title: gelecekteki&gt; işlevleri &lt;
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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865186"
---
# <a name="ltfuturegt-functions"></a>gelecekteki&gt; işlevleri &lt;

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

*ilke*\
Bir [başlatma](../standard-library/future-enums.md#launch) değeri.

### <a name="remarks"></a>Açıklamalar

Kısaltmaların tanımları:

|||
|-|-|
|*DFN*|`decay_copy(forward<Fn>(fn))`çağırmanın sonucu.|
|*darg 'ler*|Çağrıların sonuçları `decay_copy(forward<ArgsTypes>(args...))`.|
|*Kalite*|Tür `result_of<Fn(ArgTypes...)>::type`.|

İlk şablon işlevi `async(launch::any, fn, args...)`döndürür.

İkinci işlev, bir yürütmenin ayrı bir iş parçacığını yönetmek için, *ilişkili zaman uyumsuz durumu* , *DFN* ve *darg* değerleri ve bir iş parçacığı nesnesi ile birlikte bir sonuç tutan bir `future<Ty>` nesnesi döndürür.

`decay<Fn>::type`, başlatma haricinde bir tür değilse, ikinci işlev aşırı yükleme çözümüne katılmaz.

Standart C++ , ilke başlatma:: Async olduğunda, işlev yeni bir iş parçacığı oluşturur. Ancak Microsoft Uygulama Şu anda uyumsuz. Bu işlem, bazı durumlarda yeni bir tane yerine geri dönüşümlü bir iş parçacığı sağlayabileceği Windows iş parçacığı ' ndan iş parçacıklarını edinir. Bu, `launch::async` ilkesinin aslında `launch::async|launch::deferred`olarak uygulandığı anlamına gelir.  İş parçacığı temelli uygulamanın diğer bir uygulaması, iş parçacığı tamamlandığında iş parçacığı yerel değişkenlerinin yok edileceği garantisi değildir. İş parçacığı geri dönüştürülüp `async`yeni bir çağrıya sağlanmışsa, eski değişkenler yine de mevcut olacaktır. Bu nedenle, `async`ile iş parçacığı yerel değişkenleri kullanmanıza tavsiye ederiz.

*İlke* `launch::deferred`ise, işlevi, *Ertelenen işlevi* tutarak ilişkili zaman uyumsuz durumunu işaretler ve döndürür. Zaman uyumsuz bir işlevin, ilişkili zaman uyumsuz durumunun etkin olması için bekleyeceği ilk çağrı, `INVOKE(dfn, dargs..., Ty)`değerlendirerek ertelenmiş işlevi çağırır.

Her durumda, `future` nesnesinin ilişkili zaman uyumsuz durumu, `INVOKE(dfn, dargs..., Ty)` değerlendirmesi tamamlanana kadar, bir özel durum oluşturarak ya da normal şekilde döndürülünceye kadar, *hazırlık* olarak ayarlanmıştır. İlişkili zaman uyumsuz durumun sonucu, oluşturulursa bir özel durumdur veya değerlendirme tarafından döndürülen herhangi bir değerdir.

> [!NOTE]
> `std::async`ile başlatılan bir göreve eklenen bir `future`veya son [shared_future](../standard-library/shared-future-class.md)için, görev tamamlanmadığından yıkıcı engellenir; diğer bir deyişle, bu iş parçacığı henüz `.get()` veya `.wait()` çağırmadıysa ve görev hala çalışıyorsa engeller. `std::async` alınan bir `future` yerel kapsam dışına taşınırsa, onu kullanan diğer kod, yok edicinin paylaşılan durumun hazırlanabilmesi için engelleyebilen farkında olmalıdır.

Sözde işlev `INVOKE` [\<işlevsel >](../standard-library/functional.md)tanımlanmıştır.

## <a name="future_category"></a>future_category

`future` nesneleriyle ilişkili hataları karakterlendirir [error_category](../standard-library/error-category-class.md) nesnesine bir başvuru döndürür.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a>make_error_code

[Gelecekte](../standard-library/future-class.md) hatalara sahip [error_category](../standard-library/error-category-class.md) nesnesiyle birlikte bir [error_code](../standard-library/error-code-class.md) oluşturur.

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*Errno*\
Bildirilen hatayı tanımlayan bir [future_errc](../standard-library/future-enums.md#future_errc) değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a>make_error_condition

[Gelecekte](../standard-library/future-class.md) hatalara sahip [error_category](../standard-library/error-category-class.md) nesnesiyle birlikte bir [error_condition](../standard-library/error-condition-class.md) oluşturur.

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*Errno*\
Bildirilen hatayı tanımlayan bir [future_errc](../standard-library/future-enums.md#future_errc) değeri.

### <a name="return-value"></a>Dönüş Değeri

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>Kur

Bir `promise` nesnesinin *ilişkili zaman uyumsuz durumunu* başka bir nesneyle değiştirir.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol `promise` nesnesi.

*Sağ*\
Doğru `promise` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[gelecekte \<>](../standard-library/future.md)
