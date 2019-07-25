---
title: thread Sınıfı
ms.date: 11/04/2016
f1_keywords:
- thread/std::thread
- thread/std::thread::id Class
- thread/std::thread::thread
- thread/std::thread::detach
- thread/std::thread::get_id
- thread/std::thread::hardware_concurrency
- thread/std::thread::join
- thread/std::thread::joinable
- thread/std::thread::native_handle
- thread/std::thread::swap
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
helpviewer_keywords:
- std::thread [C++]
- std::thread [C++], thread
- std::thread [C++], detach
- std::thread [C++], get_id
- std::thread [C++], hardware_concurrency
- std::thread [C++], join
- std::thread [C++], joinable
- std::thread [C++], native_handle
- std::thread [C++], swap
ms.openlocfilehash: f663034cdc7985dd440a1cdfdd659358c4e250f4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458581"
---
# <a name="thread-class"></a>thread Sınıfı

Bir uygulama içinde yürütmenin iş parçacığını gözlemlemek ve yönetmek için kullanılan bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class thread;
```

## <a name="remarks"></a>Açıklamalar

Bir uygulama içinde yürütmenin iş parçacığını gözlemlemek ve yönetmek için bir **iş parçacığı** nesnesi kullanabilirsiniz. Varsayılan Oluşturucu kullanılarak oluşturulan bir iş parçacığı nesnesi, herhangi bir yürütme iş parçacığı ile ilişkili değildir. Çağrılabilir bir nesne kullanılarak oluşturulan bir iş parçacığı nesnesi, yürütmenin yeni bir iş parçacığını oluşturur ve bu iş parçacığında çağrılabilir nesneyi çağırır. İş parçacığı nesneleri taşınabilir, ancak kopyalanamayabilir. Bu nedenle, bir yürütme iş parçacığı yalnızca bir iş parçacığı nesnesiyle ilişkilendirilebilir.

Yürütmenin her iş parçacığı türünde `thread::id`benzersiz bir tanımlayıcıya sahiptir. İşlev `this_thread::get_id` , çağıran iş parçacığının tanımlayıcısını döndürür. Üye işlevi `thread::get_id` , bir iş parçacığı nesnesi tarafından yönetilen iş parçacığının tanımlayıcısını döndürür. Varsayılan olarak oluşturulmuş bir iş parçacığı nesnesi için, `thread::get_id` yöntemi, varsayılan olarak oluşturulmuş tüm iş parçacığı nesneleri için aynı değere sahip bir nesne döndürür ve bir yürütme iş parçacığı için tarafından `this_thread::get_id` döndürülen değerden farklı olabilir çağrı sırasında birleştirilir.

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Ortak sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[Thread:: ID sınıfı](#id_class)|İlişkili iş parçacığını benzersiz şekilde tanımlar.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[thread](#thread)|Bir **iş parçacığı** nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ayırmak](#detach)|**İş** parçacığı nesnesinden ilişkili iş parçacığını ayırır.|
|[get_id](#get_id)|İlişkili iş parçacığının benzersiz tanımlayıcısını döndürür.|
|[hardware_concurrency](#hardware_concurrency)|Se. Donanım iş parçacığı bağlamlarının sayısının tahminini döndürür.|
|[ayrılma](#join)|İlişkili iş parçacığı tamamlanana kadar engeller.|
|[joinable](#joinable)|İlişkili iş parçacığının joinable olup olmadığını belirtir.|
|[native_handle](#native_handle)|İş parçacığı tanıtıcısını temsil eden uygulamaya özel türü döndürür.|
|[Kur](#swap)|Nesne durumunu belirtilen bir **iş parçacığı** nesnesiyle değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Thread:: operator =](#op_eq)|Bir iş parçacığını geçerli **iş parçacığı** nesnesiyle ilişkilendirir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iş parçacığı >

**Ad alanı:** std

## <a name="detach"></a>iş parçacığı::d etach

İlişkili iş parçacığını ayırır. İşletim sistemi sonlandırmada iş parçacığı kaynaklarını serbest bırakmaktan sorumlu olur.

```cpp
void detach();
```

### <a name="remarks"></a>Açıklamalar

Bir çağrısından `detach`sonra, sonraki [get_id](#get_id) dönüş [kimliği](#id_class)çağrıları.

Çağıran nesneyle ilişkili iş parçacığı birlikte birleştirmiyorsa, işlev hata kodu `invalid_argument`olan bir [system_error](../standard-library/system-error-class.md) oluşturur.

Çağıran nesneyle ilişkili iş parçacığı geçersizse, işlev hata `system_error` `no_such_process`kodu olan bir oluşturur.

## <a name="get_id"></a>Thread:: get_id

İlişkili iş parçacığı için benzersiz bir tanımlayıcı döndürür.

```cpp
id get_id() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [thread::](#id_class) ilişkili iş parçacığını benzersiz bir şekilde tanımlayan veya `thread::id()` nesneyle ilişkili iş parçacığı olmayan ID nesnesi.

## <a name="hardware_concurrency"></a>Thread:: hardware_concurrency

Donanım iş parçacığı bağlamlarının sayısının tahminini döndüren statik yöntem.

```cpp
static unsigned int hardware_concurrency() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Donanım iş parçacığı bağlamlarının sayısını tahmin edin. Değer hesaplanamıyor veya iyi tanımlanmamışsa, bu yöntem 0 döndürür.

## <a name="id_class"></a>Thread:: ID sınıfı

İşlemdeki her yürütme iş parçacığı için benzersiz bir tanımlayıcı sağlar.

```cpp
class thread::id {
    id() noexcept;
};
```

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, var olan herhangi bir iş parçacığının `thread::id` nesnesine eşit olarak karşılaştırmayan bir nesne oluşturur.

Varsayılan olarak oluşturulmuş `thread::id` tüm nesneler eşit olarak karşılaştırılır.

## <a name="join"></a>Thread:: JOIN

Çağıran nesneyle ilişkili yürütmenin iş parçacığı tamamlanana kadar engeller.

```cpp
void join();
```

### <a name="remarks"></a>Açıklamalar

Çağrı başarılı olursa, çağıran nesne için [get_id](#get_id) için sonraki çağrılar, var olan herhangi bir iş parçacığının ile `thread::id` eşit olarak karşılaştırmayan varsayılan bir [thread:: ID](#id_class) döndürür; çağrı başarılı olmazsa, tarafından `get_id`döndürülendeğerdeğiştirilmez.

## <a name="joinable"></a>Thread:: joinable

İlişkili iş parçacığının *joinable*olup olmadığını belirtir.

```cpp
bool joinable() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

ilişkili iş parçacığı *birleştirilebilir*ise **doğru** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bir iş parçacığı nesnesi  , if ise `get_id() != id()`birleştirilebilir.

## <a name="native_handle"></a>Thread:: native_handle

İş parçacığı tanıtıcısını temsil eden uygulamaya özel türü döndürür. İş parçacığı tanıtıcısı, uygulamaya özgü yollarla kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type`, olarak `HANDLE` `void *`atama yapan bir Win32 olarak tanımlanır.

## <a name="op_eq"></a>Thread:: operator =

Belirtilen nesnenin iş parçacığını geçerli nesneyle ilişkilendirir.

```cpp
thread& operator=(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
**İş parçacığı** nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Çağıran nesne birleştirilebilir ise, yöntemi ayır çağırır.

İlişkilendirme yapıldıktan sonra, `Other` varsayılan olarak oluşturulmuş bir duruma ayarlanır.

## <a name="swap"></a>Thread:: swap

Nesne durumunu belirtilen bir **iş parçacığı** nesnesinin değeriyle değiştirir.

```cpp
void swap(thread& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
**İş parçacığı** nesnesi.

## <a name="thread"></a>Thread:: Thread Oluşturucusu

Bir **iş parçacığı** nesnesi oluşturur.

```cpp
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*VADELİ*\
İş parçacığı tarafından yürütülecek uygulama tanımlı bir işlev.

*A*\
*F*'ye geçirilecek bağımsız değişkenlerin listesi.

*Farklı*\
Var olan bir **iş parçacığı** nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, yürütme iş parçacığı ile ilişkilendirilmemiş bir nesne oluşturur. `get_id` Oluşturulan`thread::id()`nesne için çağrısı tarafından döndürülen değer.

İkinci Oluşturucu, yürütmenin yeni bir iş parçacığıyla ilişkilendirilen bir nesne oluşturur ve `INVOKE` [ \<işlevsel >](../standard-library/functional.md)tanımlanmış sözde işlevi yürütür. Yeni bir iş parçacığı başlatmak için yeterli kaynak yoksa, işlev hata kodu `resource_unavailable_try_again`olan bir [system_error](../standard-library/system-error-class.md) nesnesi oluşturur. *F* çağrısı yakalanamayan bir özel durumla sonlandığında, [Terminate](../standard-library/exception-functions.md#terminate) çağırılır.

Üçüncü Oluşturucu, ile `Other`ilişkili iş parçacığıyla ilişkili bir nesne oluşturur. `Other`sonra varsayılan olarak oluşturulmuş bir duruma ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<iş parçacığı >](../standard-library/thread.md)
