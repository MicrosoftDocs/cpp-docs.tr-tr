---
title: thread sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: bfcb554b374d035e85d53d769d04317e52e4193b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861129"
---
# <a name="thread-class"></a>thread Sınıfı

İnceleyin ve bir uygulama içinde yürütme iş parçacığı yönetmek için kullanılan nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class thread;
```

## <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz bir `thread` inceleyin ve bir uygulama içinde yürütme iş parçacığı yönetmek için nesne. Varsayılan oluşturucu kullanılarak oluşturulan bir iş parçacığı nesnesi herhangi yürütme iş parçacığı ile ilişkili değil. Aranabilir nesnesi kullanılarak oluşturulan bir iş parçacığı nesnesi yeni bir iş parçacığı yürütme oluşturur ve bu iş parçacığında aranabilir nesne çağırır. İş parçacığı nesneleri taşınabilir ancak kopyalanmadı. Bu nedenle, bir iş parçacığı yürütme yalnızca bir iş parçacığı nesne ile ilişkili olabilir.

Her iş parçacığı yürütme benzersiz bir tanımlayıcı türü sahip `thread::id`. İşlev `this_thread::get_id` çağıran iş parçacığı tanımlayıcısını döndürür. Üye işlevini `thread::get_id` bir iş parçacığı nesnesi tarafından yönetilen iş parçacığı tanımlayıcısını döndürür. Varsayılan oluşturulan iş parçacığı nesnesi için `thread::get_id` yöntemi aynı tüm varsayılan oluşturulan iş parçacığı nesneleri ve tarafından döndürülen değeri farklı bir değere sahip bir nesne döndürür `this_thread::get_id` verebilir yürütme herhangi bir iş parçacığı için Çağrı aynı anda katılması.

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Genel sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[Thread::id sınıfı](#id_class)|İlişkili iş parçacığı benzersiz olarak tanımlar.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[thread](#thread)|Oluşturan bir `thread` nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ayırma](#detach)|İlişkili iş parçacığından ayırır `thread` nesnesi.|
|[get_id](#get_id)|İlişkili iş parçacığı benzersiz tanımlayıcısını döndürür.|
|[hardware_concurrency](#hardware_concurrency)|Statik. Tahmini donanım iş parçacıklarının sayısını döndürür.|
|[Birleştirme](#join)|İlişkili iş parçacığı tamamlanana kadar engeller.|
|[birleştirilebilir](#joinable)|İlişkili iş parçacığı birleştirilebilir olup olmadığını belirtir.|
|[native_handle](#native_handle)|İş parçacığı tutamacı temsil eden uygulamaya özel tür döndürür.|
|[Değiştirme](#swap)|Belirtilen nesne durumu değiştirir `thread` nesnesi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Thread::operator =](#op_eq)|Geçerli bir iş parçacığı ilişkilendirir `thread` nesnesi.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<iş parçacığı >

**Namespace:** std

## <a name="detach"></a>  Thread::detach

İlişkili iş parçacığı ayırır. İşletim sistemi sonlandırma iş parçacığı kaynakları serbest bırakma için sorumlu olur.

```cpp
void detach();
```

### <a name="remarks"></a>Açıklamalar

Çağrı sonra `detach`, sonraki çağrılar [get_ıd](#get_id) dönmek [kimliği](#id_class).

Çağıran nesne ile ilişkili iş parçacığı birleştirilebilir değil, işlevi döndürürse bir [system_error](../standard-library/system-error-class.md) hata kodunu olan `invalid_argument`.

Çağıran nesne ile ilişkili iş parçacığı geçersiz, işlevi döndürürse bir `system_error` hata kodunu olan `no_such_process`.

## <a name="get_id"></a>  Thread::get_id

İlişkili iş parçacığı için benzersiz bir tanımlayıcı döndürür.

```cpp
id get_id() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

A [thread::id](#id_class) ilişkili iş parçacığı, benzersiz olarak tanımlayan nesne veya `thread::id()` hiçbir iş parçacığı nesne ile ilişkili ise.

## <a name="hardware_concurrency"></a>  Thread::hardware_concurrency

Donanım iş parçacıklarının sayısını tahmin döndüren statik yöntem.

```cpp
static unsigned int hardware_concurrency() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Tahmini donanım iş parçacıklarının sayısı. Değer hesaplanamıyor veya iyi tanımlanmış değilse, bu yöntem 0 döndürür.

## <a name="id_class"></a>  Thread::id sınıfı

İşlem yürütme her bir iş parçacığı için benzersiz bir tanımlayıcı sağlar.

```cpp
class thread::id {
    id() noexcept;
};
```

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu karşılaştırma değil bir nesne eşit oluşturur `thread::id` var olan tüm iş parçacığı için nesne.

Tüm varsayılan oluşturulan `thread::id` nesneleri eşit karşılaştırın.

## <a name="join"></a>  Thread::join

İş parçacığı arama nesnesiyle ilişkili yürütme tamamlanana kadar engeller.

```cpp
void join();
```

### <a name="remarks"></a>Açıklamalar

Çağrı başarılı olursa, sonraki çağrılar [get_ıd](#get_id) çağıran nesne için varsayılan dönüş [thread::id](#id_class) , değil karşılaştırmak eşit `thread::id` çağrı başarılı olmazsa tüm mevcut iş parçacığının; , tarafından döndürülen değer `get_id` değişmez.

## <a name="joinable"></a>  Thread::joinable

İlişkili iş parçacığı olup olmadığını belirtir *birleştirilebilir*.

```cpp
bool joinable() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

`true` ilişkili iş parçacığı ise *birleştirilebilir*; Aksi halde, `false`.

### <a name="remarks"></a>Açıklamalar

Bir iş parçacığı nesnesi *birleştirilebilir* varsa `get_id() != id()`.

## <a name="native_handle"></a>  Thread::native_handle

İş parçacığı tutamacı temsil eden uygulamaya özel tür döndürür. İş parçacığı tutamacı uygulamaya özel yollarla kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type` Win32 tanımlanan `HANDLE` olarak cast `void *`.

## <a name="op_eq"></a>  Thread::operator =

İş parçacığı belirtilen nesnenin geçerli nesne ile ilişkilendirir.

```cpp
thread& operator=(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

`Other` A `thread` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Çağıran nesne birleştirilebilir ise, yöntem çağrılarını kullanımdan çıkarın.

İlişkilendirme yapıldıktan sonra `Other` varsayılan oluşturulan bir durumuna ayarlanır.

## <a name="swap"></a>  Thread::Swap

Nesne durumu belirtilen değeriyle değiştirir `thread` nesnesi.

```cpp
void swap(thread& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

`Other` A `thread` nesnesi.

## <a name="thread"></a>  Thread::thread Oluşturucusu

Oluşturan bir `thread` nesnesi.

```cpp
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

`F` İş parçacığı tarafından çalıştırılacak bir uygulama tanımlı işlev.

`A` Geçirilecek bağımsız değişkenler listesi `F`.

`Other` Varolan bir `thread` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu yürütme iş parçacığı ile ilişkili olmayan bir nesne oluşturur. Bir çağrı tarafından döndürülen değer `get_id` oluşturulan nesneye için `thread::id()`.

İkinci oluşturucu yürütme yeni bir iş parçacığı ile ilişkili olan ve sahte işlevi yürüten bir nesne oluşturur `INVOKE` içinde tanımlanan [ \<işlevsel >](../standard-library/functional.md). Yeni bir iş parçacığı başlatmak yeterli kaynaklar kullanılabilir durumdaysa işlevi oluşturur bir [system_error](../standard-library/system-error-class.md) , hata kodunu sahip bir nesne `resource_unavailable_try_again`. Varsa çağrısı `F` yakalanmayan bir özel durumla sona erer [sonlandırmak](../standard-library/exception-functions.md#terminate) olarak adlandırılır.

Üçüncü Oluşturucusu ile ilişkili iş parçacığı ile ilişkili bir nesne oluşturur `Other`. `Other` ardından bir varsayılan oluşturulan durumuna ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<iş parçacığı >](../standard-library/thread.md)<br/>
