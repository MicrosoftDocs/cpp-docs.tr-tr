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
ms.openlocfilehash: 3a0d69bc2e2904b1dcf37a7e9891d95bd869a610
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866140"
---
# <a name="source_block-class"></a>source_block Sınıfı

`source_block` sınıfı, yalnızca kaynak blokları için soyut bir temel sınıftır. Sınıfı, temel bağlantı yönetimi işlevlerinin yanı sıra ortak hata denetimleri sağlar.

## <a name="syntax"></a>Sözdizimi

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

|Adı|Açıklama|
|----------|-----------------|
|`target_iterator`|Bağlı hedeflere kılavuzluk eden Yineleyici.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[source_block](#ctor)|`source_block` nesnesi oluşturur.|
|[~ source_block yok edici](#dtor)|`source_block` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ettiğinizde](#accept)|Bu `source_block` nesnesi tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[acquire_ref](#acquire_ref)|Silmeyi engellemek için bu `source_block` nesnesi üzerinde bir başvuru sayısı alır.|
|[kullanan](#consume)|Bu `source_block` nesne tarafından daha önce sunulan ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.|
|[link_target](#link_target)|Hedef bloğu bu `source_block` nesnesine bağlar.|
|[Yayın](#release)|Önceki başarılı bir ileti ayırmasını serbest bırakır.|
|[release_ref](#release_ref)|Bu `source_block` nesnesinde bir başvuru sayısı yayınlar.|
|[ayırmaya](#reserve)|Bu `source_block` nesnesi tarafından daha önce sunulan bir iletiyi ayırır.|
|[unlink_target](#unlink_target)|Hedef bloğunun bu `source_block` nesnesinden bağlantısını kaldırır.|
|[unlink_targets](#unlink_targets)|Tüm hedef blokların bu `source_block` nesnesinden bağlantısını kaldırır. ( [ISource:: unlink_targets](isource-class.md#unlink_targets)geçersiz kılar)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, kaynak tarafından önerilen bir iletiyi kabul eder. İleti blokları, `_MsgId` doğrulamak ve bir ileti döndürmek için bu yöntemi geçersiz kılmalıdır.|
|[async_send](#async_send)|Zaman uyumsuz olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir yayma görevi başlatır|
|[consume_message](#consume_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce ayrılmış bir ileti kullanır.|
|[enable_batched_processing](#enable_batched_processing)|Bu blok için toplu işleme etkinleştirilir.|
|[initialize_source](#initialize_source)|Bu `source_block`içinde `message_propagator` başlatır.|
|[link_target_notification](#link_target_notification)|Yeni bir hedefin bu `source_block` nesnesine bağlandığını bildiren bir geri çağırma.|
|[process_input_messages](#process_input_messages)|İşlem girişi iletileri. Bu yalnızca source_block türetilen yayıcı blokları için yararlıdır|
|[propagate_output_messages](#propagate_output_messages)|İletileri hedeflere yayma.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen iletiyi bağlı hedeflerin herhangi birine veya tümüne yayar. Bu, ileti blokları için ana yayma yordamlarıdır.|
|[release_message](#release_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, önceki bir ileti ayırmasını yayınlar.|
|[remove_targets](#remove_targets)|Bu kaynak bloğunun tüm hedef bağlantılarını kaldırır. Bu, yıkıcıdan çağrılmalıdır.|
|[reserve_message](#reserve_message)|Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce bu `source_block` nesnesi tarafından sunulan bir iletiyi ayırır.|
|[resume_propagation](#resume_propagation)|Türetilmiş bir sınıfta geçersiz kılınırsa, bir ayırma yayımlandıktan sonra yayılmaya devam eder.|
|[sync_send](#sync_send)|Zaman uyumlu olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir yayma görevi başlatır.|
|[unlink_target_notification](#unlink_target_notification)|Bir hedefin bu `source_block` nesnesinden bağlantısının kesildiğinizi bildiren bir geri çağırma.|
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|Tüm zaman uyumsuz yayılmaları tamamlanmasını bekler. Bu yayıcı belirli bir döndürme bekleme süresi, tüm zaman uyumsuz yayılmaları blok yok etmeden önce tamamlanmasını sağlamak için ileti bloklarının yıkıcıklarında kullanılır.|

## <a name="remarks"></a>Açıklamalar

İleti blokları, bu sınıf tarafından sağlanmış olan bağlantı yönetimi ve eşitlemeden faydalanmak için bu bloğundan türetilmelidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

`source_block`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept"></a>ettiğinizde

Bu `source_block` nesnesi tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`accept` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Parametre `_PTarget` `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

Bu `ISource` bloğu tarafından bir ileti sunulduğunda `accept` yöntemi bir hedef tarafından çağırılır. Döndürülen ileti işaretçisi, bu kaynak iletinin bir kopyasını oluşturmak için karar verirse, `ITarget` bloğunun `propagate` metoduna geçirilen yöntemden farklı olabilir.

## <a name="accept_message"></a>accept_message

Türetilmiş bir sınıfta geçersiz kılınırsa, kaynak tarafından önerilen bir iletiyi kabul eder. İleti blokları, `_MsgId` doğrulamak ve bir ileti döndürmek için bu yöntemi geçersiz kılmalıdır.

```cpp
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`message` nesnesinin çalışma zamanı nesnesi kimliği.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

Sahipliği aktarmak için özgün ileti işaretçisinin döndürülmesi gerekir. Sahipliği sürdürmek için ileti yükünün bir kopyasının yapılması ve döndürülmesi gerekir.

## <a name="acquire_ref"></a>acquire_ref

Silmeyi engellemek için bu `source_block` nesnesi üzerinde bir başvuru sayısı alır.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `link_target` yöntemi sırasında bu kaynağa bağlanmakta olan bir `ITarget` nesnesi tarafından çağırılır.

## <a name="async_send"></a>async_send

Zaman uyumsuz olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir yayma görevi başlatır

```cpp
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
Zaman uyumsuz olarak gönderilen `message` nesnesine yönelik bir işaretçi.

## <a name="consume"></a>kullanan

Bu `source_block` nesne tarafından daha önce sunulan ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılmış `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`consume` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Parametre `_PTarget` `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

`_PTarget` parametresi `reserve`çağrılan hedefi temsil etmediği takdirde Yöntem [bad_target](bad-target-class.md) bir özel durum atar.

`consume` yöntemi `accept`benzerdir, ancak her zaman **true**döndüren `reserve` çağrısı gelmelidir.

## <a name="consume_message"></a>consume_message

Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce ayrılmış bir ileti kullanır.

```cpp
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Tüketilmekte olan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

`accept`benzerdir, ancak her zaman bir `reserve`çağrısıyla yapılır.

## <a name="enable_batched_processing"></a>enable_batched_processing

Bu blok için toplu işleme etkinleştirilir.

```cpp
void enable_batched_processing();
```

## <a name="initialize_source"></a>initialize_source

Bu `source_block`içinde `message_propagator` başlatır.

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

## <a name="link_target"></a>link_target

Hedef bloğu bu `source_block` nesnesine bağlar.

```cpp
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu `source_block` nesnesine bağlamak için `ITarget` bloğuna yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Parametre `_PTarget` `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

## <a name="link_target_notification"></a>link_target_notification

Yeni bir hedefin bu `source_block` nesnesine bağlandığını bildiren bir geri çağırma.

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```

## <a name="process_input_messages"></a>process_input_messages

İşlem girişi iletileri. Bu yalnızca source_block türetilen yayıcı blokları için yararlıdır

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek ileti için bir işaretçi.

## <a name="propagate_output_messages"></a>propagate_output_messages

İletileri hedeflere yayma.

```cpp
virtual void propagate_output_messages();
```

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen iletiyi bağlı hedeflerin herhangi birine veya tümüne yayar. Bu, ileti blokları için ana yayma yordamlarıdır.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Yayılacağı ileti için bir işaretçi.

## <a name="release"></a>Yayın

Önceki başarılı bir ileti ayırmasını serbest bırakır.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılmış `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`release` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Parametre `_PTarget` `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

`_PTarget` parametresi `reserve`çağrılan hedefi temsil etmediği takdirde Yöntem [bad_target](bad-target-class.md) bir özel durum atar.

## <a name="release_message"></a>release_message

Türetilmiş bir sınıfta geçersiz kılınırsa, önceki bir ileti ayırmasını yayınlar.

```cpp
virtual void release_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Yayımlanmakta olan `message` nesnesinin `runtime_object_identity`.

## <a name="release_ref"></a>release_ref

Bu `source_block` nesnesinde bir başvuru sayısı yayınlar.

```cpp
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu kaynaktan bağlantısı kesilmekte olan bir `ITarget` nesnesi tarafından çağırılır. Kaynak bloğunun hedef blok için ayrılan kaynakları serbest bırakmaya izin verilir.

## <a name="remove_targets"></a>remove_targets

Bu kaynak bloğunun tüm hedef bağlantılarını kaldırır. Bu, yıkıcıdan çağrılmalıdır.

```cpp
void remove_targets();
```

## <a name="reserve"></a>ayırmaya

Bu `source_block` nesnesi tarafından daha önce sunulan bir iletiyi ayırır.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`reserve` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

ileti başarıyla ayrıldıysa **true** , aksi takdirde **false** . Ayırmalar, aşağıdakiler dahil olmak üzere birçok nedenden dolayı başarısız olabilir: ileti zaten ayrılmış veya başka bir hedef tarafından kabul edildi, kaynak rezervasyonları reddedebilir ve bu şekilde devam eder.

### <a name="remarks"></a>Açıklamalar

Parametre `_PTarget` `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

`reserve`çağırdıktan sonra, başarılı olduysa, iletinin sahipliğini almak ya da sağlamak için `consume` veya `release` çağırmanız gerekir.

## <a name="reserve_message"></a>reserve_message

Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce bu `source_block` nesnesi tarafından sunulan bir iletiyi ayırır.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılan `message` nesnesinin `runtime_object_identity`.

### <a name="return-value"></a>Dönüş Değeri

ileti başarıyla ayrıldıysa **true** , aksi takdirde **false** .

### <a name="remarks"></a>Açıklamalar

`reserve` çağrıldıktan sonra, **doğru**döndürürse, iletinin sahipliğini almak ya da serbest bırakmak için `consume` veya `release` çağrılmalıdır.

## <a name="resume_propagation"></a>resume_propagation

Türetilmiş bir sınıfta geçersiz kılınırsa, bir ayırma yayımlandıktan sonra yayılmaya devam eder.

```cpp
virtual void resume_propagation() = 0;
```

## <a name="ctor"></a>source_block

`source_block` nesnesi oluşturur.

```cpp
source_block();
```

## <a name="dtor"></a>~ source_block

`source_block` nesnesini yok eder.

```cpp
virtual ~source_block();
```

## <a name="sync_send"></a>sync_send

Zaman uyumlu olarak iletileri kuyruğa alır ve henüz yapmadıysanız bir yayma görevi başlatır.

```cpp
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
Zaman uyumlu olarak göndermek için `message` nesnesine yönelik bir işaretçi.

## <a name="unlink_target"></a>unlink_target

Hedef bloğunun bu `source_block` nesnesinden bağlantısını kaldırır.

```cpp
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu `source_block` nesnesinden bağlantısını kaldırmak için `ITarget` bloğuna yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Parametre `_PTarget` `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

## <a name="unlink_target_notification"></a>unlink_target_notification

Bir hedefin bu `source_block` nesnesinden bağlantısının kesildiğinizi bildiren bir geri çağırma.

```cpp
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bağlantısının oluşturulduğu `ITarget` bloğu.

## <a name="unlink_targets"></a>unlink_targets

Tüm hedef blokların bu `source_block` nesnesinden bağlantısını kaldırır.

```cpp
virtual void unlink_targets();
```

## <a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends

Tüm zaman uyumsuz yayılmaları tamamlanmasını bekler. Bu yayıcı belirli bir döndürme bekleme süresi, tüm zaman uyumsuz yayılmaları blok yok etmeden önce tamamlanmasını sağlamak için ileti bloklarının yıkıcıklarında kullanılır.

```cpp
void wait_for_outstanding_async_sends();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ISource Sınıfı](isource-class.md)
