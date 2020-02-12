---
title: completion_future Sınıfı
ms.date: 11/04/2016
f1_keywords:
- completion_future
- AMPRT/completion_future
- AMPRT/Concurrency::completion_future::completion_future
- AMPRT/Concurrency::completion_future::get
- AMPRT/Concurrency::completion_future::then
- AMPRT/Concurrency::completion_future::to_task
- AMPRT/Concurrency::completion_future::valid
- AMPRT/Concurrency::completion_future::wait
- AMPRT/Concurrency::completion_future::wait_for
- AMPRT/Concurrency::completion_future::wait_until
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
ms.openlocfilehash: 69aacad02df5290f161e9d8d311be347668be9f9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127026"
---
# <a name="completion_future-class"></a>completion_future Sınıfı

Bir C++ amp zaman uyumsuz işlemine karşılık gelen bir gelecekte temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class completion_future;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[completion_future Oluşturucusu](#ctor)|`completion_future` sınıfının yeni bir örneğini başlatır.|
|[~ completion_future yok edici](#dtor)|`completion_future` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get](#get)|İlişkili zaman uyumsuz işlem tamamlanana kadar bekler.|
|[ni](#then)|İlişkili zaman uyumsuz işlem yürütmeyi bitirdiğinde yürütülecek `completion_future` nesnesine bir geri çağırma işlevi nesnesi zincirler.|
|[to_task](#to_task)|İlişkili zaman uyumsuz işleme karşılık gelen bir `task` nesnesi döndürür.|
|[geçerli](#valid)|Nesnenin zaman uyumsuz bir işlemle ilişkili olup olmadığını gösteren bir Boole değeri alır.|
|[bekleneceğini](#wait)|İlişkili zaman uyumsuz işlem tamamlanana kadar engeller.|
|[wait_for](#wait_for)|İlişkili zaman uyumsuz işlem tamamlanana kadar veya `_Rel_time` tarafından belirtilen süre geçtiğinden engeller.|
|[wait_until](#wait_until)|İlişkili zaman uyumsuz işlem tamamlanana kadar veya geçerli saat `_Abs_time`tarafından belirtilen değeri aşana kadar engeller.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç std:: shared_future\<void >](#operator_shared_future)|`completion_future` nesnesini örtük olarak bir `std::shared_future` nesnesine dönüştürür.|
|[işleç =](#operator_eq)|Belirtilen `completion_future` nesnesinin içeriğini buna kopyalar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`completion_future`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>completion_future

`completion_future` sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
completion_future();

completion_future(
    const completion_future& _Other );

completion_future(
    completion_future&& _Other );
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanacak veya taşınacak nesne `completion_future`.

### <a name="overloads-list"></a>Aşırı yükleme listesi

|Ad|Açıklama|
|----------|-----------------|
|`completion_future();`|`completion_future` sınıfının yeni bir örneğini başlatır|
|`completion_future(const completion_future& _Other);`|Bir oluşturucuyu kopyalayarak `completion_future` sınıfının yeni bir örneğini başlatır.|
|`completion_future(completion_future&& _Other);`|Bir oluşturucuyu taşıyarak `completion_future` sınıfının yeni bir örneğini başlatır.|

## <a name="get"></a>Al

İlişkili zaman uyumsuz işlem tamamlanana kadar bekler. Zaman uyumsuz işlem sırasında bir tane ile karşılaşılırsa saklı özel durumu oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
void get() const;
```

## <a name="operator_shared_future"></a>işleç std:: shared_future\<void >

`completion_future` nesnesini örtük olarak bir `std::shared_future` nesnesine dönüştürür.

### <a name="syntax"></a>Sözdizimi

```cpp
operator std::shared_future<void>() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `std::shared_future` nesnesi.

## <a name="operator_eq"></a>işleç =

Belirtilen `completion_future` nesnesinin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
completion_future&  operator= (const completion_future& _Other );
completion_future&  operator= (completion_future&& _Other );
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu `completion_future` nesnesine bir başvuru.

## <a name="overloads-list"></a>Aşırı yükleme listesi

|Ad|Açıklama|
|----------|-----------------|
|`completion_future& operator=(const completion_future& _Other);`|Ayrıntılı bir kopya kullanarak, belirtilen `completion_future` nesnesinin içeriğini buna kopyalar.|
|`completion_future& operator=(completion_future&& _Other);`|Bir taşıma ataması kullanarak, belirtilen `completion_future` nesnesinin içeriğini buna kopyalar.|

## <a name="then"></a>ni

İlişkili zaman uyumsuz işlem yürütmeyi bitirdiğinde yürütülecek `completion_future` nesnesine bir geri çağırma işlevi nesnesi zincirler.

### <a name="syntax"></a>Sözdizimi

```cpp
template <typename _Functor>
void then(const _Functor & _Func ) const;
```

### <a name="parameters"></a>Parametreler

*_Functor*<br/>
Geri çağırma, functor.

*_Func*<br/>
Geri çağırma işlevi nesnesi.

## <a name="to_task"></a>to_task

İlişkili zaman uyumsuz işleme karşılık gelen bir `task` nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
concurrency::task<void> to_task() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlişkili zaman uyumsuz işleme karşılık gelen bir `task` nesnesi.

## <a name="valid"></a>geçerli

Nesnenin zaman uyumsuz bir işlemle ilişkili olup olmadığını gösteren bir Boole değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool valid() const;
```

### <a name="return-value"></a>Dönüş Değeri

nesne bir zaman uyumsuz işlemle ilişkiliyse **doğru** ; Aksi takdirde, **false**.

## <a name="wait"></a>bekleneceğini

İlişkili zaman uyumsuz işlem tamamlanana kadar engeller.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait() const;
```

## <a name="wait_for"></a>wait_for

İlişkili zaman uyumsuz işlem tamamlanana kadar veya `_Rel_time` tarafından belirtilen süre geçtiğinde engeller.

### <a name="syntax"></a>Sözdizimi

```cpp
template <
    class _Rep,
    class _Period
>
std::future_status::future_status wait_for(
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;
```

### <a name="parameters"></a>Parametreler

*_Rep*<br/>
Onay işareti sayısını temsil eden bir aritmetik tür.

*_Period*<br/>
Değer başına geçecek saniye sayısını temsil eden std:: Ratio.

*_Rel_time*<br/>
İşlemin tamamlanabilmesi için beklenecek en uzun süre.

### <a name="return-value"></a>Dönüş Değeri

Döndürdüğü

- ilişkili zaman uyumsuz işlem çalışmıyorsa `std::future_status::deferred`.

- ilişkili zaman uyumsuz işlem bitirse `std::future_status::ready`.

- belirtilen zaman aralığı geçtiğinde `std::future_status::timeout`.

## <a name="wait_until"></a>wait_until

İlişkili zaman uyumsuz işlem tamamlanana kadar veya geçerli saat `_Abs_time`tarafından belirtilen değeri aşana kadar engeller.

### <a name="syntax"></a>Sözdizimi

```cpp
template <
    class _Clock,
    class _Duration
>
std::future_status::future_status wait_until(
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;
```

### <a name="parameters"></a>Parametreler

*_Clock*<br/>
Bu zaman noktasının ölçüldüğü saat.

*_Duration*<br/>
`_Clock`dönemi başlangıcından bu yana olan zaman aralığı, sonra işlevin zaman aşımına uğrar.

*_Abs_time*<br/>
İşlevin daha sonra zaman aşımına uğrar olan nokta.

### <a name="return-value"></a>Dönüş Değeri

Döndürdüğü

1. ilişkili zaman uyumsuz işlem çalışmıyorsa `std::future_status::deferred`.

1. ilişkili zaman uyumsuz işlem bitirse `std::future_status::ready`.

1. belirtilen zaman aralığı geçtiğinde `std::future_status::timeout`.

## <a name="dtor"></a>~ completion_future

`completion_future` nesnesini yok eder.

### <a name="syntax"></a>Sözdizimi

```cpp
~completion_future();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
