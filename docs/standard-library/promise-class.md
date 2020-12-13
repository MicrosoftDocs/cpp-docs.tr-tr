---
description: 'Daha fazla bilgi edinin: Promise sınıfı'
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
ms.openlocfilehash: bf65a3d1f42cb331c2e87ab418f2917947b0bed7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340638"
---
# <a name="promise-class"></a>promise Sınıfı

*Zaman uyumsuz sağlayıcıyı* açıklar.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[ünü](#promise)|Bir `promise` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_future](#get_future)|Bu Promise ile ilişkili bir [gelecek](../standard-library/future-class.md) döndürür.|
|[set_exception](#set_exception)|Bu Promise 'in sonucunu bir özel durum belirtecek şekilde otomatik olarak ayarlar.|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|Bu Promise 'in sonucunu bir özel durum belirtecek şekilde ayarlar ve yalnızca geçerli iş parçacığındaki tüm iş parçacığı-yerel nesneleri yok edildikten sonra (genellikle iş parçacığı çıkışında) bildirimi teslim eder.|
|[set_value](#set_value)|Bu Promise 'in sonucunu bir değer belirtmek için atomictik olarak ayarlar.|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|Bu Promise 'in sonucunu bir değer belirtecek şekilde belirler ve yalnızca geçerli iş parçacığındaki tüm iş parçacığı-yerel nesneleri yok edildikten sonra (genellikle iş parçacığı çıkışında) bildirimi teslim eder.|
|[Kur](#swap)|Bu taahhüdün *ilişkili zaman uyumsuz durumunu* belirtilen bir Promise nesnesinin ile değiş tokuş eder.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Promise:: operator =](#op_eq)|Bu Promise nesnesinin paylaşılan durumunun atanması.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

*ünü*

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<future>

**Ad alanı:** std

## <a name="promiseget_future"></a><a name="get_future"></a> Promise:: get_future

Bu Promise ile aynı *ilişkili zaman uyumsuz duruma* sahip [gelecek](../standard-library/future-class.md) bir nesne döndürür.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Açıklamalar

Promise nesnesi boşsa, bu yöntem, [error_code](../standard-library/error-code-class.md) olan bir [future_error](../standard-library/future-error-class.md) oluşturur `no_state` .

Bu yöntem, aynı ilişkili zaman uyumsuz duruma sahip bir promise nesnesi için zaten çağrılırsa, yöntemi öğesine sahip bir oluşturur `future_error` `error_code` `future_already_retrieved` .

## <a name="promiseoperator"></a><a name="op_eq"></a> Promise:: operator =

*İlişkili zaman uyumsuz durumu* belirtilen bir nesneden aktarır `promise` .

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bir `promise` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Bu işleç, ilişkili zaman uyumsuz durumu *diğer* öğesinden aktarır. Aktarımdan sonra *diğeri* *boş* olur.

## <a name="promisepromise-constructor"></a><a name="promise"></a> Promise::p Rolen Oluşturucusu

Bir `promise` nesnesi oluşturur.

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Eşkenar*\
Bir bellek ayırıcısı. [\<allocators>](../standard-library/allocators-header.md)Daha fazla bilgi için bkz..

*Farklı*\
Bir `promise` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu *boş* bir `promise` nesne oluşturur.

İkinci Oluşturucu boş bir nesne oluşturur `promise` ve bellek ayırma Için *Al* kullanır.

Üçüncü Oluşturucu bir nesne oluşturur `promise` ve ilişkili zaman uyumsuz durumu *diğer* boş bırakır. 

## <a name="promiseset_exception"></a><a name="set_exception"></a> Promise:: set_exception

Bu nesnenin sonucu olarak bir özel durum `promise` oluşturur ve *ilişkili zaman uyumsuz durumu* *Ready* olarak ayarlar.

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>Parametreler

*Hariç tutulan*\
Bu yöntem tarafından özel durum sonucu olarak depolanan bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) .

### <a name="remarks"></a>Açıklamalar

`promise`Nesnenin ilişkili zaman uyumsuz durumu yoksa, bu yöntem hata kodu olan bir [future_error](../standard-library/future-error-class.md) oluşturur `no_state` .

`set_exception`Aynı ilişkili zaman uyumsuz duruma sahip bir nesne için [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_Value](#set_value)veya [set_value_at_thread_exit](#set_value_at_thread_exit) zaten çağrılırsa `promise` , bu yöntem `future_error` hata koduna sahip bir oluşturur `promise_already_satisfied` .

Bu yöntemin sonucu olarak, ilişkili zaman uyumsuz durumda engellenen tüm iş parçacıkları engellenmemiş hale gelir.

## <a name="promiseset_exception_at_thread_exit"></a><a name="set_exception_at_thread_exit"></a> Promise:: set_exception_at_thread_exit

Bu durumun sonucunu, `promise` yalnızca geçerli iş parçacığındaki tüm iş parçacığı-yerel nesneleri yok edildikten sonra (genellikle iş parçacığı çıkışında) bildirimi teslim eden bir özel durum belirtecek şekilde ayarlar.

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>Parametreler

*Hariç tutulan*\
Bu yöntem tarafından özel durum sonucu olarak depolanan bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) .

### <a name="remarks"></a>Açıklamalar

Promise nesnesinin *ilişkili bir zaman uyumsuz durumu* yoksa, bu yöntem hata kodu olan bir [future_error](../standard-library/future-error-class.md) oluşturur `no_state` .

[](#set_exception) `set_exception_at_thread_exit` Aynı ilişkili zaman uyumsuz duruma sahip bir nesne için set_exception,, [set_Value](#set_value)veya [set_value_at_thread_exit](#set_value_at_thread_exit) zaten çağrılırsa `promise` , bu yöntem `future_error` hata koduna sahip bir oluşturur `promise_already_satisfied` .

[Set_exception](#set_exception)aksine, bu yöntem ilgili zaman uyumsuz durumu geçerli iş parçacığındaki tüm iş parçacığı yerel nesneleri yok edilene kadar başlamaya ayarlı olarak yapmaz. Genellikle, ilişkili zaman uyumsuz durumda engellenen iş parçacıkları geçerli iş parçacığına çıkana kadar engellenmemiş.

## <a name="promiseset_value"></a><a name="set_value"></a> Promise:: set_value

Bu nesnenin sonucu olarak bir değeri otomatik olarak depolar `promise` ve *ilişkili zaman uyumsuz durumu* *Ready* olarak ayarlar.

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>Parametreler

*Acil*\
Sonuç olarak depolanacak değer.

### <a name="remarks"></a>Açıklamalar

`promise`Nesnenin ilişkili zaman uyumsuz durumu yoksa, bu yöntem hata kodu olan bir [future_error](../standard-library/future-error-class.md) oluşturur `no_state` .

Aynı [](#set_exception) [](#set_exception_at_thread_exit) `set_value` ilişkili zaman uyumsuz duruma sahip bir nesne için set_exception, set_exception_at_thread_exit, veya [set_value_at_thread_exit](#set_value_at_thread_exit) zaten çağrılırsa `promise` , bu yöntem `future_error` hata koduna sahip bir oluşturur `promise_already_satisfied` .

Bu yöntemin sonucu olarak, ilişkili zaman uyumsuz durumda engellenen tüm iş parçacıkları engellenmemiş hale gelir.

İlk yöntem aynı zamanda *Val* ilişkili zaman uyumsuz duruma kopyalanırken oluşturulan özel durumları da oluşturur. Bu durumda, ilişkili zaman uyumsuz durum, Ready olarak ayarlanmadı.

İkinci yöntem, *Val* ilişkili zaman uyumsuz duruma taşındığında oluşturulan özel durumları da oluşturur. Bu durumda, ilişkili zaman uyumsuz durum, Ready olarak ayarlanmadı.

Kısmi özelleşme için `promise<Ty&>` , saklı değer *Val*'e bir başvuru olarak etkindir.

Özelleştirme için `promise<void>` , depolanan değer yok.

## <a name="promiseset_value_at_thread_exit"></a><a name="set_value_at_thread_exit"></a> Promise:: set_value_at_thread_exit

Bu nesnenin sonucu olarak bir değeri atomicas olarak depolar `promise` .

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>Parametreler

*Acil*\
Sonuç olarak depolanacak değer.

### <a name="remarks"></a>Açıklamalar

Promise nesnesinin *ilişkili bir zaman uyumsuz durumu* yoksa, bu yöntem hata kodu olan bir [future_error](../standard-library/future-error-class.md) oluşturur `no_state` .

Aynı ilişkili zaman uyumsuz duruma sahip bir nesne için [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_Value](#set_value)veya `set_value_at_thread_exit` zaten çağrılırsa `promise` , bu yöntem `future_error` hata koduna sahip bir oluşturur `promise_already_satisfied` .

Aksine `set_value` , ilişkili zaman uyumsuz durum, geçerli iş parçacığındaki tüm iş parçacığı yerel nesneleri yok edilene kadar Ready olarak ayarlanmadı. Genellikle, ilişkili zaman uyumsuz durumda engellenen iş parçacıkları geçerli iş parçacığına çıkana kadar engellenmemiş.

İlk yöntem aynı zamanda *Val* ilişkili zaman uyumsuz duruma kopyalanırken oluşturulan özel durumları da oluşturur.

İkinci yöntem, *Val* ilişkili zaman uyumsuz duruma taşındığında oluşturulan özel durumları da oluşturur.

Kısmi özelleşme için `promise<Ty&>` , saklı değer bir *Val*'e göre etkili bir başvurudur.

Özelleştirme için `promise<void>` , depolanan değer yok.

## <a name="promiseswap"></a><a name="swap"></a> Promise:: swap

Bu Promise nesnesinin *ilişkili zaman uyumsuz durumunu* belirtilen bir nesne ile değiş tokuş eder.

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bir `promise` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
