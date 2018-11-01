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
ms.openlocfilehash: beb374efe26c25fed490b7407e087e2cc46043c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659842"
---
# <a name="timer-class"></a>süreölçer Sınıfı

A `timer` ileti bloğu tek hedef `source_block` gönderebilen bir ileti hedefine belirtilen süre geçtikten sonra veya belirli aralıklarla.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Bu çıktı iletilerini yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Zamanlayıcı](#ctor)|Fazla Yüklendi. Oluşturur bir `timer` belirli bir ileti belirtilen bir süre sonra ateşlenir ileti bloğu.|
|[~ timer yok Edicisi](#dtor)|Yok eder bir `timer` ileti bloğu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Duraklat](#pause)|Durakları `timer` ileti bloğu. Yinelenen ise `timer` blok Mesajlaşma, bir sonraki başlatılmadan `start()` çağırın. Yinelenmeyen için zamanlayıcıları, bu aynı etkiye sahiptir olarak bir `stop` çağırın.|
|[Başlangıç](#start)|Başlar `timer` ileti bloğu. Belirtilen sayıda milisaniye sonra bu çağrılır, belirtilen değeri yayılan aşağı akış olarak bir `message`.|
|[Durdur](#stop)|Durakları `timer` ileti bloğu.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu tarafından sunulan bir iletiyi kabul `timer` çağırana sahipliğini aktarma ileti bloğu.|
|[consume_message](#consume_message)|Daha önce tarafından sunulan iletiyi tüketir `timer` ve çağırana sahipliğini aktarma hedefi tarafından ayrılmış.|
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `timer` ileti bloğu.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Tarafından üretilen ileti sunmaya çalışır `timer` bağlantılı hedeflere tüm blok.|
|[release_message](#release_message)|Bir önceki ileti ayırma serbest bırakır. (Geçersiz kılmaları [source_block::release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `timer` ileti bloğu. (Geçersiz kılmaları [source_block::reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Rezervasyon piyasaya sürüldükten sonra yayma sürdürür. (Geçersiz kılmaları [source_block::resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept_message"></a> accept_message

Bu tarafından sunulan bir iletiyi kabul `timer` çağırana sahipliğini aktarma ileti bloğu.

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

##  <a name="consume_message"></a> consume_message

Daha önce tarafından sunulan iletiyi tüketir `timer` ve çağırana sahipliğini aktarma hedefi tarafından ayrılmış.

```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

Benzer şekilde `accept`, ancak her zaman bir çağrı tarafından öncesinde `reserve`.

##  <a name="link_target_notification"></a> link_target_notification

Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `timer` ileti bloğu.

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefi için bir işaretçi.

##  <a name="pause"></a> Duraklat

Durakları `timer` ileti bloğu. Yinelenen ise `timer` blok Mesajlaşma, bir sonraki başlatılmadan `start()` çağırın. Yinelenmeyen için zamanlayıcıları, bu aynı etkiye sahiptir olarak bir `stop` çağırın.

```
void pause();
```

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

Tarafından üretilen ileti sunmaya çalışır `timer` bağlantılı hedeflere tüm blok.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```

##  <a name="release_message"></a> release_message

Bir önceki ileti ayırma serbest bırakır.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Yayımlanan nesne.

##  <a name="reserve_message"></a> reserve_message

Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `timer` ileti bloğu.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Ayrılan nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ileti başarıyla ayrıldı, **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sonra `reserve` çağrılır, döndürürse **true**, ya da `consume` veya `release` alın veya iletinin sahipliğini serbest bırakmak için çağrılmalıdır.

##  <a name="resume_propagation"></a> resume_propagation

Rezervasyon piyasaya sürüldükten sonra yayma sürdürür.

```
virtual void resume_propagation();
```

##  <a name="start"></a> Başlangıç

Başlar `timer` ileti bloğu. Belirtilen sayıda milisaniye sonra bu çağrılır, belirtilen değeri yayılan aşağı akış olarak bir `message`.

```
void start();
```

##  <a name="stop"></a> Durdur

Durakları `timer` ileti bloğu.

```
void stop();
```

##  <a name="ctor"></a> Zamanlayıcı

Oluşturur bir `timer` belirli bir ileti belirtilen bir süre sonra ateşlenir ileti bloğu.

```
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
Başlamak için aşağı yönde dağıtılmasını belirtilen iletiyi çağrısından sonra geçmesi gereken milisaniye sayısını.

*value*<br/>
Zamanlayıcı sona erdiğinde aşağı yönde aktarılacaktır değeri.

*_PTarget*<br/>
Hedef için Zamanlayıcıyı iletisini yayılır.

*_Repeating*<br/>
TRUE ise, Zamanlayıcıyı düzenli aralıklarla ateşlenir gösterir. her `_Ms` milisaniye.

*_Scheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `timer` ileti bloğu zamanlandığı zamanlandı.

*_ScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `timer` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_Scheduler` veya `_ScheduleGroup` parametreleri.

##  <a name="dtor"></a> ~ timer

Yok eder bir `timer` ileti bloğu.

```
~timer();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
