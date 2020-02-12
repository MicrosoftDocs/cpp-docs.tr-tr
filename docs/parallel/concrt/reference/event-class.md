---
title: event Sınıfı
ms.date: 11/04/2016
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
ms.openlocfilehash: 2c72b4b086e932f4fe404259c25f8d2c8be2be31
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138852"
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
|[set](#set)|Olayı bildirir.|
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

## <a name="ctor"></a>olay

Yeni bir olay oluşturur.

```cpp
_CRTIMP event();
```

### <a name="remarks"></a>Açıklamalar

## <a name="dtor"></a>~ olay

Bir olayı yok eder.

```cpp
~event();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çalıştırıldığında olayda bekleyen iş parçacığı olmaması beklenir. Etkinliğin iş parçacıklarıyla sınıfların 'a izin verilmesi, tanımsız davranışa neden olur.

## <a name="reset"></a>döndürmek

Olayı, sinyal olmayan bir duruma sıfırlar.

```cpp
void reset();
```

## <a name="set"></a>kurmak

Olayı bildirir.

```cpp
void set();
```

### <a name="remarks"></a>Açıklamalar

Olayı işaret etmek, olayı bekleyen rastgele sayıda bağlamın çalıştırılabilir hale gelmesine neden olabilir.

## <a name="timeout_infinite"></a>timeout_infinite

Bir bekleme süresinin asla zaman aşımına uğramayacağını gösteren değer.

```cpp
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```

## <a name="wait"></a>bekleneceğini

Olayın sinyal gelmesini bekler.

```cpp
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parametreler

*_Timeout*<br/>
Bekleme süresi geçmeden önce geçen milisaniye sayısını belirtir. Değer `COOPERATIVE_TIMEOUT_INFINITE` zaman aşımı olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bekleme karşılandıysa `0` değeri döndürülür; Aksi takdirde, olayın sinyal verilmeksizin zaman aşımına uğradığını belirtmek için değeri `COOPERATIVE_WAIT_TIMEOUT`.

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, bu çağrı geçerli iş parçacığını engelleyebileceğinden ve uygulamanın yanıt vermemeye başlamasına neden olabileceği için ASTA iş parçacığında `wait` çağırmayın.

## <a name="wait_for_multiple"></a>wait_for_multiple

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
Beklenecek olay dizisi. Dizi içindeki olay sayısı `count` parametresi tarafından belirtilir.

*count*<br/>
`_PPEvents` parametresinde sağlanan dizi içindeki olay sayısı.

*_FWaitAll*<br/>
**True**değerine ayarlanırsa parametresi, `_PPEvents` parametresinde sağlanan dizide bulunan tüm olayların, beklemeyi karşılamak için sinyal getirmeli olduğunu belirtir. **False**değerine ayarlanırsa, `_PPEvents` parametresinde sağlanan dizideki herhangi bir olayın, beklenmesini karşıladığından emin olur.

*_Timeout*<br/>
Bekleme süresi geçmeden önce geçen milisaniye sayısını belirtir. Değer `COOPERATIVE_TIMEOUT_INFINITE` zaman aşımı olmadığını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bekleme karşılandıysa, `_PPEvents` parametresinde sağlanan dizinin içindeki dizin, bekleme koşulunu karşıladı; Aksi takdirde, değer, tatmin edilen koşul olmadan zaman aşımına uğradığını belirtmek için `COOPERATIVE_WAIT_TIMEOUT`.

### <a name="remarks"></a>Açıklamalar

`_FWaitAll` parametresi, beklemeyi karşılamak için tüm olayların işaret edilmesi gerektiğini belirtmek için `true` değer olarak ayarlandıysa, işlev tarafından döndürülen dizin, `COOPERATIVE_WAIT_TIMEOUT`değer olmaması dışında özel bir anlam taşımaz.

> [!IMPORTANT]
> Evrensel Windows Platformu (UWP) uygulamasında, bu çağrı geçerli iş parçacığını engelleyebileceğinden ve uygulamanın yanıt vermemeye başlamasına neden olabileceği için ASTA iş parçacığında `wait_for_multiple` çağırmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
