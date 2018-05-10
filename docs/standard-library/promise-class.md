---
title: promise sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::promise
- future/std::promise::promise
- future/std::promise::get_future
- future/std::promise::set_exception
- future/std::promise::set_exception_at_thread_exit
- future/std::promise::set_value
- future/std::promise::set_value_at_thread_exit
- future/std::promise::swap
dev_langs:
- C++
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::promise [C++]
- std::promise [C++], promise
- std::promise [C++], get_future
- std::promise [C++], set_exception
- std::promise [C++], set_exception_at_thread_exit
- std::promise [C++], set_value
- std::promise [C++], set_value_at_thread_exit
- std::promise [C++], swap
ms.workload:
- cplusplus
ms.openlocfilehash: ac8508cab7afc7e6614c29b64d78849383f5bc2d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="promise-class"></a>promise Sınıfı

Açıklayan bir *zaman uyumsuz sağlayıcısı*.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Promise](#promise)|Oluşturan bir `promise` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_future](#get_future)|Döndürür bir [gelecekteki](../standard-library/future-class.md) bu promise ile ilişkilendirilmiş.|
|[set_exception](#set_exception)|Otomatik olarak bir özel durum belirtmek için bu promise sonucunu ayarlar.|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|Otomatik olarak bir özel durum belirtmek için bu promise sonuç kümeleri ve tüm iş parçacığı yerel nesneler yalnızca geçerli iş parçacığı içinde (genellikle iş parçacığı Çıkışta) yok edildi bildirim sunar.|
|[set_value](#set_value)|Otomatik olarak bir değer belirtmek için bu promise sonucunu ayarlar.|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|Otomatik olarak bir değer belirtmek için bu promise sonuç kümeleri ve tüm iş parçacığı yerel nesneler yalnızca geçerli iş parçacığı içinde (genellikle iş parçacığı Çıkışta) yok edildi bildirim sunar.|
|[Değiştirme](#swap)|Alışverişleri *zaman uyumsuz durum ilişkili* , bu promise değeriyle belirtilen promise nesnesi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Promise::operator =](#op_eq)|Bu promise nesnesi paylaşılan durumu atama.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`promise`

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecekteki >

**Namespace:** std

## <a name="get_future"></a>  Promise::get_future

Döndürür bir [gelecekteki](../standard-library/future-class.md) aynı olan nesneyi *zaman uyumsuz durum ilişkili* bu promise olarak.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Açıklamalar

Promise nesnesi boş ise, bu yöntem oluşturulur bir [future_error](../standard-library/future-error-class.md) olan bir [error_code](../standard-library/error-code-class.md) , `no_state`.

Bu yöntem için aynı ilişkili zaman uyumsuz durumuna sahip bir promise nesnesi adında, yöntemi döndürürse bir `future_error` olan bir `error_code` , `future_already_retrieved`.

## <a name="op_eq"></a>  Promise::operator =

Aktarımları *zaman uyumsuz durum ilişkili* belirtilen bir gelen `promise` nesnesi.

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

`Other` A `promise` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Bu işleç ilişkili zaman uyumsuz durumundan aktarır `Other`. Aktarım sonra `Other` olan *boş*.

## <a name="promise"></a>  Promise::Promise Oluşturucusu

Oluşturan bir `promise` nesnesi.

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

`Al` Bellek ayırıcısında. Bkz: [ \<allocators >](../standard-library/allocators-header.md) daha fazla bilgi için.

`Other` A `promise` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu yapıları bir *boş* `promise` nesnesi.

Boş bir ikinci oluşturucu oluşturur `promise` nesne ve kullandığı `Al` bellek ayırma için.

Üçüncü Oluşturucusu yapıları bir `promise` nesne ve ilişkili zaman uyumsuz durumundan aktarımı `Other`ve bırakır `Other` boş.

## <a name="set_exception"></a>  Promise::set_exception

Otomatik olarak bir özel durum Bunun sonucu olarak depolar `promise` nesne ve ayarlar *zaman uyumsuz durum ilişkili* için *hazır*.

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>Parametreler

`Exc` Bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) depolanan bu yöntem tarafından özel durum sonucu olarak.

### <a name="remarks"></a>Açıklamalar

Varsa `promise` nesnesi ilişkili hiçbir zaman uyumsuz durumuna sahiptir, bu yöntem oluşturulur bir [future_error](../standard-library/future-error-class.md) hata kodunu olan `no_state`.

Varsa `set_exception`, [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value), veya [set_value_at_thread_exit](#set_value_at_thread_exit) için zaten çağrılmış bir `promise` nesnesinin sahip aynı zaman uyumsuz durum ilişkilendirilmiş, bu yöntem oluşturulur bir `future_error` hata kodunu olan `promise_already_satisfied`.

Bu yöntem sonucunda ilişkili zaman uyumsuz durumunu engellenmiş iş parçacığı sayısı engeli haline gelir.

## <a name="set_exception_at_thread_exit"></a>  Promise::set_exception_at_thread_exit

Bunun sonucunda, otomatik olarak ayarlar `promise` bir özel durum belirtmek için bildirim yalnızca tüm iş parçacığı yerel nesneleri geçerli iş parçacığında teslim edildi (genellikle iş parçacığı Çıkışta).

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>Parametreler

`Exc` Bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) depolanan bu yöntem tarafından özel durum sonucu olarak.

### <a name="remarks"></a>Açıklamalar

Promise nesnesi yok varsa *zaman uyumsuz durum ilişkili*, bu yöntem oluşturulur bir [future_error](../standard-library/future-error-class.md) hata kodunu olan `no_state`.

Varsa [set_exception](#set_exception), `set_exception_at_thread_exit`, [set_value](#set_value), veya [set_value_at_thread_exit](#set_value_at_thread_exit) için zaten çağrılmış bir `promise` aynı olan nesneyi ilişkili zaman uyumsuz durum, bu yöntem oluşturur bir `future_error` hata kodunu olan `promise_already_satisfied`.

Tersine için [set_exception](#set_exception), bu yöntem, geçerli iş parçacığının tüm iş parçacığı yerel nesneleri yok kadar hazır ilişkili zaman uyumsuz durum ayarlı değil. Genellikle, geçerli iş parçacığının çıkar kadar ilişkili zaman uyumsuz durumunu engellenmiş iş parçacıklarının engeli değildir.

## <a name="set_value"></a>  Promise::set_value

Otomatik olarak bir değer Bunun sonucu olarak depolar `promise` nesne ve ayarlar *zaman uyumsuz durum ilişkili* için *hazır*.

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>Parametreler

`Val` Sonuç olarak depolanması için değer.

### <a name="remarks"></a>Açıklamalar

Varsa `promise` nesnesi ilişkili hiçbir zaman uyumsuz durumuna sahiptir, bu yöntem oluşturulur bir [future_error](../standard-library/future-error-class.md) hata kodunu olan `no_state`.

Varsa [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), `set_value`, veya [set_value_at_thread_exit](#set_value_at_thread_exit) için zaten çağrılmış bir `promise` nesnesi aynı ilişkili zaman uyumsuz duruma sahip, bu yöntem oluşturulur bir `future_error` hata kodunu olan `promise_already_satisfied`.

Bu yöntem sonucunda ilişkili zaman uyumsuz durumunu engellenmiş iş parçacığı sayısı engeli haline gelir.

İlk yöntem de ne zaman oluşturulur herhangi bir durum oluşturduğunda `Val` ilişkili zaman uyumsuz bir duruma kopyalanır. Bu durumda, ilişkili zaman uyumsuz durumu ayarlanmamış için hazır.

İkinci yöntem de ne zaman oluşturulur herhangi bir durum oluşturduğunda `Val` ilişkili zaman uyumsuz duruma taşındığında. Bu durumda, ilişkili zaman uyumsuz durumu ayarlanmamış için hazır.

Kısmi uzmanlığı için `promise<Ty&>`, depolanmış geçerli bir başvuru değerdir `Val`.

Özelleştirme için `promise<void>`, depolanan bir değeri yok.

## <a name="set_value_at_thread_exit"></a>  Promise::set_value_at_thread_exit

Otomatik olarak bir değer Bunun sonucu olarak depolar `promise` nesnesi.

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>Parametreler

`Val` Sonuç olarak depolanması için değer.

### <a name="remarks"></a>Açıklamalar

Promise nesnesi yok varsa *zaman uyumsuz durum ilişkili*, bu yöntem oluşturulur bir [future_error](../standard-library/future-error-class.md) hata kodunu olan `no_state`.

Varsa [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value), veya `set_value_at_thread_exit` için zaten çağrılmış bir `promise` aynı olan nesneyi ilişkili zaman uyumsuz durum, bu yöntem oluşturur bir `future_error` hata kodunu olan `promise_already_satisfied`.

Tersine için `set_value`, ilişkili zaman uyumsuz durum geçerli iş parçacığının tüm iş parçacığı yerel nesneleri yok kadar hazır ayarlı değil. Genellikle, geçerli iş parçacığının çıkar kadar ilişkili zaman uyumsuz durumunu engellenmiş iş parçacıklarının engeli değildir.

İlk yöntem de ne zaman oluşturulur herhangi bir durum oluşturduğunda `Val` ilişkili zaman uyumsuz bir duruma kopyalanır.

İkinci yöntem de ne zaman oluşturulur herhangi bir durum oluşturduğunda `Val` ilişkili zaman uyumsuz duruma taşındığında.

Kısmi uzmanlığı için `promise<Ty&>`, depolanan değerin etkili bir şekilde başvurusudur `Val`.

Özelleştirme için `promise<void>`, depolanan bir değeri yok.

## <a name="swap"></a>  Promise::Swap

Alışverişleri *zaman uyumsuz durum ilişkili* , belirtilen bir nesne ile bu promise nesnesi.

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

`Other` A `promise` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
