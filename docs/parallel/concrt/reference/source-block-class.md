---
title: source_block sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4a184e0fee76f3aa5bb8f7729250c03b10b9dfc
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163497"
---
# <a name="sourceblock-class"></a>source_block Sınıfı

`source_block` Sınıfı, yalnızca kaynak bloklar için Özet temel sınıf. Sınıfı, düzgün olarak sık karşılaşılan hata denetimleri temel bağlantı yönetimi işlevselliği sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```

#### <a name="parameters"></a>Parametreler

*_TargetLinkRegistry*<br/>
Hedef bağlantıları tutmak için kullanılacak bağlantı kayıt defteri.

*_MessageProcessorType*<br/>
İleti işleme için işlemci türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`target_iterator`|Bağlı hedefleri yürütmek için bir yineleyici.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[source_block](#ctor)|Oluşturur bir `source_block` nesne.|
|[~ source_block yok Edicisi](#dtor)|Yok eder `source_block` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kabul et](#accept)|Bu tarafından sunulan bir iletiyi kabul `source_block` çağırana sahipliğini aktarma nesnesi.|
|[acquire_ref](#acquire_ref)|Bu başvuru sayısını alması `source_block` silinmesini engellemek için nesne.|
|[kullanma](#consume)|Daha önce bu tarafından sunulan iletiyi tüketir `source_block` nesne ve çağırana sahipliğini aktarma hedefi, başarılı bir şekilde ayrılmıştır.|
|[link_target](#link_target)|Bir hedef bloğu için bağlantı `source_block` nesne.|
|[Yayın](#release)|Önceki bir başarılı iletisi ayırma serbest bırakır.|
|[release_ref](#release_ref)|Bir başvuru sayısı bu sürümleri `source_block` nesne.|
|[ayırma](#reserve)|Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `source_block` nesne.|
|[unlink_target](#unlink_target)|Bu hedef bloğun olan bağlantısını kesen `source_block` nesne.|
|[unlink_targets](#unlink_targets)|Bu, tüm hedef bloklara olan bağlantısını kesen `source_block` nesne. (Geçersiz kılmaları [Isource::unlink_targets](isource-class.md#unlink_targets).)|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[accept_message](#accept_message)|Türetilen bir sınıfta geçersiz kılındığında, kaynağı tarafından sunulan bir iletiye kabul eder. İleti blokları doğrulamak için bu yöntemi geçersiz kılmalıdır `_MsgId` ve bir ileti döndürür.|
|[async_send](#async_send)|Zaman uyumsuz olarak iletileri kuyruğa alır ve bu zaten yapılmadıysa bir yayma görevi başlar|
|[consume_message](#consume_message)|Türetilen bir sınıfta geçersiz kılındığında, daha önce ayrılmış bir iletiyi tüketir.|
|[enable_batched_processing](#enable_batched_processing)|Bu blok için işleme toplu olanak tanır.|
|[initialize_source](#initialize_source)|Başlatır `message_propagator` bu `source_block`.|
|[link_target_notification](#link_target_notification)|Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `source_block` nesne.|
|[process_input_messages](#process_input_messages)|İşlem giriş iletileri. Yalnızca source_block türetilen Yayıcı bloklar için kullanışlıdır|
|[propagate_output_messages](#propagate_output_messages)|Hedeflere iletileri yayar.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Türetilen bir sınıfta geçersiz kılındığında, tüm bağlı hedeflerin belirli bir ileti yayar. İleti blokları için ana yayma yordamı budur.|
|[release_message](#release_message)|Türetilen bir sınıfta geçersiz kılındığında, bir önceki ileti ayırma serbest bırakır.|
|[remove_targets](#remove_targets)|Bu kaynak bloğu tüm hedef bağlantıları kaldırır. Bu yıkıcıdan çağrılmalıdır.|
|[reserve_message](#reserve_message)|Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir iletiyi ayırdıktan `source_block` nesne.|
|[resume_propagation](#resume_propagation)|Türetilen bir sınıfta geçersiz kılındığında, bir ayırma piyasaya sürüldükten sonra yayma devam ettirir.|
|[sync_send](#sync_send)|Zaman uyumlu iletileri kuyruğa alır ve bu zaten yapılmadıysa bir yayma görevi başlar.|
|[unlink_target_notification](#unlink_target_notification)|Bir hedef bu bağlantısız olduğunu bildiren bir geri çağırma `source_block` nesne.|
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|Tamamlamak tüm zaman uyumsuz yayılmaları bekler. Bu Yayıcı özgü dönmesini bekleyin ileti blokları yıkıcılarda tüm zaman uyumsuz yayılmaları blok yok etme öncesinde tamamlanması zaman sahip olduğunuzdan emin olmak için kullanılır.|

## <a name="remarks"></a>Açıklamalar

İleti blokları bağlantı yönetimi ve bu sınıfı tarafından sağlanan eşitleme yararlanmak için bu blok türetilmesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

`source_block`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept"></a> Kabul et

Bu tarafından sunulan bir iletiyi kabul `source_block` çağırana sahipliğini aktarma nesnesi.

```
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `accept` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum, parametre `_PTarget` olduğu `NULL`.

`accept` Yöntemi, bir hedef tarafından çağrıldığında, bir ileti bu edilmeksizin sunulacaktır ancak `ISource` blok. İleti işaretçi döndürülen yöntemlere geçirilen olandan farklı olabilir `propagate` yöntemi `ITarget` iletinin bir kopyasını oluşturmak bu kaynak karar verirse, engelleyin.

##  <a name="accept_message"></a> accept_message

Türetilen bir sınıfta geçersiz kılındığında, kaynağı tarafından sunulan bir iletiye kabul eder. İleti blokları doğrulamak için bu yöntemi geçersiz kılmalıdır `_MsgId` ve bir ileti döndürür.

```
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Çalışma zamanı nesne kimliğini `message` nesne.

### <a name="return-value"></a>Dönüş Değeri

Arayanın artık sahipliğini olan iletisi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sahipliğini devretmek için özgün ileti işaretçi döndürülmelidir. Sahipliği korumak için bir kopyasını ileti yükü yapılan ve döndürülen olması gerekir.

##  <a name="acquire_ref"></a> acquire_ref

Bu başvuru sayısını alması `source_block` silinmesini engellemek için nesne.

```
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran bir `ITarget` sırasında bu kaynağa bağlı nesnesi `link_target` yöntemi.

##  <a name="async_send"></a> async_send

Zaman uyumsuz olarak iletileri kuyruğa alır ve bu zaten yapılmadıysa bir yayma görevi başlar

```
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
Bir işaretçi bir `message` zaman uyumsuz olarak göndermek için nesne.

##  <a name="consume"></a> kullanma

Daha önce bu tarafından sunulan iletiyi tüketir `source_block` nesne ve çağırana sahipliğini aktarma hedefi, başarılı bir şekilde ayrılmıştır.

```
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Ayrılmış, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `consume` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum, parametre `_PTarget` olduğu `NULL`.

Çağırılıyorsa yöntem bir [bad_target](bad-target-class.md) özel durum, parametre `_PTarget` adlı hedef göstermiyor `reserve`.

`consume` Yöntemi benzer `accept`, ancak her zaman bir çağrı tarafından gelmelidir `reserve` döndürülen **true**.

##  <a name="consume_message"></a> consume_message

Türetilen bir sınıfta geçersiz kılındığında, daha önce ayrılmış bir iletiyi tüketir.

```
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Kullanılan nesne.

### <a name="return-value"></a>Dönüş Değeri

Arayanın artık sahipliğini olan iletisi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Benzer şekilde `accept`, ancak her zaman bir çağrı tarafından öncesinde `reserve`.

##  <a name="enable_batched_processing"></a> enable_batched_processing

Bu blok için işleme toplu olanak tanır.

```
void enable_batched_processing();
```

##  <a name="initialize_source"></a> initialize_source

Başlatır `message_propagator` bu `source_block`.

```
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
Görevleri zamanlamak için kullanılacak Zamanlayıcı.

*_PScheduleGroup*<br/>
Görevleri zamanlamak için kullanılacak zamanlama grubu.

##  <a name="link_target"></a> link_target

Bir hedef bloğu için bağlantı `source_block` nesne.

```
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bir işaretçi bir `ITarget` bloğu için bağlantı `source_block` nesne.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum, parametre `_PTarget` olduğu `NULL`.

##  <a name="link_target_notification"></a> link_target_notification

Yeni bir hedef için bağlandı olduğunu bildiren bir geri çağırma `source_block` nesne.

```
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```

##  <a name="process_input_messages"></a> process_input_messages

İşlem giriş iletileri. Yalnızca source_block türetilen Yayıcı bloklar için kullanışlıdır

```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İşlenecek iletisi için bir işaretçi.

##  <a name="propagate_output_messages"></a> propagate_output_messages

Hedeflere iletileri yayar.

```
virtual void propagate_output_messages();
```

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

Türetilen bir sınıfta geçersiz kılındığında, tüm bağlı hedeflerin belirli bir ileti yayar. İleti blokları için ana yayma yordamı budur.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
İletisini yayılması için bir işaretçi.

##  <a name="release"></a> Yayın

Önceki bir başarılı iletisi ayırma serbest bırakır.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Ayrılmış, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `release` yöntemi.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum, parametre `_PTarget` olduğu `NULL`.

Çağırılıyorsa yöntem bir [bad_target](bad-target-class.md) özel durum, parametre `_PTarget` adlı hedef göstermiyor `reserve`.

##  <a name="release_message"></a> release_message

Türetilen bir sınıfta geçersiz kılındığında, bir önceki ileti ayırma serbest bırakır.

```
virtual void release_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Yayımlanan nesne.

##  <a name="release_ref"></a> release_ref

Bir başvuru sayısı bu sürümleri `source_block` nesne.

```
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran bir hedef blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran bir `ITarget` bu kaynaktan bağlantısız bir nesne. Kaynak blok için hedef blok ayrılmış tüm kaynakları serbest bırakmak için kullanılabilir.

##  <a name="remove_targets"></a> remove_targets

Bu kaynak bloğu tüm hedef bağlantıları kaldırır. Bu yıkıcıdan çağrılmalıdır.

```
void remove_targets();
```

##  <a name="reserve"></a> ayırma

Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `source_block` nesne.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `reserve` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ileti başarıyla ayrıldı, **false** Aksi takdirde. Ayırmalar dahil olmak üzere çeşitli nedenlerle başarısız olabilir: ileti zaten ayrılmış veya kaynak ayırmaları Reddet vb. başka bir hedef tarafından kabul.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum, parametre `_PTarget` olduğu `NULL`.

Çağırdıktan sonra `reserve`, başarılı olursa ya da çağırmalıdır `consume` veya `release` alabilir veya ileti, bir elinde sırasıyla vermek için.

##  <a name="reserve_message"></a> reserve_message

Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir iletiyi ayırdıktan `source_block` nesne.

```
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Ayrılan nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ileti başarıyla ayrıldı, **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sonra `reserve` çağrılır, döndürürse **true**, ya da `consume` veya `release` alın veya iletinin sahipliğini serbest bırakmak için çağrılmalıdır.

##  <a name="resume_propagation"></a> resume_propagation

Türetilen bir sınıfta geçersiz kılındığında, bir ayırma piyasaya sürüldükten sonra yayma devam ettirir.

```
virtual void resume_propagation() = 0;
```

##  <a name="ctor"></a> source_block

Oluşturur bir `source_block` nesne.

```
source_block();
```

##  <a name="dtor"></a> ~ source_block

Yok eder `source_block` nesne.

```
virtual ~source_block();
```

##  <a name="sync_send"></a> sync_send

Zaman uyumlu iletileri kuyruğa alır ve bu zaten yapılmadıysa bir yayma görevi başlar.

```
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>Parametreler

*_Msg*<br/>
Bir işaretçi bir `message` zaman uyumlu olarak göndermek için nesne.

##  <a name="unlink_target"></a> unlink_target

Bu hedef bloğun olan bağlantısını kesen `source_block` nesne.

```
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bir işaretçi bir `ITarget` buradan bağlantısını kaldırmak için bloğu `source_block` nesne.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) özel durum, parametre `_PTarget` olduğu `NULL`.

##  <a name="unlink_target_notification"></a> unlink_target_notification

Bir hedef bu bağlantısız olduğunu bildiren bir geri çağırma `source_block` nesne.

```
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
`ITarget` Kaldırıldı blok.

##  <a name="unlink_targets"></a> unlink_targets

Bu, tüm hedef bloklara olan bağlantısını kesen `source_block` nesne.

```
virtual void unlink_targets();
```

##  <a name="wait_for_outstanding_async_sends"></a> wait_for_outstanding_async_sends

Tamamlamak tüm zaman uyumsuz yayılmaları bekler. Bu Yayıcı özgü dönmesini bekleyin ileti blokları yıkıcılarda tüm zaman uyumsuz yayılmaları blok yok etme öncesinde tamamlanması zaman sahip olduğunuzdan emin olmak için kullanılır.

```
void wait_for_outstanding_async_sends();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ISource Sınıfı](isource-class.md)
