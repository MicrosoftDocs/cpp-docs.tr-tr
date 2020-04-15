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
ms.openlocfilehash: eb171e09451e16e89716dfdc44ed6c611e2d2280
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372118"
---
# <a name="packaged_task-class"></a>packaged_task Sınıfı

Çağrı *asynchronous provider* imzası olan bir çağrı sarıcı olan eşzamanlı `Ty(ArgTypes...)`bir sağlayıcı açıklar. *İlişkili asenkron durumu,* olası sonuca ek olarak çağrılabilir nesnesinin bir kopyasını tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class>
class packaged_task;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Packaged_task](#packaged_task)|Bir `packaged_task` nesne inşa eder.|
|[packaged_task::~packaged_task Yıkıcı](#dtorpackaged_task_destructor)|Bir `packaged_task` nesneyi yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[get_future](#get_future)|Aynı ilişkili asynchronous durumuna sahip [gelecekteki](../standard-library/future-class.md) bir nesne döndürür.|
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|İlişkili eşzamanlı durumda depolanan çağrılabilir nesneyi çağırır ve döndürülen değeri atomik olarak depolar.|
|[Sıfırlamak](#reset)|İlişkili eşzamanlı durumu değiştirir.|
|[Takas](#swap)|İlişkili asenkron durumu, belirtilen bir nesnenin durumuyla değiştirir.|
|[Geçerli](#valid)|Nesnenin ilişkili bir asynchronous durumu olup olmadığını belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[packaged_task::operator=](#op_eq)|İlişkili bir eşzamanlı durumu belirtilen bir nesneden aktarın.|
|[packaged_task::operator()](#op_call)|İlişkili eşzamanlı durumda depolanan çağrılabilir nesneyi çağırır, döndürülen değeri atomik olarak depolar ve durumu *hazır*adatır.|
|[packaged_task::operatör bool](#op_bool)|Nesnenin ilişkili bir asynchronous durumu olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<gelecek>

**Ad alanı:** std

## <a name="packaged_taskget_future"></a><a name="get_future"></a>packaged_task:get_future

Aynı *ilişkili asynchronous durumuna*sahip bir tür `future<Ty>` nesnesi döndürür.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Açıklamalar

Nesne ilişkili bir eşzamanlı durum yoksa, bu yöntem `no_state`. hata kodu olan bir [future_error](../standard-library/future-error-class.md) atar `packaged_task`

Bu yöntem zaten aynı ilişkili `packaged_task` eşil durumu olan bir nesne için çağrıldı, `future_error` yöntem bir hata `future_already_retrieved`kodu olan atar .

## <a name="packaged_taskmake_ready_at_thread_exit"></a><a name="make_ready_at_thread_exit"></a>packaged_task:make_ready_at_thread_exit

*İlişkili eşzamanlı durumda* depolanan çağrılabilir nesneyi çağırır ve döndürülen değeri atomik olarak depolar.

```cpp
void make_ready_at_thread_exit(ArgTypes... args);
```

### <a name="remarks"></a>Açıklamalar

Nesne ilişkili bir asynchronous durumu yoksa, bu yöntem hata kodu olan bir `no_state`future_error atar. [future_error](../standard-library/future-error-class.md) `packaged_task`

Bu yöntem veya [make_ready_at_thread_exit](#make_ready_at_thread_exit) zaten aynı `packaged_task` ilişkili asynchronous durumuna sahip bir nesne için `future_error` çağrıldı, yöntem `promise_already_satisfied`bir hata kodu olan atar .

Aksi takdirde, `INVOKE(fn, args..., Ty)`bu işleç , *fn* ilişkili asynchronous durumda depolanan çağrılabilir nesne olduğu çağırır. Döndürülen herhangi bir değer, ilişkili eşzamanlı durumunun döndürülen sonucu olarak atomik olarak depolanır.

[packaged_task aksine::operator()](#op_call), ilişkili asenkron durum, çağrı `ready` iş parçacığındaki tüm iş parçacığı yerel nesneleri yok edilene kadar ayarlanmaz. Genellikle, ilişkili asenkron durumda engellenen iş parçacıkları, çağrı iş parçacığı çıkana kadar engellenmez.

## <a name="packaged_taskoperator"></a><a name="op_eq"></a>packaged_task::operator=

*İlişkili asenkron durumu* belirtilen bir nesneden aktarın.

```cpp
packaged_task& operator=(packaged_task&& Right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `packaged_task` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

İşlemden sonra, *Sağ* artık ilişkili bir eşzamanlı durum vardır.

## <a name="packaged_taskoperator"></a><a name="op_call"></a>packaged_task::operator()

*İlişkili eşzamanlı durumda*depolanan çağrılabilir nesneyi çağırır, döndürülen değeri atomik olarak depolar ve durumu *hazır*adatır.

```cpp
void operator()(ArgTypes... args);
```

### <a name="remarks"></a>Açıklamalar

Nesne ilişkili bir asynchronous durumu yoksa, bu yöntem hata kodu olan bir `no_state`future_error atar. [future_error](../standard-library/future-error-class.md) `packaged_task`

Bu yöntem veya [make_ready_at_thread_exit](#make_ready_at_thread_exit) zaten aynı `packaged_task` ilişkili asynchronous durumuna sahip bir nesne için `future_error` çağrıldı, yöntem `promise_already_satisfied`bir hata kodu olan atar .

Aksi takdirde, `INVOKE(fn, args..., Ty)`bu işleç , *fn* ilişkili asynchronous durumda depolanan çağrılabilir nesne olduğu çağırır. Döndürülen herhangi bir değer, ilişkili eşzamanlı durumunun döndürülen sonucu olarak atomik olarak depolanır ve durum hazır olarak ayarlanır. Sonuç olarak, ilişkili asynchronous durumunda engellenen tüm iş parçacıkları engellenir.

## <a name="packaged_taskoperator-bool"></a><a name="op_bool"></a>packaged_task::operatör bool

Nesnenin bir `associated asynchronous state`.

```cpp
operator bool() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

nesnenin ilişkili bir eşzamanlı durumu varsa **doğru;** aksi takdirde, **yanlış**.

## <a name="packaged_taskpackaged_task-constructor"></a><a name="packaged_task"></a>packaged_task::packaged_task Constructor

Bir `packaged_task` nesne inşa eder.

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

*Doğru*\
Bir `packaged_task` nesnesi.

*Ayırma*\
Bir bellek ayırıcısı. Daha fazla bilgi için [ \<>ayırıcılara ](../standard-library/allocators-header.md)bakın.

*Fn*\
Bir işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, ilişkili `packaged_task` *asynchronous durumu*olmayan bir nesne yi inşa eder.

İkinci oluşturucu bir `packaged_task` nesne inşa eder ve ilişkili asenkron durumu *Sağ'dan*aktarMaktadır. İşlemden sonra, *Sağ* artık ilişkili bir eşzamanlı durum vardır.

Üçüncü oluşturucu, ilişkili `packaged_task` asynchronous durumunda depolanan *fn'nin* bir kopyasını içeren bir nesne inşa eder.

Dördüncü oluşturucu, ilişkili `packaged_task` asynchronous durumunda depolanan *fn* bir kopyasını olan bir `alloc` nesne inşa eder ve bellek ayırma için kullanır.

## <a name="packaged_taskpackaged_task-destructor"></a><a name="dtorpackaged_task_destructor"></a>packaged_task::~packaged_task Yıkıcı

Bir `packaged_task` nesneyi yok eder.

```cpp
~packaged_task();
```

### <a name="remarks"></a>Açıklamalar

*İlişkili eşyokolon durum* *hazır*değilse, yıkıcı ilişkili asenkron durumda sonuç `broken_promise` olarak bir hata kodu olan bir [future_error](../standard-library/future-error-class.md) özel durum depolar ve ilişkili eşzamanlı durumda engellenen tüm iş parçacıkları engellenmemiş olur.

## <a name="packaged_taskreset"></a><a name="reset"></a>packaged_task::sıfırlama

Varolan ilişkili eşzamanlı durumu değiştirmek için yeni ilişkili bir *eşyokuz durumu* kullanır.

```cpp
void reset();
```

### <a name="remarks"></a>Açıklamalar

Sonuç olarak, bu `*this = packaged_task(move(fn))`yöntem, *fn* bu nesne için ilişkili asynchronöz durumda depolanan işlev nesnesi olduğu yürütülür. Bu nedenle, nesnenin durumu temizlenir ve [get_future](#get_future), [işleç()](#op_call)ve [make_ready_at_thread_exit](#make_ready_at_thread_exit) yeni oluşturulmuş bir nesne üzerinde sanki çağrılabilir.

## <a name="packaged_taskswap"></a><a name="swap"></a>packaged_task::takas

İlişkili asenkron durumu, belirtilen bir nesnenin durumuyla değiştirir.

```cpp
void swap(packaged_task& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Bir `packaged_task` nesnesi.

## <a name="packaged_taskvalid"></a><a name="valid"></a>packaged_task::geçerli

Nesnenin bir `associated asynchronous state`.

```cpp
bool valid() const;
```

### <a name="return-value"></a>Dönüş Değeri

nesnenin ilişkili bir eşzamanlı durumu varsa **doğru;** aksi takdirde, **yanlış**.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<gelecek>](../standard-library/future.md)
