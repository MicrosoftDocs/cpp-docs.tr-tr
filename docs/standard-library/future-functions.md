---
title: '&lt;Gelecekteki&gt; işlevleri'
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
ms.openlocfilehash: 56ae0da7e86e092cee46d24d1a2a27d9d54709e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159515"
---
# <a name="ltfuturegt-functions"></a>&lt;Gelecekteki&gt; işlevleri

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[değiştirme](#swap)|

## <a name="async"></a>  zaman uyumsuz

Temsil eden bir *zaman uyumsuz sağlayıcıyı*.

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>Parametreler

*İlke*<br/>
A [başlatma](../standard-library/future-enums.md#launch) değeri.

### <a name="remarks"></a>Açıklamalar

Kısaltmalar tanımları:

|||
|-|-|
|*dfn*|Arama sonucu `decay_copy(forward<Fn>(fn))`.|
|*dargs*|Arama sonuçları `decay_copy(forward<ArgsTypes>(args...))`.|
|*Ty*|Türü `result_of<Fn(ArgTypes...)>::type`.|

İlk şablon işlevinin döndürdüğü `async(launch::any, fn, args...)`.

İkinci işlevi döndürür bir `future<Ty>` nesnesi *ilişkili zaman uyumsuz durumu* tutan bir sonuç değerlerini birlikte *dfn* ve *dargs* ve bir iş parçacığı ayrı bir iş parçacığı yürütme yönetmek için nesne.

Sürece `decay<Fn>::type` bir tür başlatma dışında ikinci işlev aşırı yükleme çözünürlüğü içinde yer almaz.

C++ Standart ilkesini launch::async ise işlev yeni bir iş parçacığı oluşturur belirtir. Ancak Microsoft uygulaması şu anda DSCP. Windows, bazı durumlarda yeni bir tane yerine geri dönüştürülmüş iş parçacığı sağlayabilir işten, parçacıklarını alır. Diğer bir deyişle `launch::async` ilke olarak uygulanan gerçekten `launch::async|launch::deferred`.  İş parçacığı havuzu tabanlı bir uygulama, başka bir dolaylı bir garanti yoktur olan iş parçacığı tamamlandığında iş parçacığı yerel değişkenleri yok edilir. İş parçacığına geri dönüştürüldü ve yeni bir çağrı için sağlanan varsa `async`, eski değişkenleri varolmaya devam eder. Bu nedenle, iş parçacığı yerel değişkenleriyle kullanmamanızı öneririz `async`.

Varsa *ilke* olduğu `launch::deferred`, işlevi, ilişkili zaman uyumsuz durumu tutan olarak işaretler. bir *işlevi ertelenmiş* ve döndürür. Geçerli hazır olması ilişkili zaman uyumsuz durumu için bekleyeceği zaman aşımına olmayan işlevi yapılan ilk çağrı değerlendirerek ertelenmiş işlevi çağırır `INVOKE(dfn, dargs..., Ty)`.

Tüm durumlarda, ilişkili zaman uyumsuz durumu `future` nesnesi ayarlanmadı *hazır* değerlendirmesi kadar `INVOKE(dfn, dargs..., Ty)` özel bir durum yaratarak veya normalde döndürerek tamamlar. Bir durum değilse bir özel durum ya da değerlendirmesi tarafından döndürülen herhangi bir değer ilişkili zaman uyumsuz durumu sonucudur.

> [!NOTE]
> İçin bir `future`— veya son [shared_future](../standard-library/shared-future-class.md)— kullanmaya bir göreve ekli `std::async`, yok edici blokları görevi tamamlanmadıysa; bu iş parçacığı henüz arama diğer bir deyişle, bunu engeller `.get()` veya `.wait()` ve görev hala çalışıyor. Varsa bir `future` alınan `std::async` taşınan yerel kapsamı dışında bunu kullanan başka bir kod yok edici paylaşılan durum hazır olmasını engelleyebilir farkında olmalıdır.

Sözde işlevi `INVOKE` tanımlanan [ \<işlevsel >](../standard-library/functional.md).

## <a name="future_category"></a>  future_category

Bir başvuru döndürür [error_category](../standard-library/error-category-class.md) ilişkili hataları nesnesi `future` nesneleri.

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a>  make_error_code

Oluşturur bir [error_code](../standard-library/error-code-class.md) ile birlikte [error_category](../standard-library/error-category-class.md) nesnesi [gelecekteki](../standard-library/future-class.md) hataları.

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*errno*<br/>
A [future_errc](../standard-library/future-enums.md#future_errc) raporlanan hatayı tanımlayan bir değer.

### <a name="return-value"></a>Dönüş Değeri

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a>  make_error_condition

Oluşturur bir [error_condition](../standard-library/error-condition-class.md) ile birlikte [error_category](../standard-library/error-category-class.md) nesnesi [gelecekteki](../standard-library/future-class.md) hataları.

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>Parametreler

*errno*<br/>
A [future_errc](../standard-library/future-enums.md#future_errc) raporlanan hatayı tanımlayan bir değer.

### <a name="return-value"></a>Dönüş Değeri

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>  değiştirme

Değişimleri *ilişkili zaman uyumsuz durumu* birinin `promise` , başka bir nesne.

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol `promise` nesne.

*sağ*<br/>
Sağa `promise` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[\<gelecek >](../standard-library/future.md)<br/>
