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
ms.openlocfilehash: e759b1bc8cb47c5c943f29545e3b03ee535f3df7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370677"
---
# <a name="packagedtask-class"></a>packaged_task Sınıfı

Açıklayan bir *zaman uyumsuz sağlayıcıyı* yani çağrı imzası olan bir çağrı sarmalayıcı `Ty(ArgTypes...)`. Kendi *ilişkili zaman uyumsuz durumu* olası sonucu yanı sıra kendi çağrılabilir nesnesinin bir kopyasını tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class>
class packaged_task;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[packaged_task](#packaged_task)|Oluşturur bir `packaged_task` nesne.|
|[packaged_task:: ~ packaged_task yıkıcısı](#dtorpackaged_task_destructor)|Yok eder bir `packaged_task` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get_future](#get_future)|Döndürür bir [gelecekteki](../standard-library/future-class.md) nesnesi aynı ilişkilendirilmiş zaman uyumsuz duruma.|
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|İlişkili zaman uyumsuz durumu içerisinde saklanan ve döndürülen değeri atomik olarak depolar çağrılabilir nesne çağırır.|
|[Sıfırlama](#reset)|İlişkili zaman uyumsuz durumu değiştirir.|
|[değiştirme](#swap)|İlişkili zaman uyumsuz duruma, belirtilen bir nesnenin ile değiştirir.|
|[valid](#valid)|Nesnenin ilişkili bir zaman uyumsuz duruma sahip olup olmadığını belirtir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[packaged_task::operator=](#op_eq)|Belirtilen bir nesneden bir ilişkili zaman uyumsuz durumu aktarır.|
|[packaged_task::operator()](#op_call)|İlişkili zaman uyumsuz durumu içerisinde saklanan, atomik olarak döndürülen değeri depolar ve durumu ayarlar çağrılabilir nesne çağırır *hazır*.|
|[packaged_task::operator bool](#op_bool)|Nesnenin ilişkili bir zaman uyumsuz duruma sahip olup olmadığını belirtir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecek >

**Namespace:** std

## <a name="get_future"></a>  packaged_task::get_future

Türünde bir nesne döndürür `future<Ty>` aynı olan *ilişkili zaman uyumsuz durumu*.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Açıklamalar

Varsa `packaged_task` nesne bir ilişkili zaman uyumsuz duruma sahip değil, bu yöntem bir [future_error](../standard-library/future-error-class.md) bir hata koduna sahip `no_state`.

Bu yöntem için zaten çağrılmış bir `packaged_task` nesnesi aynı ilişkilendirilmiş zaman uyumsuz duruma, çağırılıyorsa yöntem bir `future_error` bir hata koduna sahip `future_already_retrieved`.

## <a name="make_ready_at_thread_exit"></a>  packaged_task::make_ready_at_thread_exit

Depolanan çağrılabilir nesne çağırır *ilişkili zaman uyumsuz durumu* ve döndürülen değeri atomik olarak depolar.

```cpp
void make_ready_at_thread_exit(ArgTypes... args);
```

### <a name="remarks"></a>Açıklamalar

Varsa `packaged_task` bir ilişkili zaman uyumsuz durumu nesnesi yoksa, bu yöntem bir [future_error](../standard-library/future-error-class.md) bir hata koduna sahip `no_state`.

Bu yöntem veya [make_ready_at_thread_exit](#make_ready_at_thread_exit) için zaten çağrılmış bir `packaged_task` nesnesi aynı ilişkilendirilmiş zaman uyumsuz duruma, çağırılıyorsa yöntem bir `future_error` bir hata koduna sahip `promise_already_satisfied`.

Aksi takdirde, bu işlecini çağıran `INVOKE(fn, args..., Ty)`burada *fn* ilişkili zaman uyumsuz durumu içerisinde saklanan çağrılabilir nesnedir. Döndürülen herhangi bir değeri atomik olarak ilişkili zaman uyumsuz duruma döndürülen sonucu olarak depolanır.

Tersine [packaged_task:: operator()](#op_call), ilişkili zaman uyumsuz durumu olarak ayarlanmazsa `ready` çağıran iş parçacığındaki tüm iş parçacığı-yerel nesneleri yok olana kadar. Genellikle, çağıran iş parçacığı çıkana kadar ilişkili zaman uyumsuz durumda engellenen iş parçacıklarının engeli değildir.

## <a name="op_eq"></a>  packaged_task::operator =

Aktarımları *ilişkili zaman uyumsuz durumu* belirtilen bir nesneden.

```cpp
packaged_task& operator=(packaged_task&& Right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
A `packaged_task` nesne.

### <a name="return-value"></a>Dönüş Değeri

`*this`

### <a name="remarks"></a>Açıklamalar

İşlemden sonra *sağ* artık bir ilişkili zaman uyumsuz duruma sahip değil.

## <a name="op_call"></a>  packaged_task:: operator()

Depolanan çağrılabilir nesne çağırır *ilişkili zaman uyumsuz durumu*atomik olarak döndürülen değeri depolar ve durumu ayarlar *hazır*.

```cpp
void operator()(ArgTypes... args);
```

### <a name="remarks"></a>Açıklamalar

Varsa `packaged_task` bir ilişkili zaman uyumsuz durumu nesnesi yoksa, bu yöntem bir [future_error](../standard-library/future-error-class.md) bir hata koduna sahip `no_state`.

Bu yöntem veya [make_ready_at_thread_exit](#make_ready_at_thread_exit) için zaten çağrılmış bir `packaged_task` nesnesi aynı ilişkilendirilmiş zaman uyumsuz duruma, çağırılıyorsa yöntem bir `future_error` bir hata koduna sahip `promise_already_satisfied`.

Aksi takdirde, bu işlecini çağıran `INVOKE(fn, args..., Ty)`burada *fn* ilişkili zaman uyumsuz durumu içerisinde saklanan çağrılabilir nesnedir. Tüm döndürülen değeri atomik olarak ilişkili zaman uyumsuz duruma döndürülen sonucu olarak depolanır ve durumunu ayarlamak için hazır. Sonuç olarak, ilişkili aman uyumsuz durumda engellenen iş parçacıklarının engeli kaldırılır.

## <a name="op_bool"></a>  packaged_task::operator bool

Nesne olup olmadığını belirten bir `associated asynchronous state`.

```cpp
operator bool() const noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilişkili zaman uyumsuz durumu; nesne varsa, aksi takdirde, **false**.

## <a name="packaged_task"></a>  packaged_task::packaged_task Oluşturucusu

Oluşturur bir `packaged_task` nesne.

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

*sağ*<br/>
A `packaged_task` nesne.

*Ayırma*<br/>
Bellek ayırıcı Daha fazla bilgi için [ \<ayırıcılar >](../standard-library/allocators-header.md).

*fn*<br/>
Bir işlev nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu yapıları bir `packaged_task` hiçbir nesne *ilişkili zaman uyumsuz durumu*.

İkinci oluşturucu yapıları bir `packaged_task` nesnesini ve ilişkili zaman uyumsuz durumu aktarır *sağ*. İşlemden sonra *sağ* artık bir ilişkili zaman uyumsuz duruma sahip değil.

Üçüncü Oluşturucu yapıları bir `packaged_task` bir kopyasına sahip nesne *fn* , ilişkili zaman uyumsuz durumunda depolanan.

Dördüncü Oluşturucu yapıları bir `packaged_task` bir kopyasına sahip nesne *fn* , ilişkili zaman uyumsuz durumunda depolanan ve kullandığı `alloc` bellek ayırma için.

## <a name="dtorpackaged_task_destructor"></a>  packaged_task:: ~ packaged_task yıkıcısı

Yok eder bir `packaged_task` nesne.

```cpp
~packaged_task();
```

### <a name="remarks"></a>Açıklamalar

Varsa *ilişkili zaman uyumsuz durumu* değil *hazır*, yok edici depoları bir [future_error](../standard-library/future-error-class.md) bir hata koduna sahip bir özel durum `broken_promise` sonucu olarak ilişkili zaman uyumsuz durumu ve engeli ilişkili zaman uyumsuz durumda engellenen tüm iş parçacıkları.

## <a name="reset"></a>  packaged_task::reset

Yeni bir kullanan *ilişkili zaman uyumsuz durumu* ilişkili zaman uyumsuz durumunu değiştirin.

```cpp
void reset();
```

### <a name="remarks"></a>Açıklamalar

Aslında, bu yöntem çalıştırır `*this = packaged_task(move(fn))`burada *fn* bu nesne için ilişkili zaman uyumsuz durumunda depolanan bir işlev nesnesidir. Bu nedenle, bir nesnenin durumu temizlenir, ve [get_future](#get_future), [operator()](#op_call), ve [make_ready_at_thread_exit](#make_ready_at_thread_exit) yeni oluşturulmuş gibi bir nesne üzerinde çağrılabilir.

## <a name="swap"></a>  packaged_task::Swap

İlişkili zaman uyumsuz duruma, belirtilen bir nesnenin ile değiştirir.

```cpp
void swap(packaged_task& Right) noexcept;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
A `packaged_task` nesne.

## <a name="valid"></a>  packaged_task::valid

Nesne olup olmadığını belirten bir `associated asynchronous state`.

```cpp
bool valid() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** ilişkili zaman uyumsuz durumu; nesne varsa, aksi takdirde, **false**.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<gelecek >](../standard-library/future.md)<br/>
