---
description: 'Hakkında daha fazla bilgi edinin: completion_future sınıfı'
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
ms.openlocfilehash: 8cf252bc29dc85014cb6375eab18de98d6d31646
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247858"
---
# <a name="completion_future-class"></a>completion_future Sınıfı

C++ AMP zaman uyumsuz bir işleme karşılık gelen bir gelecekte temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class completion_future;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[completion_future Oluşturucusu](#ctor)|`completion_future` sınıfının yeni bir örneğini başlatır.|
|[~ completion_future yok edici](#dtor)|Nesneyi yok eder `completion_future` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Al](#get)|İlişkili zaman uyumsuz işlem tamamlanana kadar bekler.|
|[ni](#then)|`completion_future`İlişkili zaman uyumsuz işlem yürütmeyi bitirdiğinde yürütülecek nesneye bir geri çağırma işlevi nesnesi zincirler.|
|[to_task](#to_task)|`task`İlişkili zaman uyumsuz işleme karşılık gelen bir nesne döndürür.|
|[geçerli](#valid)|Nesnenin zaman uyumsuz bir işlemle ilişkili olup olmadığını gösteren bir Boole değeri alır.|
|[bekleneceğini](#wait)|İlişkili zaman uyumsuz işlem tamamlanana kadar engeller.|
|[wait_for](#wait_for)|İlişkili zaman uyumsuz işlem tamamlanana veya tarafından belirtilen saatin süresi geçene kadar engeller `_Rel_time` .|
|[wait_until](#wait_until)|İlişkili zaman uyumsuz işlem tamamlanana veya geçerli saat tarafından belirtilen değeri aşana kadar engeller `_Abs_time` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç std:: shared_future\<void>](#operator_shared_future)|Nesneyi örtük olarak nesnesine dönüştürür `completion_future` `std::shared_future` .|
|[işleç =](#operator_eq)|Belirtilen `completion_future` nesnenin içeriğini buna kopyalar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`completion_future`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amprt. h

**Ad alanı:** eşzamanlılık

## <a name="completion_future"></a><a name="ctor"></a> completion_future

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
`completion_future`Kopyalanacak veya taşınacak nesne.

### <a name="overloads-list"></a>Aşırı yükleme listesi

|Ad|Açıklama|
|----------|-----------------|
|`completion_future();`|Sınıfının yeni bir örneğini başlatır `completion_future`|
|`completion_future(const completion_future& _Other);`|`completion_future`Bir oluşturucuyu kopyalayarak sınıfının yeni bir örneğini başlatır.|
|`completion_future(completion_future&& _Other);`|`completion_future`Bir oluşturucuyu taşıyarak sınıfın yeni bir örneğini başlatır.|

## <a name="get"></a><a name="get"></a> Al

İlişkili zaman uyumsuz işlem tamamlanana kadar bekler. Zaman uyumsuz işlem sırasında bir tane ile karşılaşılırsa saklı özel durumu oluşturur.

### <a name="syntax"></a>Syntax

```cpp
void get() const;
```

## <a name="operator-stdshared_futurevoid"></a><a name="operator_shared_future"></a> işleç std:: shared_future\<void>

Nesneyi örtük olarak nesnesine dönüştürür `completion_future` `std::shared_future` .

### <a name="syntax"></a>Syntax

```cpp
operator std::shared_future<void>() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `std::shared_future` nesnesi.

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Belirtilen `completion_future` nesnenin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
completion_future&  operator= (const completion_future& _Other );
completion_future&  operator= (completion_future&& _Other );
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu nesneye bir başvuru `completion_future` .

## <a name="overloads-list"></a>Aşırı yükleme listesi

|Ad|Açıklama|
|----------|-----------------|
|`completion_future& operator=(const completion_future& _Other);`|`completion_future`Bir derin kopya kullanarak, belirtilen nesnenin içeriğini buna kopyalar.|
|`completion_future& operator=(completion_future&& _Other);`|Belirtilen `completion_future` nesnenin içeriğini bir taşıma ataması kullanarak buna kopyalar.|

## <a name="then"></a><a name="then"></a> ni

`completion_future`İlişkili zaman uyumsuz işlem yürütmeyi bitirdiğinde yürütülecek nesneye bir geri çağırma işlevi nesnesi zincirler.

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

## <a name="to_task"></a><a name="to_task"></a> to_task

`task`İlişkili zaman uyumsuz işleme karşılık gelen bir nesne döndürür.

### <a name="syntax"></a>Syntax

```cpp
concurrency::task<void> to_task() const;
```

### <a name="return-value"></a>Dönüş Değeri

`task`İlişkili zaman uyumsuz işleme karşılık gelen bir nesne.

## <a name="valid"></a><a name="valid"></a> geçerli

Nesnenin zaman uyumsuz bir işlemle ilişkili olup olmadığını gösteren bir Boole değeri alır.

### <a name="syntax"></a>Syntax

```cpp
bool valid() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** nesne bir zaman uyumsuz işlemle ilişkiliyse; Aksi takdirde, **`false`** .

## <a name="wait"></a><a name="wait"></a> bekleneceğini

İlişkili zaman uyumsuz işlem tamamlanana kadar engeller.

### <a name="syntax"></a>Syntax

```cpp
void wait() const;
```

## <a name="wait_for"></a><a name="wait_for"></a> wait_for

İlişkili zaman uyumsuz işlem tamamlanana kadar veya tarafından belirtilen süre `_Rel_time` geçtiğinde engeller.

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

Şunu döndürür:

- `std::future_status::deferred` ilişkili zaman uyumsuz işlem çalışmıyorsa.

- `std::future_status::ready` ilişkili zaman uyumsuz işlem tamamlanmıştır.

- `std::future_status::timeout` belirtilen zaman aralığı geçtiğinde.

## <a name="wait_until"></a><a name="wait_until"></a> wait_until

İlişkili zaman uyumsuz işlem tamamlanana veya geçerli saat tarafından belirtilen değeri aşana kadar engeller `_Abs_time` .

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
İşlevin başlangıcından bu yana olan zaman aralığı `_Clock` , sonra işlevin zaman aşımına uğrar.

*_Abs_time*<br/>
İşlevin daha sonra zaman aşımına uğrar olan nokta.

### <a name="return-value"></a>Dönüş Değeri

Şunu döndürür:

1. `std::future_status::deferred` ilişkili zaman uyumsuz işlem çalışmıyorsa.

1. `std::future_status::ready` ilişkili zaman uyumsuz işlem tamamlanmıştır.

1. `std::future_status::timeout` belirtilen zaman aralığı geçtiğinde.

## <a name="completion_future"></a><a name="dtor"></a> ~ completion_future

Nesneyi yok eder `completion_future` .

### <a name="syntax"></a>Syntax

```cpp
~completion_future();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
