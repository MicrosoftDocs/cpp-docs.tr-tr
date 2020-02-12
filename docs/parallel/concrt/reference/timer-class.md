---
title: süreölçer Sınıfı
ms.date: 11/04/2016
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
ms.openlocfilehash: c39afc565a7ec775600b9c9fb6f15a89acdef57b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142525"
---
# <a name="timer-class"></a>süreölçer Sınıfı

`timer` mesajlaşma bloğu, belirli bir süre geçtikten sonra veya belirli aralıklarla hedefine bir ileti gönderebilen tek hedef `source_block`.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Bu bloktaki çıkış iletilerinin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[görevine](#ctor)|Fazla Yüklendi. Belirtilen bir aralıktan sonra belirli bir iletiyi tetikleyen `timer` mesajlaşma bloğu oluşturur.|
|[~ süreölçer yok edici](#dtor)|`timer` mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[tamazsınız](#pause)|`timer` mesajlaşma bloğunu sonlandırır. Yinelenen bir `timer` mesajlaşma bloğu ise, sonraki bir `start()` çağrısıyla yeniden başlatılabilir. Yinelenmeyen zamanlayıcılar için, `stop` çağrısıyla aynı etkiye sahiptir.|
|[start](#start)|`timer` mesajlaşma bloğunu başlatır. Bu çağrıldıktan sonra belirtilen milisaniye sayısı, belirtilen değer aşağı akış `message`olarak yayılır.|
|[durdurulması](#stop)|`timer` mesajlaşma bloğunu sonlandırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu `timer` mesajlaşma bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[consume_message](#consume_message)|, `timer` tarafından daha önce sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve sahipliği çağırana aktarmıştır.|
|[link_target_notification](#link_target_notification)|Yeni bir hedefin bu `timer` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.|
|[propagate_to_any_targets](#propagate_to_any_targets)|`timer` bloğu tarafından oluşturulan iletiyi tüm bağlantılı hedeflere sunmaya çalışır.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu `timer` mesajlaşma bloğunun sunduğu bir iletiyi ayırır. (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Bir ayırma yayımlandıktan sonra yayılmaya devam eder. (Geçersiz kılmalar [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept_message"></a>accept_message

Bu `timer` mesajlaşma bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

## <a name="consume_message"></a>consume_message

, `timer` tarafından daha önce sunulan ve hedef tarafından ayrılmış bir ileti tüketir ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Tüketilmekte olan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`benzerdir, ancak her zaman bir `reserve`çağrısıyla yapılır.

## <a name="link_target_notification"></a>link_target_notification

Yeni bir hedefin bu `timer` mesajlaşma bloğuna bağlandığını bildiren bir geri çağırma.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefe yönelik bir işaretçi.

## <a name="pause"></a>tamazsınız

`timer` mesajlaşma bloğunu sonlandırır. Yinelenen bir `timer` mesajlaşma bloğu ise, sonraki bir `start()` çağrısıyla yeniden başlatılabilir. Yinelenmeyen zamanlayıcılar için, `stop` çağrısıyla aynı etkiye sahiptir.

```cpp
void pause();
```

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

`timer` bloğu tarafından oluşturulan iletiyi tüm bağlantılı hedeflere sunmaya çalışır.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```

## <a name="release_message"></a>release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Yayımlanmakta olan `message` nesnesinin `runtime_object_identity`.

## <a name="reserve_message"></a>reserve_message

Daha önce bu `timer` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

ileti başarıyla ayrıldıysa **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

`reserve` çağrıldıktan sonra, **doğru**döndürürse, iletinin sahipliğini almak ya da serbest bırakmak için `consume` veya `release` çağrılmalıdır.

## <a name="resume_propagation"></a>resume_propagation

Bir ayırma yayımlandıktan sonra yayılmaya devam eder.

```cpp
virtual void resume_propagation();
```

## <a name="start"></a>başından

`timer` mesajlaşma bloğunu başlatır. Bu çağrıldıktan sonra belirtilen milisaniye sayısı, belirtilen değer aşağı akış `message`olarak yayılır.

```cpp
void start();
```

## <a name="stop"></a>durdurulması

`timer` mesajlaşma bloğunu sonlandırır.

```cpp
void stop();
```

## <a name="ctor"></a>görevine

Belirtilen bir aralıktan sonra belirli bir iletiyi tetikleyen `timer` mesajlaşma bloğu oluşturur.

```cpp
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```

### <a name="parameters"></a>Parametreler

*_Ms*<br/>
Belirtilen ileti için başlangıç çağrısının aşağı akış olarak yayılması için geçmesi gereken milisaniye sayısı.

*value*<br/>
Zamanlayıcı geçtiğinde aşağı akış yayılacağı değer.

*_PTarget*<br/>
Süreölçerinin iletiyi yayalacak hedef.

*_Repeating*<br/>
Doğru ise, zamanlayıcının her `_Ms` milisaniyede düzenli olarak tetikleneceği anlamına gelir.

*_Scheduler*<br/>
`timer` mesajlaşma bloğunun yayma görevinin zamanlandığı `Scheduler` nesnesi zamanlandı.

*_ScheduleGroup*<br/>
`timer` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

`_Scheduler` veya `_ScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

## <a name="dtor"></a>~ Zamanlayıcı

`timer` mesajlaşma bloğunu yok eder.

```cpp
~timer();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
