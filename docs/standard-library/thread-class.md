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
ms.openlocfilehash: d1405062ef553dbfea3b60b5f39e0546707343b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412078"
---
# <a name="thread-class"></a>thread Sınıfı

İnceleyin ve uygulamadaki iş parçacığı yönetmek için kullanılan nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class thread;
```

## <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz bir **iş parçacığı** inceleyin ve uygulamadaki iş parçacığı yönetmek için nesne. Varsayılan oluşturucu kullanılarak oluşturulan bir iş parçacığı nesnesi ile yürütme herhangi bir iş parçacığı ilişkili değil. Çağrılabilir nesnesi kullanılarak oluşturulan bir iş parçacığı nesnesi, yeni bir iş parçacığı yürütme oluşturur ve bu iş parçacığındaki çağrılabilir nesne çağırır. İş parçacığı nesneleri taşınabilir ancak kopyalanamaz. Bu nedenle, bir iş parçacığı, yalnızca bir iş parçacığı nesnesi ile ilişkilendirilmiş olabilir.

Her iş parçacığı yürütme sahip türünün benzersiz bir tanımlayıcı `thread::id`. İşlev `this_thread::get_id` çağıran iş parçacığını tanımlayıcısını döndürür. Üye işlevi `thread::get_id` bir iş parçacığı nesnesi tarafından yönetilen iş parçacığı tanımlayıcısını döndürür. Varsayılan olarak oluşturulan iş parçacığı nesnesi için `thread::get_id` yöntemi aynı tüm varsayılan olarak oluşturulan iş parçacığı nesneleri ve döndürdüğü değerden farklı bir değere sahip bir nesne döndürür `this_thread::get_id` herhangi bir iş parçacığı verebilir yürütme için Aramanın zaman katılması.

## <a name="members"></a>Üyeler

### <a name="public-classes"></a>Genel sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[Thread::id sınıfı](#id_class)|İlişkili iş parçacığının benzersiz olarak tanımlar.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[thread](#thread)|Oluşturur bir **iş parçacığı** nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ayırma](#detach)|İlişkili iş parçacığından ayırır **iş parçacığı** nesne.|
|[get_id](#get_id)|İlişkili iş parçacığının benzersiz tanımlayıcısını döndürür.|
|[hardware_concurrency](#hardware_concurrency)|Statik. Tahmini donanım iş parçacıklarının sayısını döndürür.|
|[Katılın](#join)|İlişkili iş parçacığı tamamlanıncaya kadar engeller.|
|[birleştirilebilir](#joinable)|İlişkili iş parçacığı birleştirilebilir olup olmadığını belirtir.|
|[native_handle](#native_handle)|İş parçacığı işleyicisini temsil eden uygulamaya özel türü döndürür.|
|[değiştirme](#swap)|Belirtilen nesne durumu değiştirir **iş parçacığı** nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Thread::operator =](#op_eq)|Geçerli bir iş parçacığı ilişkilendirir **iş parçacığı** nesne.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<iş parçacığı >

**Namespace:** std

## <a name="detach"></a>  Thread::detach

İlişkili iş parçacığı ayırır. İşletim sistemi üzerinde sonlandırma iş parçacığı kaynakları serbest bırakmak için sorumlu olur.

```cpp
void detach();
```

### <a name="remarks"></a>Açıklamalar

Çağrısı yapıldıktan sonra `detach`sonraki çağrılar [get_ıd](#get_id) dönüş [kimliği](#id_class).

İşlev çağırma nesne ile ilişkili iş parçacığı birleştirilebilir değilse, oluşturur bir [system_error](../standard-library/system-error-class.md) bir hata koduna sahip `invalid_argument`.

Arama nesne ile ilişkili iş parçacığı geçersiz ise, işlev oluşturur bir `system_error` bir hata koduna sahip `no_such_process`.

## <a name="get_id"></a>  Thread::get_id

İlişkili iş parçacığı için benzersiz bir tanımlayıcı döndürür.

```cpp
id get_id() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

A [thread::id](#id_class) ilişkili iş parçacığının benzersiz olarak tanımlayan bir nesne veya `thread::id()` hiçbir iş parçacığı nesnesi ile ilişkili ise.

## <a name="hardware_concurrency"></a>  Thread::hardware_concurrency

Donanım iş parçacıklarının sayısını tahmin döndüren statik yöntem.

```cpp
static unsigned int hardware_concurrency() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

Donanım iş parçacıklarının sayısını tahmin edin. Bu yöntem, değeri hesaplanamıyor veya iyi tanımlanmış değilse, 0 döndürür.

## <a name="id_class"></a>  Thread::id sınıfı

Her iş parçacığı bir işlemdeki yürütme için benzersiz bir tanımlayıcı sağlar.

```cpp
class thread::id {
    id() noexcept;
};
```

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu karşılaştırmaz bir nesne eşit oluşturur `thread::id` var olan herhangi bir iş parçacığı için nesne.

Tüm varsayılan oluşturulmuş `thread::id` nesneler eşit karşılaştırın.

## <a name="join"></a>  Thread::join

İş parçacığı arama nesne ile ilişkili yürütme tamamlanıncaya kadar engeller.

```cpp
void join();
```

### <a name="remarks"></a>Açıklamalar

Çağrı başarılı olursa, yapılan sonraki çağrılar [get_ıd](#get_id) çağrı nesnesi için varsayılan dönüş [thread::id](#id_class) , değil karşılaştırma eşit `thread::id` çağrısı başarısız olursa tüm mevcut iş parçacığının; , tarafından döndürülen değer `get_id` değiştirilmez.

## <a name="joinable"></a>  Thread::joinable

İlişkili iş parçacığı olup olmadığını belirtir *birleştirilebilir*.

```cpp
bool joinable() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilişkili iş parçacığı ise *birleştirilebilir*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bir iş parçacığı nesnesi *birleştirilebilir* varsa `get_id() != id()`.

## <a name="native_handle"></a>  Thread::native_handle

İş parçacığı işleyicisini temsil eden uygulamaya özel türü döndürür. İş parçacığı tutamacı, uygulamaya özel şekillerde kullanılabilir.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Dönüş Değeri

`native_handle_type` bir Win32 tanımlanan `HANDLE` olarak cast `void *`.

## <a name="op_eq"></a>  Thread::operator =

İş parçacığı belirtilen bir nesnenin geçerli nesneye ile ilişkilendirir.

```cpp
thread& operator=(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
A **iş parçacığı** nesne.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

Çağrı nesnesi birleştirilebilir ise, yöntem çağrılarını çıkarın.

İlişki kurulduktan sonra `Other` varsayılan olarak oluşturulmuş bir duruma ayarlanır.

## <a name="swap"></a>  Thread::Swap

Belirli bir nesne durumunu değiştirir **iş parçacığı** nesne.

```cpp
void swap(thread& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
A **iş parçacığı** nesne.

## <a name="thread"></a>  Thread::thread Oluşturucusu

Oluşturur bir **iş parçacığı** nesne.

```cpp
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parametreler

*F*<br/>
İş parçacığı tarafından yürütülecek bir uygulama tanımlı işlev.

*A*<br/>
Geçirilecek bağımsız değişkenler listesi *F*.

*Diğer*<br/>
Mevcut bir **iş parçacığı** nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, yürütme iş parçacığı ile ilişkili olmayan bir nesne oluşturur. Bir çağrı tarafından döndürülen değer `get_id` oluşturulan nesne için `thread::id()`.

İkinci oluşturucu sözde işlevi yürütür ve yeni bir iş parçacığı yürütme ile ilişkili bir nesne oluşturur `INVOKE` içinde tanımlanan [ \<işlevsel >](../standard-library/functional.md). Yeni bir iş parçacığı yeterli kaynakları kullanılabilir, işlev oluşturur. bir [system_error](../standard-library/system-error-class.md) hata kodunu nesnesi `resource_unavailable_try_again`. Çağrı *F* yakalanmayan bir özel durumla sona erer [sonlandırmak](../standard-library/exception-functions.md#terminate) çağrılır.

Üçüncü Oluşturucu, ilişkili olduğu iş parçacığı ile ilişkili bir nesne oluşturur `Other`. `Other` Ardından, varsayılan olarak oluşturulmuş bir duruma ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<iş parçacığı >](../standard-library/thread.md)<br/>
