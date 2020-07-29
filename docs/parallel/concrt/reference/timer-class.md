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
ms.openlocfilehash: 026aef03bb813585decb206c1691835330a4dd05
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224948"
---
# <a name="timer-class"></a>süreölçer Sınıfı

`timer`İleti bloğu, belirli `source_block` bir süre geçtikten sonra veya belirli aralıklarla hedefine bir ileti gönderebilen tek hedeftir.

## <a name="syntax"></a>Söz dizimi

```cpp
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bu bloktaki çıkış iletilerinin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[görevine](#ctor)|Fazla Yüklendi. Belirtilen bir `timer` aralıktan sonra belirli bir iletiyi tetikleyen bir mesajlaşma bloğu oluşturur.|
|[~ süreölçer yok edici](#dtor)|Bir `timer` mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[tamazsınız](#pause)|`timer`Mesajlaşma bloğunu sonlandırır. Yinelenen `timer` mesajlaşma bloğu ise, sonraki bir çağrıyla yeniden başlatılabilir `start()` . Yinelenmeyen zamanlayıcılar için, çağrı ile aynı etkiye sahiptir `stop` .|
|[start](#start)|`timer`Mesajlaşma bloğunu başlatır. Bu çağrıldıktan sonra belirtilen milisaniye sayısı, belirtilen değer aşağı akış olarak dağıtılır `message` .|
|[durdurulması](#stop)|`timer`Mesajlaşma bloğunu sonlandırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `timer` ve sahipliği çağırana aktarmakta.|
|[consume_message](#consume_message)|, Hedef tarafından daha önce sunulan ve ayrılmış bir ileti tüketir `timer` ve sahipliği çağırana aktarmıştır.|
|[link_target_notification](#link_target_notification)|Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `timer` .|
|[propagate_to_any_targets](#propagate_to_any_targets)|, Blok tarafından oluşturulan iletiyi `timer` tüm bağlantılı hedeflere sunmaya çalışır.|
|[release_message](#release_message)|Önceki bir ileti ayırmasını yayınlar. (Geçersiz kılmalar [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `timer` . (Geçersiz kılmalar [source_block:: reserve_message](source-block-class.md#reserve_message).)|
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

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

Bu mesajlaşma bloğu tarafından sunulan bir iletiyi kabul eder `timer` ve sahipliği çağırana aktarmakta.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

, Hedef tarafından daha önce sunulan ve ayrılmış bir ileti tüketir `timer` ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Tüketilmekte olan nesne.

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept`,, Ancak, ' a benzer ancak her zaman öğesine yapılan bir çağrıdır `reserve` .

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

Bu mesajlaşma bloğuna yeni bir hedef bağlandığını bildiren bir geri çağırma `timer` .

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Yeni bağlantılı hedefe yönelik bir işaretçi.

## <a name="pause"></a><a name="pause"></a>tamazsınız

`timer`Mesajlaşma bloğunu sonlandırır. Yinelenen `timer` mesajlaşma bloğu ise, sonraki bir çağrıyla yeniden başlatılabilir `start()` . Yinelenmeyen zamanlayıcılar için, çağrı ile aynı etkiye sahiptir `stop` .

```cpp
void pause();
```

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

, Blok tarafından oluşturulan iletiyi `timer` tüm bağlantılı hedeflere sunmaya çalışır.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```

## <a name="release_message"></a><a name="release_message"></a>release_message

Önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Serbest bırakılmakta olan nesne.

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `timer` .

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Ayrılan nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** ileti başarıyla ayrıldıysa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Çağrıldıktan sonra `reserve` , döndürürse, **`true`** `consume` `release` iletinin sahipliğini almak ya da serbest bırakmak için ya da çağrılması gerekir.

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

Bir ayırma yayımlandıktan sonra yayılmaya devam eder.

```cpp
virtual void resume_propagation();
```

## <a name="start"></a><a name="start"></a>başından

`timer`Mesajlaşma bloğunu başlatır. Bu çağrıldıktan sonra belirtilen milisaniye sayısı, belirtilen değer aşağı akış olarak dağıtılır `message` .

```cpp
void start();
```

## <a name="stop"></a><a name="stop"></a>durdurulması

`timer`Mesajlaşma bloğunu sonlandırır.

```cpp
void stop();
```

## <a name="timer"></a><a name="ctor"></a>görevine

Belirtilen bir `timer` aralıktan sonra belirli bir iletiyi tetikleyen bir mesajlaşma bloğu oluşturur.

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

*deeri*<br/>
Zamanlayıcı geçtiğinde aşağı akış yayılacağı değer.

*_PTarget*<br/>
Süreölçerinin iletiyi yayalacak hedef.

*_Repeating*<br/>
Doğru ise, zamanlayıcının her milisaniyede düzenli olarak tetikleneceği anlamına gelir `_Ms` .

*_Scheduler*<br/>
`Scheduler` `timer` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne zamanlandı.

*_ScheduleGroup*<br/>
`ScheduleGroup` `timer` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

Veya parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır `_Scheduler` `_ScheduleGroup` .

## <a name="timer"></a><a name="dtor"></a>~ Zamanlayıcı

Bir `timer` mesajlaşma bloğunu yok eder.

```cpp
~timer();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
