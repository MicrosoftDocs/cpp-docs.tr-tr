---
description: 'Daha fazla bilgi edinin: iş parçacığı sınıfı'
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
ms.openlocfilehash: b9afa8e649fd2b3fb0fdaf339e4a6fbead5b4ef6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207468"
---
# <a name="thread-class"></a>thread Sınıfı

Bir uygulama içinde yürütmenin iş parçacığını gözlemlemek ve yönetmek için kullanılan bir nesneyi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class thread;
```

## <a name="remarks"></a>Açıklamalar

Bir `thread` uygulama içinde yürütmenin iş parçacığını gözlemlemek ve yönetmek için bir nesnesi kullanabilirsiniz. Varsayılan Oluşturucu kullanılarak oluşturulan bir iş parçacığı nesnesi, herhangi bir yürütme iş parçacığı ile ilişkili değildir. Çağrılabilir bir nesne kullanılarak oluşturulan bir iş parçacığı nesnesi, yürütmenin yeni bir iş parçacığını oluşturur ve bu iş parçacığında çağrılabilir nesneyi çağırır. İş parçacığı nesneleri taşınabilir, ancak kopyalanamayabilir. Bu nedenle, bir yürütme iş parçacığı yalnızca bir iş parçacığı nesnesiyle ilişkilendirilebilir.

Yürütmenin her iş parçacığı türünde benzersiz bir tanımlayıcıya sahiptir `thread::id` . İşlev, `this_thread::get_id` çağıran iş parçacığının tanımlayıcısını döndürür. Üye işlevi, `thread::get_id` bir iş parçacığı nesnesi tarafından yönetilen iş parçacığının tanımlayıcısını döndürür. Varsayılan olarak oluşturulmuş bir iş parçacığı nesnesi için, `thread::get_id` yöntemi, varsayılan olarak oluşturulmuş tüm iş parçacığı nesneleri için aynı değere sahip bir nesne döndürür ve `this_thread::get_id` çağrı sırasında birleştirilebilecek herhangi bir yürütme iş parçacığı için tarafından döndürülen değerden farklıdır.

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Ortak sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[Thread:: ID sınıfı](#id_class)|İlişkili iş parçacığını benzersiz şekilde tanımlar.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[thread](#thread)|Bir `thread` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ayırmak](#detach)|İlişkili iş parçacığını `thread` nesneden ayırır.|
|[get_id](#get_id)|İlişkili iş parçacığının benzersiz tanımlayıcısını döndürür.|
|[hardware_concurrency](#hardware_concurrency)|Statik. Donanım iş parçacığı bağlamlarının sayısının tahminini döndürür.|
|[ayrılma](#join)|İlişkili iş parçacığı tamamlanana kadar engeller.|
|[joinable](#joinable)|İlişkili iş parçacığının joinable olup olmadığını belirtir.|
|[native_handle](#native_handle)|İş parçacığı tanıtıcısını temsil eden uygulamaya özel türü döndürür.|
|[Kur](#swap)|Nesne durumunu belirtilen bir `thread` nesneyle değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Thread:: operator =](#op_eq)|Bir iş parçacığını geçerli nesneyle ilişkilendirir `thread` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<thread>

**Ad alanı:** std

## <a name="threaddetach"></a><a name="detach"></a> iş parçacığı::d etach

İlişkili iş parçacığını ayırır. İşletim sistemi sonlandırmada iş parçacığı kaynaklarını serbest bırakmaktan sorumlu olur.

```cpp
void detach();
```

### <a name="remarks"></a>Açıklamalar

Bir çağrısından sonra `detach` , [get_id](#get_id) için sonraki çağrılar döndürür. [](#id_class)

Çağıran nesneyle ilişkili iş parçacığı birlikte birleştirmiyorsa, işlev hata kodu olan bir [system_error](../standard-library/system-error-class.md) oluşturur `invalid_argument` .

Çağıran nesneyle ilişkili iş parçacığı geçersizse, işlev hata kodu olan bir oluşturur `system_error` `no_such_process` .

## <a name="threadget_id"></a><a name="get_id"></a> iş parçacığı:: get_id

İlişkili iş parçacığı için benzersiz bir tanımlayıcı döndürür.

```cpp
id get_id() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [thread::](#id_class) ilişkili iş parçacığını benzersiz bir şekilde tanımlayan veya `thread::id()` nesneyle ilişkili iş parçacığı olmayan ID nesnesi.

## <a name="threadhardware_concurrency"></a><a name="hardware_concurrency"></a> iş parçacığı:: hardware_concurrency

Donanım iş parçacığı bağlamlarının sayısının tahminini döndüren statik yöntem.

```cpp
static unsigned int hardware_concurrency() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Donanım iş parçacığı bağlamlarının sayısını tahmin edin. Değer hesaplanamıyor veya iyi tanımlanmamışsa, bu yöntem 0 döndürür.

## <a name="threadid-class"></a><a name="id_class"></a> Thread:: ID sınıfı

İşlemdeki her yürütme iş parçacığı için benzersiz bir tanımlayıcı sağlar.

```cpp
class thread::id {
    id() noexcept;
};
```

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, `thread::id` var olan herhangi bir iş parçacığının nesnesine eşit olarak karşılaştırmayan bir nesne oluşturur.

Varsayılan olarak oluşturulmuş tüm `thread::id` Nesneler eşit olarak karşılaştırılır.

## <a name="threadjoin"></a><a name="join"></a> Thread:: JOIN

Çağıran nesneyle ilişkili yürütmenin iş parçacığı tamamlanana kadar engeller.

```cpp
void join();
```

### <a name="remarks"></a>Açıklamalar

Çağrı başarılı olursa, çağıran nesne için [get_id](#get_id) sonraki çağrıları, var olan herhangi bir iş parçacığının ile eşit olarak karşılaştırmayan bir varsayılan [iş parçacığı:: ID](#id_class) döndürür `thread::id` ; çağrı başarısız olursa, tarafından döndürülen değer `get_id` değiştirilmez.

## <a name="threadjoinable"></a><a name="joinable"></a> Thread:: joinable

İlişkili iş parçacığının *joinable* olup olmadığını belirtir.

```cpp
bool joinable() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** ilişkili iş parçacığı *birleştirilebilir*; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bir iş parçacığı nesnesi, if ise *birleştirilebilir* `get_id() != id()` .

## <a name="threadnative_handle"></a><a name="native_handle"></a> iş parçacığı:: native_handle

İş parçacığı tanıtıcısını temsil eden uygulamaya özel türü döndürür. İş parçacığı tanıtıcısı, uygulamaya özgü yollarla kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type` , olarak atama yapan bir Win32 olarak tanımlanır `HANDLE` `void *` .

## <a name="threadoperator"></a><a name="op_eq"></a> Thread:: operator =

Belirtilen nesnenin iş parçacığını geçerli nesneyle ilişkilendirir.

```cpp
thread& operator=(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bir `thread` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Çağıran nesne birleştirilebilir ise, yöntemi ayır çağırır.

İlişkilendirme yapıldıktan sonra, varsayılan olarak `Other` oluşturulmuş bir duruma ayarlanır.

## <a name="threadswap"></a><a name="swap"></a> Thread:: swap

Nesne durumunu belirtilen bir nesne ile değiştirir `thread` .

```cpp
void swap(thread& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Farklı*\
Bir `thread` nesnesi.

## <a name="threadthread-constructor"></a><a name="thread"></a> Thread:: Thread Oluşturucusu

Bir `thread` nesnesi oluşturur.

```cpp
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Vadeli*\
İş parçacığı tarafından yürütülecek uygulama tanımlı bir işlev.

*A*\
*F*'ye geçirilecek bağımsız değişkenlerin listesi.

*Farklı*\
Varolan bir `thread` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, yürütme iş parçacığı ile ilişkilendirilmemiş bir nesne oluşturur. Oluşturulan nesne için çağrısı tarafından döndürülen değer `get_id` `thread::id()` .

İkinci Oluşturucu, yürütmenin yeni bir iş parçacığıyla ilişkili bir nesne oluşturur ve içinde tanımlanan sözde işlevi yürütür `INVOKE` [\<functional>](../standard-library/functional.md) . Yeni bir iş parçacığı başlatmak için yeterli kaynak yoksa, işlev hata kodu olan bir [system_error](../standard-library/system-error-class.md) nesnesi oluşturur `resource_unavailable_try_again` . *F* çağrısı yakalanamayan bir özel durumla sonlandığında, [Terminate](../standard-library/exception-functions.md#terminate) çağırılır.

Üçüncü Oluşturucu, ile ilişkili iş parçacığıyla ilişkili bir nesne oluşturur `Other` . `Other` sonra varsayılan olarak oluşturulmuş bir duruma ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<thread>](../standard-library/thread.md)
