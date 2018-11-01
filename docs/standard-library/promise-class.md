---
title: promise Sınıfı
ms.date: 10/18/2018
f1_keywords:
- future/std::promise
- future/std::promise::promise
- future/std::promise::get_future
- future/std::promise::set_exception
- future/std::promise::set_exception_at_thread_exit
- future/std::promise::set_value
- future/std::promise::set_value_at_thread_exit
- future/std::promise::swap
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
helpviewer_keywords:
- std::promise [C++]
- std::promise [C++], promise
- std::promise [C++], get_future
- std::promise [C++], set_exception
- std::promise [C++], set_exception_at_thread_exit
- std::promise [C++], set_value
- std::promise [C++], set_value_at_thread_exit
- std::promise [C++], swap
ms.openlocfilehash: 101c9939f1636d87780aa15aea9459ebb927684d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592578"
---
# <a name="promise-class"></a>promise Sınıfı

Açıklayan bir *zaman uyumsuz sağlayıcıyı*.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Promise](#promise)|Oluşturur bir `promise` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_future](#get_future)|Döndürür bir [gelecekteki](../standard-library/future-class.md) bu taahhüt ile ilişkili.|
|[set_exception](#set_exception)|Bir özel durumu belirtmek için bu Sözün sonucunu atomik olarak belirler.|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|Atomik olarak bir özel durumu belirtmek için bu Sözün sonucunu ayarlar ve (genellikle iş parçacığı çıkışında) yalnızca geçerli iş parçacığındaki tüm iş parçacığı-yerel nesneleri yok olana bildirimi teslim eder.|
|[set_value](#set_value)|Bir değer belirtmek için bu Sözün sonucunu atomik olarak belirler.|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|Atomik olarak bir değer belirtmek için bu Sözün sonucunu ayarlar ve (genellikle iş parçacığı çıkışında) yalnızca geçerli iş parçacığındaki tüm iş parçacığı-yerel nesneleri yok olana bildirimi teslim eder.|
|[değiştirme](#swap)|Değişimleri *ilişkili zaman uyumsuz durumu* , belirtilen bir nesneninkiyle bu Sözün.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Promise::operator =](#op_eq)|Bu söz nesnesinin paylaşılan durumunun ataması.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

*Promise*<br/>

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecek >

**Namespace:** std

## <a name="get_future"></a>  Promise::get_future

Döndürür bir [gelecekteki](../standard-library/future-class.md) aynı nesne *ilişkili zaman uyumsuz durumu* bu taahhüt.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Açıklamalar

Taahhüt nesnesi boşsa, bu yöntemin oluşturduğu bir [future_error](../standard-library/future-error-class.md) olan bir [error_code](../standard-library/error-code-class.md) , `no_state`.

Bu yöntem aynı ilişkili zaman uyumsuz duruma sahip bir promise nesnesi için zaten çağırmışsa çağırılıyorsa yöntem bir `future_error` olan bir `error_code` , `future_already_retrieved`.

## <a name="op_eq"></a>  Promise::operator =

Aktarımları *ilişkili zaman uyumsuz durumu* belirtilen bir `promise` nesne.

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
A `promise` nesne.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Bu işleç, ilişkili zaman uyumsuz durumu aktarır *diğer*. Aktarım sonra *diğer* olduğu *boş*.

## <a name="promise"></a>  Promise::Promise Oluşturucusu

Oluşturur bir `promise` nesne.

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Al*<br/>
Bellek ayırıcı Bkz: [ \<ayırıcılar >](../standard-library/allocators-header.md) daha fazla bilgi için.

*Diğer*<br/>
A `promise` nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu yapıları bir *boş* `promise` nesne.

İkinci oluşturucu boş bir yapıları `promise` nesne ve kullandığı *Al* bellek ayırma için.

Üçüncü Oluşturucu yapıları bir `promise` nesnesini ve ilişkili zaman uyumsuz durumu aktarır *diğer*ve çıktığında *diğer* boş.

## <a name="set_exception"></a>  Promise::set_exception

Bir özel durum bu sonucu atomik olarak depolar `promise` nesne ve ayarlar *ilişkili zaman uyumsuz durumu* için *hazır*.

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>Parametreler

*Hariç tutulan*<br/>
Bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) depolanan bu yöntem tarafından özel durum sonucu olarak.

### <a name="remarks"></a>Açıklamalar

Varsa `promise` nesnesinde ilişkili zaman uyumsuz durumu olmadan, bu yöntem bir [future_error](../standard-library/future-error-class.md) bir hata koduna sahip `no_state`.

Varsa `set_exception`, [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value), veya [set_value_at_thread_exit](#set_value_at_thread_exit) için zaten çağrılmış bir `promise` nesnesinin sahip aynı ilişkili zaman uyumsuz durumu, bu yöntem bir `future_error` bir hata koduna sahip `promise_already_satisfied`.

Bu yöntemin sonucu olarak ilişkili zaman uyumsuz durumda engellenen iş parçacıklarının engeli kaldırılır.

## <a name="set_exception_at_thread_exit"></a>  Promise::set_exception_at_thread_exit

Bu sonucu atomik olarak belirler `promise` bir özel durumu belirtmek için bildirim yalnızca tüm iş parçacığı-yerel nesneleri geçerli iş parçacığında teslim yok edildikten sonra (genellikle iş parçacığı çıkışında).

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>Parametreler

*Hariç tutulan*<br/>
Bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) depolanan bu yöntem tarafından özel durum sonucu olarak.

### <a name="remarks"></a>Açıklamalar

Promise nesnesi Hayır varsa *ilişkili zaman uyumsuz durumu*, bu yöntem bir [future_error](../standard-library/future-error-class.md) bir hata koduna sahip `no_state`.

Varsa [set_exception](#set_exception), `set_exception_at_thread_exit`, [set_value](#set_value), veya [set_value_at_thread_exit](#set_value_at_thread_exit) için zaten çağrılmış bir `promise` aynı nesne ilişkili zaman uyumsuz durum, bu yöntem oluşturur bir `future_error` bir hata koduna sahip `promise_already_satisfied`.

Tersine [set_exception](#set_exception), bu yöntem, geçerli iş parçacığındaki tüm iş parçacığı-yerel nesneleri yok olana kadar hazır olmak için ilişkili zaman uyumsuz durumu ayarlamaz. Genellikle, geçerli iş parçacığı çıkana kadar ilişkili zaman uyumsuz durumda engellenen iş parçacıklarının engeli değildir.

## <a name="set_value"></a>  Promise::set_value

Bir değeri bu sonucu atomik olarak depolar `promise` nesne ve ayarlar *ilişkili zaman uyumsuz durumu* için *hazır*.

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Sonuç olarak depolanacak değer.

### <a name="remarks"></a>Açıklamalar

Varsa `promise` nesnesinde ilişkili zaman uyumsuz durumu olmadan, bu yöntem bir [future_error](../standard-library/future-error-class.md) bir hata koduna sahip `no_state`.

Varsa [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), `set_value`, veya [set_value_at_thread_exit](#set_value_at_thread_exit) için zaten çağrılmış bir `promise` nesnesi aynı ilişkili zaman uyumsuz duruma sahip, bu yöntem bir `future_error` bir hata koduna sahip `promise_already_satisfied`.

Bu yöntemin sonucu olarak ilişkili zaman uyumsuz durumda engellenen iş parçacıklarının engeli kaldırılır.

İlk yöntem ayrıca oluşan herhangi bir özel durum oluşturduğunda *Val* ilgili zaman uyumsuz duruma kopyalanır. Bu durumda, ilişkili zaman uyumsuz durumu ayarlanmamış için hazır.

İkinci yöntem aynı zamanda oluşan herhangi bir özel durumu oluşturur *Val* ilişkili zaman uyumsuz duruma taşındığında. Bu durumda, ilişkili zaman uyumsuz durumu ayarlanmamış için hazır.

Kısmi özelleştirmesi için `promise<Ty&>`, saklanan değer etkili bir başvurudur *Val*.

Özelleştirmesi için `promise<void>`, kayıtlı hiçbir değer yok.

## <a name="set_value_at_thread_exit"></a>  Promise::set_value_at_thread_exit

Bir değeri bu sonucu atomik olarak depolar `promise` nesne.

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Sonuç olarak depolanacak değer.

### <a name="remarks"></a>Açıklamalar

Promise nesnesi Hayır varsa *ilişkili zaman uyumsuz durumu*, bu yöntem bir [future_error](../standard-library/future-error-class.md) bir hata koduna sahip `no_state`.

Varsa [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value), veya `set_value_at_thread_exit` için zaten çağrılmış bir `promise` aynı nesne ilişkili zaman uyumsuz durum, bu yöntem oluşturur bir `future_error` bir hata koduna sahip `promise_already_satisfied`.

Tersine `set_value`, geçerli iş parçacığındaki tüm iş parçacığı-yerel nesneleri yok olana kadar hazır olmak için ilişkili zaman uyumsuz durumu ayarlanmamış. Genellikle, geçerli iş parçacığı çıkana kadar ilişkili zaman uyumsuz durumda engellenen iş parçacıklarının engeli değildir.

İlk yöntem ayrıca oluşan herhangi bir özel durum oluşturduğunda *Val* ilgili zaman uyumsuz duruma kopyalanır.

İkinci yöntem aynı zamanda oluşan herhangi bir özel durumu oluşturur *Val* ilişkili zaman uyumsuz duruma taşındığında.

Kısmi özelleştirmesi için `promise<Ty&>`, saklanan değer etkili bir şekilde bir başvurudur *Val*.

Özelleştirmesi için `promise<void>`, kayıtlı hiçbir değer yok.

## <a name="swap"></a>  Promise::Swap

Değişimleri *ilişkili zaman uyumsuz durumu* ile belirtilen bir nesnenin bu söz nesnesinin.

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
A `promise` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
