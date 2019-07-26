---
title: packaged_task Sınıfı
ms.date: 11/04/2016
f1_keywords:
- future/std::packaged_task
- future/std::packaged_task::packaged_task
- future/std::packaged_task::get_future
- future/std::packaged_task::make_ready_at_thread_exit
- future/std::packaged_task::reset
- future/std::packaged_task::swap
- future/std::packaged_task::valid
- future/std::packaged_task::operator()
- future/std::packaged_task::operator bool
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
helpviewer_keywords:
- std::packaged_task [C++]
- std::packaged_task [C++], packaged_task
- std::packaged_task [C++], get_future
- std::packaged_task [C++], make_ready_at_thread_exit
- std::packaged_task [C++], reset
- std::packaged_task [C++], swap
- std::packaged_task [C++], valid
ms.openlocfilehash: 5bb04b84b723f239c338c02befa8cd3468cec3f2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450076"
---
# <a name="packagedtask-class"></a>packaged_task Sınıfı

Çağrı imzası `Ty(ArgTypes...)`olan bir çağrı sarmalayıcısı olan *zaman uyumsuz sağlayıcıyı* açıklar. *İlişkili zaman uyumsuz durumu* , olası sonucun yanı sıra çağrılabilir nesnesinin bir kopyasını tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class>
class packaged_task;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[packaged_task](#packaged_task)|Bir `packaged_task` nesnesi oluşturur.|
|[packaged_task:: ~ packaged_task yıkıcısı](#dtorpackaged_task_destructor)|Bir `packaged_task` nesneyi yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_future](#get_future)|Aynı ilişkili zaman uyumsuz duruma sahip [gelecek](../standard-library/future-class.md) bir nesne döndürür.|
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|İlişkili zaman uyumsuz durumda depolanan çağrılabilir nesneyi çağırır ve döndürülen değeri otomatik olarak depolar.|
|[döndürmek](#reset)|İlişkili zaman uyumsuz durumu değiştirir.|
|[Kur](#swap)|İlişkili zaman uyumsuz durumu, belirtilen bir nesne ile değiş tokuş eder.|
|[valid](#valid)|Nesnenin ilişkili bir zaman uyumsuz duruma sahip olup olmadığını belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[packaged_task::operator=](#op_eq)|Belirtilen bir nesneden ilişkili bir zaman uyumsuz durumu aktarır.|
|[packaged_task::operator()](#op_call)|İlişkili zaman uyumsuz durumda depolanan çağrılabilir nesneyi çağırır, döndürülen değeri otomatik olarak depolar ve durumu *Ready*olarak ayarlar.|
|[packaged_task:: operator bool](#op_bool)|Nesnenin ilişkili bir zaman uyumsuz duruma sahip olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<gelecekte >

**Ad alanı:** std

## <a name="get_future"></a>packaged_task::get_future

Aynı `future<Ty>` *ilişkili zaman uyumsuz duruma*sahip olan türde bir nesne döndürür.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Açıklamalar

Nesnenin ilişkili bir zaman uyumsuz durumu yoksa, bu yöntem hata kodu `no_state`olan bir [future_error](../standard-library/future-error-class.md) oluşturur. `packaged_task`

Aynı ilişkili zaman uyumsuz duruma sahip bir `packaged_task` nesne için bu yöntem zaten çağrılırsa, yöntemi hata kodu `future_already_retrieved`olan bir `future_error` oluşturur.

## <a name="make_ready_at_thread_exit"></a>packaged_task::make_ready_at_thread_exit

*İlişkili zaman uyumsuz durumda* depolanan çağrılabilir nesneyi çağırır ve döndürülen değeri otomatik olarak depolar.

```cpp
void make_ready_at_thread_exit(ArgTypes... args);
```

### <a name="remarks"></a>Açıklamalar

Nesnenin ilişkili bir zaman uyumsuz durumu yoksa, bu yöntem hata kodu `no_state`olan bir [future_error](../standard-library/future-error-class.md) oluşturur. `packaged_task`

Aynı ilişkili zaman uyumsuz [](#make_ready_at_thread_exit) duruma sahip bir `packaged_task` nesne için bu yöntem veya make_ready_at_thread_exit zaten çağrılırsa, yöntemi hata kodu `promise_already_satisfied`olan bir `future_error` oluşturur.

Aksi takdirde, bu işleç `INVOKE(fn, args..., Ty)`çağrılır, burada *FN* , ilişkili zaman uyumsuz durumda depolanan çağrılabilir nesnedir. Döndürülen tüm değerler, ilişkili zaman uyumsuz durumun döndürülen sonucu olarak, otomatik olarak depolanır.

[Packaged_task:: operator ()](#op_call)aksine, ilişkili zaman uyumsuz durum, çağıran iş parçacığındaki tüm `ready` iş parçacığı yerel nesneleri yok edilene kadar olarak ayarlanır. Genellikle, ilişkili zaman uyumsuz durumda engellenen iş parçacıkları, çağıran iş parçacığına çıkana kadar engellenmemiş.

## <a name="op_eq"></a>packaged_task:: operator =

*İlişkili zaman uyumsuz durumu* belirtilen bir nesneden aktarır.

```cpp
packaged_task& operator=(packaged_task&& Right);
```

### <a name="parameters"></a>Parametreler

*Right*\
A `packaged_task` nesne.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

İşlemden *sonra, artık* ilişkili bir zaman uyumsuz duruma sahip değildir.

## <a name="op_call"></a>packaged_task:: operator ()

*İlişkili zaman uyumsuz durumda*depolanan çağrılabilir nesneyi çağırır, döndürülen değeri otomatik olarak depolar ve durumu *Ready*olarak ayarlar.

```cpp
void operator()(ArgTypes... args);
```

### <a name="remarks"></a>Açıklamalar

Nesnenin ilişkili bir zaman uyumsuz durumu yoksa, bu yöntem hata kodu `no_state`olan bir [future_error](../standard-library/future-error-class.md) oluşturur. `packaged_task`

Aynı ilişkili zaman uyumsuz [](#make_ready_at_thread_exit) duruma sahip bir `packaged_task` nesne için bu yöntem veya make_ready_at_thread_exit zaten çağrılırsa, yöntemi hata kodu `promise_already_satisfied`olan bir `future_error` oluşturur.

Aksi takdirde, bu işleç `INVOKE(fn, args..., Ty)`çağrılır, burada *FN* , ilişkili zaman uyumsuz durumda depolanan çağrılabilir nesnedir. Döndürülen herhangi bir değer, ilişkili zaman uyumsuz durumun döndürülen sonucu olarak otomatik olarak depolanır ve durum, Ready olarak ayarlanır. Sonuç olarak, ilişkili zaman uyumsuz durumda engellenen tüm iş parçacıkları engellenmemiş hale gelir.

## <a name="op_bool"></a>packaged_task:: operator bool

Nesnenin öğesine sahip `associated asynchronous state`olup olmadığını belirtir.

```cpp
operator bool() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

nesnenin ilişkili bir zaman uyumsuz durumu varsa **doğru** ; Aksi takdirde, **false**.

## <a name="packaged_task"></a>packaged_task::p ackaged_task Oluşturucusu

Bir `packaged_task` nesnesi oluşturur.

```cpp
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```

### <a name="parameters"></a>Parametreler

*Right*\
A `packaged_task` nesne.

*tahsis*\
Bir bellek ayırıcısı. Daha fazla bilgi için bkz [ \<. ayrıcılar >](../standard-library/allocators-header.md).

*FN*\
Bir işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `packaged_task` *ilişkili zaman uyumsuz durumu*olmayan bir nesne oluşturur.

İkinci Oluşturucu bir `packaged_task` nesne oluşturur ve ilişkili zaman uyumsuz durumu *sağdan*aktarır. İşlemden *sonra, artık* ilişkili bir zaman uyumsuz duruma sahip değildir.

Üçüncü Oluşturucu, ilişkili zaman `packaged_task` uyumsuz durumunda bulunan *FN* 'nin bir kopyasına sahip bir nesne oluşturur.

Dördüncü Oluşturucu, ilişkili zaman `packaged_task` uyumsuz durumunda bulunan bir *FN* kopyasına sahip bir nesne oluşturur ve bellek ayırma için kullanır `alloc` .

## <a name="dtorpackaged_task_destructor"></a>packaged_task:: ~ packaged_task yıkıcısı

Bir `packaged_task` nesneyi yok eder.

```cpp
~packaged_task();
```

### <a name="remarks"></a>Açıklamalar

*İlişkili zaman uyumsuz durum* , yok edicisi, ilişkili zaman uyumsuz durumda ve üzerinde engellenen tüm iş parçacıkları  `broken_promise` gibi hata kodu olan bir [future_error](../standard-library/future-error-class.md) özel durumu depolar. ilişkili zaman uyumsuz durum engellenmemiş hale gelir.

## <a name="reset"></a>packaged_task:: Reset

Var olan ilişkili zaman uyumsuz durumu değiştirmek için yeni bir *ilişkili zaman uyumsuz durum* kullanır.

```cpp
void reset();
```

### <a name="remarks"></a>Açıklamalar

Aslında bu yöntem yürütülür `*this = packaged_task(move(fn))`, burada *FN* bu nesne için ilişkili zaman uyumsuz durumda depolanan Function nesnesidir. Bu nedenle, nesnenin durumu temizlenir ve [get_future](#get_future), [operator ()](#op_call)ve [make_ready_at_thread_exit](#make_ready_at_thread_exit) , yeni oluşturulmuş bir nesnede olduğu gibi çağrılabilir.

## <a name="swap"></a>packaged_task:: swap

İlişkili zaman uyumsuz durumu, belirtilen bir nesne ile değiş tokuş eder.

```cpp
void swap(packaged_task& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
A `packaged_task` nesne.

## <a name="valid"></a>packaged_task:: geçerli

Nesnenin öğesine sahip `associated asynchronous state`olup olmadığını belirtir.

```cpp
bool valid() const;
```

### <a name="return-value"></a>Dönüş Değeri

nesnenin ilişkili bir zaman uyumsuz durumu varsa **doğru** ; Aksi takdirde, **false**.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<gelecekte >](../standard-library/future.md)
