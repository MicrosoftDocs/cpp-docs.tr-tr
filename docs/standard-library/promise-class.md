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
ms.openlocfilehash: a6541fefb2423853f8e59a662e1c8a37777dc14c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323035"
---
# <a name="promise-class"></a>promise Sınıfı

Bir *eşzamanlı sağlayıcı*açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Söz](#promise)|Bir `promise` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[get_future](#get_future)|Bu sözle ilişkili bir [geleceği](../standard-library/future-class.md) döndürür.|
|[set_exception](#set_exception)|Atomik bir özel durum belirtmek için bu sözün sonucunu ayarlar.|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|Atomik olarak bu söz sonucunu bir özel durum belirtmek için ayarlar ve bildirimi yalnızca geçerli iş parçacığındaki tüm iş parçacığı yerel nesneleri yok edildikten sonra (genellikle iş parçacığı çıkışında) teslim eder.|
|[Set_value](#set_value)|Atomik bir değer belirtmek için bu sözün sonucunu ayarlar.|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|Atomik olarak bu sözün sonucunu bir değeri belirtmek için ayarlar ve bildirimi yalnızca geçerli iş parçacığındaki tüm iş parçacığı yerel nesneleri yok edildikten sonra (genellikle iş parçacığı çıkışında) teslim eder.|
|[Takas](#swap)|Bu sözün *ilişkili eşzamanlı durumunu,* belirtilen bir söz nesnesinin ki ile değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[söz::operator=](#op_eq)|Bu söz nesnesinin paylaşılan durumunun atanması.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

*Söz*

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<gelecek>

**Ad alanı:** std

## <a name="promiseget_future"></a><a name="get_future"></a>söz::get_future

Bu sözle ilişkili *asenkron duruma* sahip [gelecekteki](../standard-library/future-class.md) bir nesneyi döndürür.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Açıklamalar

Söz nesnesi boşsa, bu yöntem [error_code](../standard-library/error-code-class.md) olan `no_state`bir [future_error](../standard-library/future-error-class.md) atar.

Bu yöntem zaten aynı ilişkili asenkron durumuna sahip bir söz nesnesi için `future_error` çağrıldıysa, yöntem bir `error_code` `future_already_retrieved`.

## <a name="promiseoperator"></a><a name="op_eq"></a>söz::operator=

*İlişkili asenkron durumu* belirtilen `promise` bir nesneden aktarın.

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*\
Bir `promise` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Bu işleç ilişkili asenkron durumu *Diğer'den*aktarmaktadır. Aktarımdan sonra, *Diğer* *boş .*

## <a name="promisepromise-constructor"></a><a name="promise"></a>söz::promise Constructor

Bir `promise` nesne inşa eder.

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Al*\
Bir bellek ayırıcısı. Daha fazla bilgi için [ \<tahsisatörler>](../standard-library/allocators-header.md) bakın.

*Diğer*\
Bir `promise` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu *boş* `promise` bir nesne inşa eder.

İkinci oluşturucu boş `promise` bir nesne inşa eder ve bellek ayırma için *Al* kullanır.

Üçüncü oluşturucu bir `promise` nesne inşa eder ve ilişkili asenkron durumu *Diğer*'den aktarın ve *Diğer* boş bırakır.

## <a name="promiseset_exception"></a><a name="set_exception"></a>söz::set_exception

Atomik olarak bu `promise` nesnenin sonucu olarak bir özel durum depolar ve ilgili *asynchronous durumunu* *hazır*aayarlar.

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>Parametreler

*Exc*\
Özel durum sonucu olarak bu yöntem tarafından depolanan bir [exception_ptr.](../standard-library/exception-typedefs.md#exception_ptr)

### <a name="remarks"></a>Açıklamalar

Nesne ilişkili asynchronous durumu yoksa, bu yöntem [future_error](../standard-library/future-error-class.md) `no_state`. hata kodu olan bir future_error atar `promise`

`set_exception`, [set_exception_at_thread_exit,](#set_exception_at_thread_exit) [set_value](#set_value)veya [set_value_at_thread_exit](#set_value_at_thread_exit) zaten aynı `promise` ilişkili asenkron durumuna sahip bir nesne için `future_error` çağrıldıysa, bu `promise_already_satisfied`yöntem bir hata kodu atar.

Bu yöntemin bir sonucu olarak, ilişkili asynchronous durumunda engellenen tüm iş parçacıkları engellenmemiş olur.

## <a name="promiseset_exception_at_thread_exit"></a><a name="set_exception_at_thread_exit"></a>söz::set_exception_at_thread_exit

Atomik olarak bunun `promise` sonucunu bir özel durum belirtmek için ayarlar ve bildirimi yalnızca geçerli iş parçacığındaki tüm iş parçacığı yerel nesneleri yok edildikten sonra (genellikle iş parçacığı çıkışında) teslim eder.

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>Parametreler

*Exc*\
Özel durum sonucu olarak bu yöntem tarafından depolanan bir [exception_ptr.](../standard-library/exception-typedefs.md#exception_ptr)

### <a name="remarks"></a>Açıklamalar

Söz nesnesi *ilişkili asynchronous durumu*yoksa, [future_error](../standard-library/future-error-class.md) bu yöntem `no_state`hata kodu olan bir future_error atar.

[set_exception](#set_exception), `set_exception_at_thread_exit`, [set_value](#set_value), veya [set_value_at_thread_exit](#set_value_at_thread_exit) `promise` zaten aynı ilişkili asynchronous durumuna sahip bir `future_error` nesne için çağrıldı, `promise_already_satisfied`bu yöntem bir hata kodu olan atar.

[set_exception](#set_exception)aksine, bu yöntem, geçerli iş parçacığı tüm iş parçacığı yerel nesneler yok edildikten sonra hazır ilişkili asynchronous durumu ayarlamaz. Genellikle, ilişkili asenkron durumda engellenen iş parçacıkları, geçerli iş parçacığı çıkana kadar engellenmez.

## <a name="promiseset_value"></a><a name="set_value"></a>söz::set_value

Atomik olarak bu `promise` nesnenin sonucu olarak bir değer depolar ve ilişkili *asenkron durumu* *hazır*olarak ayarlar.

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>Parametreler

*Val*\
Sonuç olarak depolanacak değer.

### <a name="remarks"></a>Açıklamalar

Nesne ilişkili asynchronous durumu yoksa, bu yöntem [future_error](../standard-library/future-error-class.md) `no_state`. hata kodu olan bir future_error atar `promise`

[set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit)set_exception_at_thread_exit `set_value`, set_value_at_thread_exit veya [set_value_at_thread_exit](#set_value_at_thread_exit) `promise` zaten aynı ilişkili asynchronous durumuna sahip bir `future_error` nesne için çağrıldı, `promise_already_satisfied`bu yöntem bir hata kodu olan atar.

Bu yöntemin bir sonucu olarak, ilişkili asynchronous durumunda engellenen tüm iş parçacıkları engellenmemiş olur.

İlk yöntem, *Val* ilişkili asynchronous durumuna kopyalandığında atılan herhangi bir özel durum da atar. Bu durumda, ilişkili eşzamanlı durum hazır olarak ayarlanmaz.

İkinci yöntem, *Val* ilişkili asynchronous durumuna taşındığında atılan herhangi bir özel durum da atar. Bu durumda, ilişkili eşzamanlı durum hazır olarak ayarlanmaz.

Kısmi uzmanlık `promise<Ty&>`için, depolanan değer aslında *Val*bir referanstır.

Uzmanlık `promise<void>`için, depolanan değer yoktur.

## <a name="promiseset_value_at_thread_exit"></a><a name="set_value_at_thread_exit"></a>söz::set_value_at_thread_exit

Atomik olarak bu `promise` nesnenin sonucu olarak bir değer depolar.

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>Parametreler

*Val*\
Sonuç olarak depolanacak değer.

### <a name="remarks"></a>Açıklamalar

Söz nesnesi *ilişkili asynchronous durumu*yoksa, [future_error](../standard-library/future-error-class.md) bu yöntem `no_state`hata kodu olan bir future_error atar.

[set_exception](#set_exception), [set_exception_at_thread_exit,](#set_exception_at_thread_exit) [set_value,](#set_value)veya `set_value_at_thread_exit` zaten `promise` aynı ilişkili asynchronous durumuna sahip bir nesne `future_error` için çağrıldı, bu `promise_already_satisfied`yöntem bir hata kodu olan atar.

Bunun `set_value`aksine, ilişkili eşzamanlı durum, geçerli iş parçacığındaki tüm iş parçacığı yerel nesneleri yok edilene kadar hazır olarak ayarlanmaz. Genellikle, ilişkili asenkron durumda engellenen iş parçacıkları, geçerli iş parçacığı çıkana kadar engellenmez.

İlk yöntem, *Val* ilişkili asynchronous durumuna kopyalandığında atılan herhangi bir özel durum da atar.

İkinci yöntem, *Val* ilişkili asynchronous durumuna taşındığında atılan herhangi bir özel durum da atar.

Kısmi uzmanlık `promise<Ty&>`için, depolanan değer etkili *Val*bir referanstır.

Uzmanlık `promise<void>`için, depolanan değer yoktur.

## <a name="promiseswap"></a><a name="swap"></a>söz::takas

Bu söz nesnesinin *ilişkili eşzamanlı durumunu,* belirtilen bir nesneninkiyle değiştirir.

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*\
Bir `promise` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)
