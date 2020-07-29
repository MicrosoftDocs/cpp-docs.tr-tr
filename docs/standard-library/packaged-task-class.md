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
ms.openlocfilehash: d03fb128240c4e3e6bd48c3237d240afba946ad8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233034"
---
# <a name="packaged_task-class"></a>packaged_task Sınıfı

Çağrı imzası olan bir çağrı sarmalayıcısı olan *zaman uyumsuz sağlayıcıyı* açıklar `Ty(ArgTypes...)` . *İlişkili zaman uyumsuz durumu* , olası sonucun yanı sıra çağrılabilir nesnesinin bir kopyasını tutar.

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
|[packaged_task:: ~ packaged_task yok edici](#dtorpackaged_task_destructor)|Bir nesneyi yok eder `packaged_task` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_future](#get_future)|Aynı ilişkili zaman uyumsuz duruma sahip [gelecek](../standard-library/future-class.md) bir nesne döndürür.|
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|İlişkili zaman uyumsuz durumda depolanan çağrılabilir nesneyi çağırır ve döndürülen değeri otomatik olarak depolar.|
|[döndürmek](#reset)|İlişkili zaman uyumsuz durumu değiştirir.|
|[Kur](#swap)|İlişkili zaman uyumsuz durumu, belirtilen bir nesne ile değiş tokuş eder.|
|[geçerli](#valid)|Nesnenin ilişkili bir zaman uyumsuz duruma sahip olup olmadığını belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[packaged_task:: operator =](#op_eq)|Belirtilen bir nesneden ilişkili bir zaman uyumsuz durumu aktarır.|
|[packaged_task:: operator ()](#op_call)|İlişkili zaman uyumsuz durumda depolanan çağrılabilir nesneyi çağırır, döndürülen değeri otomatik olarak depolar ve durumu *Ready*olarak ayarlar.|
|[packaged_task:: operator bool](#op_bool)|Nesnenin ilişkili bir zaman uyumsuz duruma sahip olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<future>

**Ad alanı:** std

## <a name="packaged_taskget_future"></a><a name="get_future"></a>packaged_task:: get_future

`future<Ty>`Aynı *ilişkili zaman uyumsuz duruma*sahip olan türde bir nesne döndürür.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Açıklamalar

`packaged_task`Nesnenin ilişkili bir zaman uyumsuz durumu yoksa, bu yöntem hata kodu olan bir [future_error](../standard-library/future-error-class.md) oluşturur `no_state` .

`packaged_task`Aynı ilişkili zaman uyumsuz duruma sahip bir nesne için bu yöntem zaten çağrılırsa, yöntemi hata kodu olan bir oluşturur `future_error` `future_already_retrieved` .

## <a name="packaged_taskmake_ready_at_thread_exit"></a><a name="make_ready_at_thread_exit"></a>packaged_task:: make_ready_at_thread_exit

*İlişkili zaman uyumsuz durumda* depolanan çağrılabilir nesneyi çağırır ve döndürülen değeri otomatik olarak depolar.

```cpp
void make_ready_at_thread_exit(ArgTypes... args);
```

### <a name="remarks"></a>Açıklamalar

`packaged_task`Nesnenin ilişkili bir zaman uyumsuz durumu yoksa, bu yöntem hata kodu olan bir [future_error](../standard-library/future-error-class.md) oluşturur `no_state` .

Aynı ilişkili zaman uyumsuz duruma sahip bir nesne için bu yöntem veya [make_ready_at_thread_exit](#make_ready_at_thread_exit) zaten çağrılırsa `packaged_task` , yöntemi hata kodu olan bir oluşturur `future_error` `promise_already_satisfied` .

Aksi takdirde, bu işleç çağrılır `INVOKE(fn, args..., Ty)` , burada *FN* , ilişkili zaman uyumsuz durumda depolanan çağrılabilir nesnedir. Döndürülen tüm değerler, ilişkili zaman uyumsuz durumun döndürülen sonucu olarak, otomatik olarak depolanır.

[Packaged_task:: operator ()](#op_call)' in aksine, ilişkili zaman uyumsuz durum, `ready` çağıran iş parçacığındaki tüm iş parçacığı yerel nesneleri yok edilene kadar olarak ayarlanır. Genellikle, ilişkili zaman uyumsuz durumda engellenen iş parçacıkları, çağıran iş parçacığına çıkana kadar engellenmemiş.

## <a name="packaged_taskoperator"></a><a name="op_eq"></a>packaged_task:: operator =

*İlişkili zaman uyumsuz durumu* belirtilen bir nesneden aktarır.

```cpp
packaged_task& operator=(packaged_task&& Right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `packaged_task` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

İşlemden *sonra, artık* ilişkili bir zaman uyumsuz duruma sahip değildir.

## <a name="packaged_taskoperator"></a><a name="op_call"></a>packaged_task:: operator ()

*İlişkili zaman uyumsuz durumda*depolanan çağrılabilir nesneyi çağırır, döndürülen değeri otomatik olarak depolar ve durumu *Ready*olarak ayarlar.

```cpp
void operator()(ArgTypes... args);
```

### <a name="remarks"></a>Açıklamalar

`packaged_task`Nesnenin ilişkili bir zaman uyumsuz durumu yoksa, bu yöntem hata kodu olan bir [future_error](../standard-library/future-error-class.md) oluşturur `no_state` .

Aynı ilişkili zaman uyumsuz duruma sahip bir nesne için bu yöntem veya [make_ready_at_thread_exit](#make_ready_at_thread_exit) zaten çağrılırsa `packaged_task` , yöntemi hata kodu olan bir oluşturur `future_error` `promise_already_satisfied` .

Aksi takdirde, bu işleç çağrılır `INVOKE(fn, args..., Ty)` , burada *FN* , ilişkili zaman uyumsuz durumda depolanan çağrılabilir nesnedir. Döndürülen herhangi bir değer, ilişkili zaman uyumsuz durumun döndürülen sonucu olarak otomatik olarak depolanır ve durum, Ready olarak ayarlanır. Sonuç olarak, ilişkili zaman uyumsuz durumda engellenen tüm iş parçacıkları engellenmemiş hale gelir.

## <a name="packaged_taskoperator-bool"></a><a name="op_bool"></a>packaged_task:: operator bool

Nesnenin öğesine sahip olup olmadığını belirtir `associated asynchronous state` .

```cpp
operator bool() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesnenin ilişkili bir zaman uyumsuz durumu varsa; Aksi takdirde, **`false`** .

## <a name="packaged_taskpackaged_task-constructor"></a><a name="packaged_task"></a>packaged_task::p ackaged_task Oluşturucusu

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
Bir `packaged_task` nesnesi.

*tahsis*\
Bir bellek ayırıcısı. Daha fazla bilgi için bkz. [\<allocators>](../standard-library/allocators-header.md).

*FN*\
Bir işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `packaged_task` *ilişkili zaman uyumsuz durumu*olmayan bir nesne oluşturur.

İkinci Oluşturucu bir nesne oluşturur `packaged_task` ve ilişkili zaman uyumsuz durumu *sağdan*aktarır. İşlemden *sonra, artık* ilişkili bir zaman uyumsuz duruma sahip değildir.

Üçüncü Oluşturucu, `packaged_task` ilişkili zaman uyumsuz durumunda bulunan *FN* 'nin bir kopyasına sahip bir nesne oluşturur.

Dördüncü Oluşturucu, `packaged_task` ilişkili zaman uyumsuz durumunda bulunan bir *FN* kopyasına sahip bir nesne oluşturur ve `alloc` bellek ayırma için kullanır.

## <a name="packaged_taskpackaged_task-destructor"></a><a name="dtorpackaged_task_destructor"></a>packaged_task:: ~ packaged_task yok edici

Bir nesneyi yok eder `packaged_task` .

```cpp
~packaged_task();
```

### <a name="remarks"></a>Açıklamalar

*İlişkili zaman uyumsuz durum* *yoksa, yıkıcı,* ilişkili zaman uyumsuz durumunda sonuç olarak hata kodu olan [future_error](../standard-library/future-error-class.md) bir özel durum depolar `broken_promise` ve ilişkili zaman uyumsuz durumda engellenen tüm iş parçacıkları engellenmemiş olur.

## <a name="packaged_taskreset"></a><a name="reset"></a>packaged_task:: Reset

Var olan ilişkili zaman uyumsuz durumu değiştirmek için yeni bir *ilişkili zaman uyumsuz durum* kullanır.

```cpp
void reset();
```

### <a name="remarks"></a>Açıklamalar

Aslında bu yöntem yürütülür `*this = packaged_task(move(fn))` , burada *FN* bu nesne için ilişkili zaman uyumsuz durumda depolanan Function nesnesidir. Bu nedenle, nesnenin durumu temizlenir ve [get_future](#get_future), [işleç ()](#op_call)ve [make_ready_at_thread_exit](#make_ready_at_thread_exit) yeni oluşturulmuş bir nesne gibi çağrılabilir.

## <a name="packaged_taskswap"></a><a name="swap"></a>packaged_task:: swap

İlişkili zaman uyumsuz durumu, belirtilen bir nesne ile değiş tokuş eder.

```cpp
void swap(packaged_task& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `packaged_task` nesnesi.

## <a name="packaged_taskvalid"></a><a name="valid"></a>packaged_task:: geçerli

Nesnenin öğesine sahip olup olmadığını belirtir `associated asynchronous state` .

```cpp
bool valid() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesnenin ilişkili bir zaman uyumsuz durumu varsa; Aksi takdirde, **`false`** .

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
