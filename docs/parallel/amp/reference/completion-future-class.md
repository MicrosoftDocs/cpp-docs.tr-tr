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
ms.openlocfilehash: 663122c2d8cd430e921773e75dfd7975e4a41516
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272925"
---
# <a name="completionfuture-class"></a>completion_future Sınıfı

Gelecekteki karşılık gelen bir C++ AMP zaman uyumsuz işlemi temsil eder.

### <a name="syntax"></a>Sözdizimi

```
class completion_future;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[completion_future Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `completion_future` sınıfı.|
|[~ completion_future yok Edicisi](#dtor)|Yok eder `completion_future` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[get](#get)|İlişkili zaman uyumsuz işlem tamamlanana kadar bekler.|
|[Ardından](#then)|Bir geri çağırma işlevi nesnesine zincir `completion_future` ilişkili zaman uyumsuz işlemin yürütülmesi tamamlandığında yürütülecek nesne.|
|[to_task](#to_task)|Döndürür bir `task` nesnesini ilişkili asenkron işleme karşı.|
|[valid](#valid)|Nesnenin bir zaman uyumsuz işlemle ilişkili olup olmadığını gösteren bir Boole değeri alır.|
|[bekleme](#wait)|İlişkili zaman uyumsuz işlem tamamlanıncaya kadar engeller.|
|[wait_for](#wait_for)|İlişkili zaman uyumsuz işlem tamamlanıncaya kadar engeller ya da tarafından belirlenen süre `_Rel_time` geçti.|
|[wait_until](#wait_until)|İlişkili zaman uyumsuz işlem tamamlanıncaya kadar veya geçerli saati tarafından belirtilen değeri aşana kadar engeller `_Abs_time`.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç std::shared_future\<void >](#operator_shared_future)|Örtük olarak dönüştürür `completion_future` nesnesini bir `std::shared_future` nesne.|
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `completion_future` bu nesne içine.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`completion_future`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amprt.h

**Namespace:** eşzamanlılık

## <a name="ctor"></a> completion_future

Yeni bir örneğini başlatır `completion_future` sınıfı.

### <a name="syntax"></a>Sözdizimi

```
completion_future();

completion_future(
    const completion_future& _Other );

completion_future(
    completion_future&& _Other );
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`completion_future` Kopyalamak veya taşımak için nesne.

### <a name="overloads-list"></a>Aşırı yükler listesi

|Ad|Açıklama|
|----------|-----------------|
|`completion_future();`|Yeni bir örneğini başlatır `completion_future` sınıfı|
|`completion_future(const completion_future& _Other);`|Yeni bir örneğini başlatır `completion_future` bir oluşturucu kopyalayarak sınıfı.|
|`completion_future(completion_future&& _Other);`|Yeni bir örneğini başlatır `completion_future` bir oluşturucu taşıyarak sınıfı.|

## <a name="get"></a> Al

İlişkili zaman uyumsuz işlem tamamlanana kadar bekler. Bir zaman uyumsuz işlemi sırasında karşılaşılan depolanan özel durum oluşturur.

### <a name="syntax"></a>Sözdizimi

```
void get() const;
```

## <a name="operator_shared_future"></a> işleç std::shared_future<void>

Örtük olarak dönüştürür `completion_future` nesnesini bir `std::shared_future` nesne.

### <a name="syntax"></a>Sözdizimi

```
operator std::shared_future<void>() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `std::shared_future` nesne.

## <a name="operator_eq"></a> işleç =

Belirtilen içeriğini kopyalar `completion_future` bu nesne içine.

### <a name="syntax"></a>Sözdizimi

```
completion_future&  operator= (const completion_future& _Other );
completion_future&  operator= (completion_future&& _Other );
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `completion_future` nesne.

## <a name="overloads-list"></a>Aşırı yükler listesi

|Ad|Açıklama|
|----------|-----------------|
|`completion_future& operator=(const completion_future& _Other);`|Belirtilen içeriğini kopyalar `completion_future` içine derin kopya kullanarak bu nesne.|
|`completion_future& operator=(completion_future&& _Other);`|Belirtilen içeriğini kopyalar `completion_future` içine bir taşıma ataması kullanarak bu nesne.|

## <a name="then"></a> Ardından

Bir geri çağırma işlevi nesnesine zincir `completion_future` ilişkili zaman uyumsuz işlemin yürütülmesi tamamlandığında yürütülecek nesne.

### <a name="syntax"></a>Sözdizimi

```
template <typename _Functor>
void then(const _Functor & _Func ) const;
```

### <a name="parameters"></a>Parametreler

*_Functor*<br/>
İşlev nesnesini geri çağırma.

*_Func*<br/>
Geri çağırma işlevi nesnesi.

## <a name="to_task"></a> to_task

Döndürür bir `task` nesnesini ilişkili asenkron işleme karşı.

### <a name="syntax"></a>Sözdizimi

```
concurrency::task<void> to_task() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `task` nesnesini ilişkili asenkron işleme karşı.

## <a name="valid"></a> Geçerli

Nesnenin bir zaman uyumsuz işlemle ilişkili olup olmadığını gösteren bir Boole değeri alır.

### <a name="syntax"></a>Sözdizimi

```
bool valid() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesne ise, bir zaman uyumsuz işlemle ilişkili; Aksi takdirde **false**.

## <a name="wait"></a> bekleme

İlişkili zaman uyumsuz işlem tamamlanıncaya kadar engeller.

### <a name="syntax"></a>Sözdizimi

```
void wait() const;
```

## <a name="wait_for"></a> wait_for

İlişkili zaman uyumsuz işlem tamamlanıncaya kadar engeller veya tarafından belirtilen zaman `_Rel_time` geçti.

### <a name="syntax"></a>Sözdizimi

```
template <
    class _Rep,
    class _Period
>
std::future_status::future_status wait_for(
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;
```

### <a name="parameters"></a>Parametreler

*_Rep*<br/>
İşaret sayısını gösteren aritmetik türü.

*_Period*<br/>
Değer çizgisi beklenecek saniye sayısını gösteren std::ratio.

*_Rel_time*<br/>
En fazla işlemin tamamlanması için beklenecek süre miktarı.

### <a name="return-value"></a>Dönüş Değeri

döndürür:

- `std::future_status::deferred` ilişkili zaman uyumsuz işlem çalışmıyorsa.

- `std::future_status::ready` ilişkili zaman uyumsuz işlem tamamlandıysa.

- `std::future_status::timeout` Belirtilen süre dolduysa durumunda.

## <a name="wait_until"></a> wait_until

İlişkili zaman uyumsuz işlem tamamlanıncaya kadar veya geçerli saati tarafından belirtilen değeri aşana kadar engeller `_Abs_time`.

### <a name="syntax"></a>Sözdizimi

```
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
Zaman aralığı başladığından bu yana `_Clock`'s dönem, işlev sonra zaman aşımına gösterir.

*_Abs_time*<br/>
Sonrasında işlevin zaman aşımına uğrayacağı zaman içinde nokta.

### <a name="return-value"></a>Dönüş Değeri

döndürür:

1. `std::future_status::deferred` ilişkili zaman uyumsuz işlem çalışmıyorsa.

1. `std::future_status::ready` ilişkili zaman uyumsuz işlem tamamlandıysa.

1. `std::future_status::timeout` Eğer belirtilen süre geçti.

## <a name="dtor"></a> ~ completion_future

Yok eder `completion_future` nesne.

### <a name="syntax"></a>Sözdizimi

```
~completion_future();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
