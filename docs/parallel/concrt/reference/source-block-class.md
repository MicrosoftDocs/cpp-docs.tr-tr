---
title: source_block Sınıfı
ms.date: 11/04/2016
f1_keywords:
- source_block
- AGENTS/concurrency::source_block
- AGENTS/concurrency::source_block::source_block
- AGENTS/concurrency::source_block::accept
- AGENTS/concurrency::source_block::acquire_ref
- AGENTS/concurrency::source_block::consume
- AGENTS/concurrency::source_block::link_target
- AGENTS/concurrency::source_block::release
- AGENTS/concurrency::source_block::release_ref
- AGENTS/concurrency::source_block::reserve
- AGENTS/concurrency::source_block::unlink_target
- AGENTS/concurrency::source_block::unlink_targets
- AGENTS/concurrency::source_block::accept_message
- AGENTS/concurrency::source_block::async_send
- AGENTS/concurrency::source_block::consume_message
- AGENTS/concurrency::source_block::enable_batched_processing
- AGENTS/concurrency::source_block::initialize_source
- AGENTS/concurrency::source_block::link_target_notification
- AGENTS/concurrency::source_block::process_input_messages
- AGENTS/concurrency::source_block::propagate_output_messages
- AGENTS/concurrency::source_block::propagate_to_any_targets
- AGENTS/concurrency::source_block::release_message
- AGENTS/concurrency::source_block::remove_targets
- AGENTS/concurrency::source_block::reserve_message
- AGENTS/concurrency::source_block::resume_propagation
- AGENTS/concurrency::source_block::sync_send
- AGENTS/concurrency::source_block::unlink_target_notification
- AGENTS/concurrency::source_block::wait_for_outstanding_async_sends
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
ms.openlocfilehash: 304bc65d969fa677d67bf578021a63f628e0a1f5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228446"
---
# <a name="source_block-class"></a>source_block Sınıfı

`source_block`Sınıfı, yalnızca kaynak blokları için soyut bir temel sınıftır. Sınıfı, temel bağlantı yönetimi işlevlerinin yanı sıra ortak hata denetimleri sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```

### <a name="parameters"></a>Parametreler

*_TargetLinkRegistry*<br/>
Hedef bağlantıları tutmak için kullanılacak bağlantı kayıt defteri.

*_MessageProcessorType*<br/>
İleti işleme için işlemci türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`target_iterator`|Bağlı hedeflere kılavuzluk eden Yineleyici.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[source_block](#ctor)|Bir `source_block` nesnesi oluşturur.|
|[~ source_block yok edici](#dtor)|Nesneyi yok eder `source_block` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ettiğinizde](#accept)|Bu nesne tarafından sunulan `source_block` ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[acquire_ref](#acquire_ref)|Silmeyi engellemek için bu nesnede bir başvuru sayısı alır `source_block` .|
|[kullanan](#consume)|Bu nesne tarafından daha önce sunulan `source_block` ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.|
|[link_target](#link_target)|Bu nesneye bir hedef blok bağlar `source_block` .|
|[Yayın](#release)|Önceki başarılı bir ileti ayırmasını serbest bırakır.|
|[release_ref](#release_ref)|Bu nesnede bir başvuru sayısı yayınlar `source_block` .|
|[Rezerve et](#reserve)|Bu nesne tarafından daha önce sunulan bir iletiyi ayırır `source_block` .|
|[unlink_target](#unlink_target)|Bu nesneden bir hedef bloğunun bağlantısını kaldırır `source_block` .|
|[unlink_targets](#unlink_targets)|Bu nesneden tüm hedef blokların bağlantılarını Kaldır `source_block` . ( [ISource:: unlink_targets](isource-class.md#unlink_targets)geçersiz kılar)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, kaynak tarafından önerilen bir iletiyi kabul eder. İleti blokları, bir iletiyi doğrulamak ve döndürmek için bu yöntemi geçersiz kılmalıdır `_MsgId` .|
|[async_send](#async_send)|Zaman uyumsuz olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir yayma görevi başlatır|
|[consume_message](#consume_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce ayrılmış bir ileti kullanır.|
|[enable_batched_processing](#enable_batched_processing)|Bu blok için toplu işleme etkinleştirilir.|
|[initialize_source](#initialize_source)|`message_propagator`Bunu içinde başlatır `source_block` .|
|[link_target_notification](#link_target_notification)|Bu nesneye yeni bir hedef bağlandığını bildiren bir geri çağırma `source_block` .|
|[process_input_messages](#process_input_messages)|İşlem girişi iletileri. Bu yalnızca source_block türetilen yayıcı blokları için yararlıdır|
|[propagate_output_messages](#propagate_output_messages)|İletileri hedeflere yayma.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen iletiyi bağlı hedeflerin herhangi birine veya tümüne yayar. Bu, ileti blokları için ana yayma yordamlarıdır.|
|[release_message](#release_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, önceki bir ileti ayırmasını yayınlar.|
|[remove_targets](#remove_targets)|Bu kaynak bloğunun tüm hedef bağlantılarını kaldırır. Bu, yıkıcıdan çağrılmalıdır.|
|[reserve_message](#reserve_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu nesne tarafından daha önce sunulan bir iletiyi ayırır `source_block` .|
|[resume_propagation](#resume_propagation)|Türetilmiş bir sınıfta geçersiz kılınırsa, bir ayırma yayımlandıktan sonra yayılmaya devam eder.|
|[sync_send](#sync_send)|Zaman uyumlu olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir yayma görevi başlatır.|
|[unlink_target_notification](#unlink_target_notification)|Bir hedefin bu nesneden bağlantısının kesildiğinizi bildiren bir geri çağırma `source_block` .|
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|Tüm zaman uyumsuz yayılmaları tamamlanmasını bekler. Bu yayıcı belirli bir döndürme bekleme süresi, tüm zaman uyumsuz yayılmaları blok yok etmeden önce tamamlanmasını sağlamak için ileti bloklarının yıkıcıklarında kullanılır.|

## <a name="remarks"></a>Açıklamalar

İleti blokları, bu sınıf tarafından sağlanmış olan bağlantı yönetimi ve eşitlemeden faydalanmak için bu bloğundan türetilmelidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

`source_block`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept"></a><a name="accept"></a>ettiğinizde

Bu nesne tarafından sunulan `source_block` ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `accept` .

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Parametresi ise, yöntemi [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur `_PTarget` `NULL` .

`accept`Bu blok tarafından bir ileti sunulduğunda yöntemi bir hedef tarafından çağırılır `ISource` . Döndürülen ileti işaretçisi, `propagate` `ITarget` Bu kaynak iletinin bir kopyasını oluşturmak için karar verirse, bloğun yöntemine geçirilen yöntemden farklı olabilir.

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

Türetilmiş bir sınıfta geçersiz kılınırsa, kaynak tarafından önerilen bir iletiyi kabul eder. İleti blokları, bir iletiyi doğrulamak ve döndürmek için bu yöntemi geçersiz kılmalıdır `_MsgId` .

```cpp
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Nesnenin çalışma zamanı nesne kimliği `message` .

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

Sahipliği aktarmak için özgün ileti işaretçisinin döndürülmesi gerekir. Sahipliği sürdürmek için ileti yükünün bir kopyasının yapılması ve döndürülmesi gerekir.

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

Silmeyi engellemek için bu nesnede bir başvuru sayısı alır `source_block` .

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem `ITarget` , yöntemi sırasında bu kaynağa bağlanan bir nesne tarafından çağırılır `link_target` .

## <a name="async_send"></a><a name="async_send"></a>async_send

Zaman uyumsuz olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir yayma görevi başlatır

```cpp
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
`message`Zaman uyumsuz olarak gönderilen nesneye yönelik bir işaretçi.

## <a name="consume"></a><a name="consume"></a>kullanan

Bu nesne tarafından daha önce sunulan `source_block` ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Ayrılan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `consume` .

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Parametresi ise, yöntemi [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur `_PTarget` `NULL` .

Parametresi, [bad_target](bad-target-class.md) `_PTarget` çağıran hedefi temsil etmediği takdirde bad_target bir özel durum oluşturur `reserve` .

`consume`Yöntemi öğesine benzerdir `accept` , ancak her zaman döndürülen bir çağrı gelmelidir `reserve` **`true`** .

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce ayrılmış bir ileti kullanır.

```cpp
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Tüketilmekte olan nesne.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

`accept`,, Ancak, ' a benzer ancak her zaman öğesine yapılan bir çağrıdır `reserve` .

## <a name="enable_batched_processing"></a><a name="enable_batched_processing"></a>enable_batched_processing

Bu blok için toplu işleme etkinleştirilir.

```cpp
void enable_batched_processing();
```

## <a name="initialize_source"></a><a name="initialize_source"></a>initialize_source

`message_propagator`Bunu içinde başlatır `source_block` .

```cpp
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
Görevleri zamanlamak için kullanılacak Zamanlayıcı.

*_PScheduleGroup*<br/>
Görevleri zamanlamak için kullanılacak zamanlama grubu.

## <a name="link_target"></a><a name="link_target"></a>link_target

Bu nesneye bir hedef blok bağlar `source_block` .

```cpp
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
`ITarget`Bu nesneye bağlanacak bloğa yönelik bir işaretçi `source_block` .

### <a name="remarks"></a>Açıklamalar

Parametresi ise, yöntemi [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur `_PTarget` `NULL` .

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

Bu nesneye yeni bir hedef bağlandığını bildiren bir geri çağırma `source_block` .

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```

## <a name="process_input_messages"></a><a name="process_input_messages"></a>process_input_messages

İşlem girişi iletileri. Bu yalnızca source_block türetilen yayıcı blokları için yararlıdır

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti için bir işaretçi.

## <a name="propagate_output_messages"></a><a name="propagate_output_messages"></a>propagate_output_messages

İletileri hedeflere yayma.

```cpp
virtual void propagate_output_messages();
```

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen iletiyi bağlı hedeflerin herhangi birine veya tümüne yayar. Bu, ileti blokları için ana yayma yordamlarıdır.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Yayılacağı ileti için bir işaretçi.

## <a name="release"></a><a name="release"></a>Yayın

Önceki başarılı bir ileti ayırmasını serbest bırakır.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Ayrılan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `release` .

### <a name="remarks"></a>Açıklamalar

Parametresi ise, yöntemi [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur `_PTarget` `NULL` .

Parametresi, [bad_target](bad-target-class.md) `_PTarget` çağıran hedefi temsil etmediği takdirde bad_target bir özel durum oluşturur `reserve` .

## <a name="release_message"></a><a name="release_message"></a>release_message

Türetilmiş bir sınıfta geçersiz kılınırsa, önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Serbest bırakılmakta olan nesne.

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

Bu nesnede bir başvuru sayısı yayınlar `source_block` .

```cpp
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `ITarget` Bu kaynaktan bağlantısı kesilmekte olan bir nesne tarafından çağırılır. Kaynak bloğunun hedef blok için ayrılan kaynakları serbest bırakmaya izin verilir.

## <a name="remove_targets"></a><a name="remove_targets"></a>remove_targets

Bu kaynak bloğunun tüm hedef bağlantılarını kaldırır. Bu, yıkıcıdan çağrılmalıdır.

```cpp
void remove_targets();
```

## <a name="reserve"></a><a name="reserve"></a>ayırmaya

Bu nesne tarafından daha önce sunulan bir iletiyi ayırır `source_block` .

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `reserve` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** ileti başarıyla ayrıldıysa, **`false`** tersi durumda. Ayırmalar, aşağıdakiler dahil olmak üzere birçok nedenden dolayı başarısız olabilir: ileti zaten ayrılmış veya başka bir hedef tarafından kabul edildi, kaynak rezervasyonları reddedebilir ve bu şekilde devam eder.

### <a name="remarks"></a>Açıklamalar

Parametresi ise, yöntemi [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur `_PTarget` `NULL` .

Öğesini çağırdıktan sonra, başarılı olursa, `reserve` `consume` `release` sırasıyla iletinin sahipliğini almak veya vermek için ya da ' i çağırmanız gerekir.

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

Türetilmiş bir sınıfta geçersiz kılınırsa, bu nesne tarafından daha önce sunulan bir iletiyi ayırır `source_block` .

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Ayrılan nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** ileti başarıyla ayrıldıysa, **`false`** tersi durumda.

### <a name="remarks"></a>Açıklamalar

Çağrıldıktan sonra `reserve` , döndürürse, **`true`** `consume` `release` iletinin sahipliğini almak ya da serbest bırakmak için ya da çağrılması gerekir.

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

Türetilmiş bir sınıfta geçersiz kılınırsa, bir ayırma yayımlandıktan sonra yayılmaya devam eder.

```cpp
virtual void resume_propagation() = 0;
```

## <a name="source_block"></a><a name="ctor"></a>source_block

Bir `source_block` nesnesi oluşturur.

```cpp
source_block();
```

## <a name="source_block"></a><a name="dtor"></a>~ source_block

Nesneyi yok eder `source_block` .

```cpp
virtual ~source_block();
```

## <a name="sync_send"></a><a name="sync_send"></a>sync_send

Zaman uyumlu olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir yayma görevi başlatır.

```cpp
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
`message`Zaman uyumlu olarak gönderilen nesneye yönelik bir işaretçi.

## <a name="unlink_target"></a><a name="unlink_target"></a>unlink_target

Bu nesneden bir hedef bloğunun bağlantısını kaldırır `source_block` .

```cpp
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
`ITarget`Bu nesnenin bağlantısını kaldırmak için bir blok işaretçisi `source_block` .

### <a name="remarks"></a>Açıklamalar

Parametresi ise, yöntemi [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur `_PTarget` `NULL` .

## <a name="unlink_target_notification"></a><a name="unlink_target_notification"></a>unlink_target_notification

Bir hedefin bu nesneden bağlantısının kesildiğinizi bildiren bir geri çağırma `source_block` .

```cpp
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
`ITarget`Bağlantısının oluşturulduğu blok.

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

Bu nesneden tüm hedef blokların bağlantılarını Kaldır `source_block` .

```cpp
virtual void unlink_targets();
```

## <a name="wait_for_outstanding_async_sends"></a><a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends

Tüm zaman uyumsuz yayılmaları tamamlanmasını bekler. Bu yayıcı belirli bir döndürme bekleme süresi, tüm zaman uyumsuz yayılmaları blok yok etmeden önce tamamlanmasını sağlamak için ileti bloklarının yıkıcıklarında kullanılır.

```cpp
void wait_for_outstanding_async_sends();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[ISource Sınıfı](isource-class.md)
