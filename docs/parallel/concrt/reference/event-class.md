---
title: event Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
ms.openlocfilehash: 3f2ec71083f7a7905bad5cda014baba914e31e79
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215809"
---
# <a name="event-class"></a>event Sınıfı

Eşzamanlılık Çalışma Zamanı açıkça farkında olan el ile sıfırlama olayı.

## <a name="syntax"></a>Sözdizimi

```cpp
class event;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ olay yıkıcısı](#dtor)|Bir olayı yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[döndürmek](#reset)|Olayı, sinyal olmayan bir duruma sıfırlar.|
|[kurmak](#set)|Olayı bildirir.|
|[bekleneceğini](#wait)|Olayın sinyal gelmesini bekler.|
|[wait_for_multiple](#wait_for_multiple)|Birden çok olayın sinyal gelmesini bekler.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[timeout_infinite](#timeout_infinite)|Bir bekleme süresinin asla zaman aşımına uğramayacağını gösteren değer.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [eşitleme veri yapıları](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`event`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="event"></a><a name="ctor"></a>olay

Yeni bir olay oluşturur.

```cpp
_CRTIMP event();
```

### <a name="remarks"></a>Açıklamalar

## <a name="event"></a><a name="dtor"></a>~ olay

Bir olayı yok eder.

```cpp
~event();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında olayda bekleyen iş parçacığı olmaması beklenir. Etkinliğin iş parçacıklarıyla sınıfların 'a izin verilmesi, tanımsız davranışa neden olur.

## <a name="reset"></a><a name="reset"></a>döndürmek

Olayı, sinyal olmayan bir duruma sıfırlar.

```cpp
void reset();
```

## <a name="set"></a><a name="set"></a>kurmak

Olayı bildirir.

```cpp
void set();
```

### <a name="remarks"></a>Açıklamalar

Olayı işaret etmek, olayı bekleyen rastgele sayıda bağlamın çalıştırılabilir hale gelmesine neden olabilir.

## <a name="timeout_infinite"></a><a name="timeout_infinite"></a>timeout_infinite

Bir bekleme süresinin asla zaman aşımına uğramayacağını gösteren değer.

```cpp
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```

## <a name="wait"></a><a name="wait"></a>bekleneceğini

Olayın sinyal gelmesini bekler.

```cpp
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parametreler

*_Timeout*<br/>
Bekleme süresi geçmeden önce geçen milisaniye sayısını belirtir. Değer, `COOPERATIVE_TIMEOUT_INFINITE` zaman aşımı olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bekleme karşılandıysa, değer `0` döndürülür; Aksi takdirde, `COOPERATIVE_WAIT_TIMEOUT` olayın sinyal verilmeksizin zaman aşımına uğradığını belirten değer.

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, `wait` Bu çağrı geçerli iş parçacığını engelleyebileceğinden ve uygulamanın yanıt vermemeye başlamasına neden olabileceği IÇIN ASTA iş parçacığı üzerinde çağırmayın.

## <a name="wait_for_multiple"></a><a name="wait_for_multiple"></a>wait_for_multiple

Birden çok olayın sinyal gelmesini bekler.

```cpp
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parametreler

*_PPEvents*<br/>
Beklenecek olay dizisi. Dizi içindeki olay sayısı, `count` parametresiyle belirtilir.

*biriktirme*<br/>
Parametresinde sağlanan dizi içindeki olay sayısı `_PPEvents` .

*_FWaitAll*<br/>
Değer olarak ayarlanırsa parametresi, **`true`** parametre içinde sağlanan dizideki tüm olayların, `_PPEvents` beklemeyi karşılamak için sinyal getirmeli olduğunu belirtir. Değer olarak ayarlanırsa **`false`** , parametre içinde sağlanan dizideki herhangi bir olayın, `_PPEvents` beklenecektir.

*_Timeout*<br/>
Bekleme süresi geçmeden önce geçen milisaniye sayısını belirtir. Değer, `COOPERATIVE_TIMEOUT_INFINITE` zaman aşımı olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bekleme karşılandıysa, parametre içinde bekleme koşulunu karşılamakta olan dizinin içindeki dizin `_PPEvents` ; Aksi takdirde, `COOPERATIVE_WAIT_TIMEOUT` bekleme durumu karşılanmadan zaman aşımına uğradığını belirtmek için değeri.

### <a name="remarks"></a>Açıklamalar

Parametresi, `_FWaitAll` **`true`** beklemeyi karşılamak için tüm olayların işaret edilmesi gerektiğini belirtmek üzere değerine ayarlanırsa, işlev tarafından döndürülen dizin, değer olmaması dışında özel bir anlam taşımaz `COOPERATIVE_WAIT_TIMEOUT` .

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, `wait_for_multiple` Bu çağrı geçerli iş parçacığını engelleyebileceğinden ve uygulamanın yanıt vermemeye başlamasına neden olabileceği IÇIN ASTA iş parçacığı üzerinde çağırmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
