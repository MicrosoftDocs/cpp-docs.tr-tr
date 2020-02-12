---
title: multitype_join Sınıfı
ms.date: 11/04/2016
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
ms.openlocfilehash: 4214c43fa0d0ab8fdd29ed54738c19f72a07267a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138948"
---
# <a name="multitype_join-class"></a>multitype_join Sınıfı

`multitype_join` mesajlaşma bloğu, kaynaklarından her birinin farklı türlerindeki iletileri birleştiren ve hedeflerine Birleşik iletilerin bir listesini sunan çok kaynaklı, tek hedef mesajlaşma bloğudur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Blok tarafından birleştirilen ve yayılan iletilerin `tuple` yük türü.

*_Jtype*<br/>
`join` bloğunun türü, `greedy` ya da `non_greedy`

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|`T`için bir tür diğer adı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[multitype_join](#ctor)|Fazla Yüklendi. `multitype_join` mesajlaşma bloğu oluşturur.|
|[~ multitype_join yok edici](#dtor)|`multitype_join` mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ettiğinizde](#accept)|Bu `multitype_join` bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[acquire_ref](#acquire_ref)|Silmeyi engellemek için bu `multitype_join` mesajlaşma bloğunda bir başvuru sayısı alır.|
|[kullanan](#consume)|Daha önce `multitype_join` mesajlaşma bloğu tarafından sunulan ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.|
|[link_target](#link_target)|Hedef bloğu bu `multitype_join` mesajlaşma bloğuna bağlar.|
|[Yayın](#release)|Önceki başarılı bir ileti ayırmasını serbest bırakır.|
|[release_ref](#release_ref)|Bu `multiple_join` mesajlaşma bloğunda bir başvuru sayısı yayınlar.|
|[ayırmaya](#reserve)|Daha önce bu `multitype_join` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.|
|[unlink_target](#unlink_target)|Hedef bloğunun bu `multitype_join` mesajlaşma bloğundan bağlantısını kaldırır.|
|[unlink_targets](#unlink_targets)|Bu `multitype_join` mesajlaşma bloğundan tüm hedeflerin bağlantısını kaldırır. ( [ISource:: unlink_targets](isource-class.md#unlink_targets)geçersiz kılar)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept"></a>ettiğinizde

Bu `multitype_join` bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`accept` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

## <a name="acquire_ref"></a>acquire_ref

Silmeyi engellemek için bu `multitype_join` mesajlaşma bloğunda bir başvuru sayısı alır.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `link_target` yöntemi sırasında bu kaynağa bağlanmakta olan bir `ITarget` nesnesi tarafından çağırılır.

## <a name="consume"></a>kullanan

Daha önce `multitype_join` mesajlaşma bloğu tarafından sunulan ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılmış `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`consume` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan `message` nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`consume` yöntemi `accept`benzerdir, ancak her zaman **true**döndüren `reserve` çağrısı gelmelidir.

## <a name="link_target"></a>link_target

Hedef bloğu bu `multitype_join` mesajlaşma bloğuna bağlar.

```cpp
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu `multitype_join` mesajlaşma bloğuna bağlantı için `ITarget` bloğuna yönelik bir işaretçi.

## <a name="ctor"></a>multitype_join

`multitype_join` mesajlaşma bloğu oluşturur.

```cpp
explicit multitype_join(
    T _Tuple);

multitype_join(
    Scheduler& _PScheduler,
    T _Tuple);

multitype_join(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

multitype_join(
    multitype_join&& _Join);
```

### <a name="parameters"></a>Parametreler

*_Tuple*<br/>
Bu `multitype_join` mesajlaşma bloğuna yönelik kaynakların `tuple`.

*_PScheduler*<br/>
`multitype_join` mesajlaşma bloğunun yayma görevinin içinde `Scheduler` nesnesi zamanlandı.

*_PScheduleGroup*<br/>
`multitype_join` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

*_Join*<br/>
Kopyalamanın `multitype_join` bir mesajlaşma bloğu. Özgün nesnenin yalnız bırakılmış olduğunu ve bunu bir taşıma Oluşturucusu yapmayı unutmayın.

### <a name="remarks"></a>Açıklamalar

`_PScheduler` veya `_PScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

Taşıma işlemi bir kilit altında gerçekleştirilmez, bu, taşıma sırasında uçuş kapsamında hiçbir hafif görev olmadığından emin olmak için kullanıcıya ait olduğu anlamına gelir. Aksi takdirde, çok sayıda özel durum ortaya çıkabilir, bu durum istisnalara veya tutarsız duruma gelebilir.

## <a name="dtor"></a>~ multitype_join

`multitype_join` mesajlaşma bloğunu yok eder.

```cpp
~multitype_join();
```

## <a name="release"></a>Yayın

Önceki başarılı bir ileti ayırmasını serbest bırakır.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Yayımlanmakta olan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`release` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

## <a name="release_ref"></a>release_ref

Bu `multiple_join` mesajlaşma bloğunda bir başvuru sayısı yayınlar.

```cpp
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu kaynaktan bağlantısı kesilmekte olan bir `ITarget` nesnesi tarafından çağırılır. Kaynak bloğunun hedef blok için ayrılan kaynakları serbest bırakmaya izin verilir.

## <a name="reserve"></a>ayırmaya

Daha önce bu `multitype_join` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`reserve` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

ileti başarıyla ayrıldıysa `true`, aksi takdirde `false`. Ayırmalar, aşağıdakiler dahil olmak üzere birçok nedenden dolayı başarısız olabilir: ileti zaten ayrılmış veya başka bir hedef tarafından kabul edildi, kaynak rezervasyonları reddedebilir ve bu şekilde devam eder.

### <a name="remarks"></a>Açıklamalar

`reserve`çağırdıktan sonra, başarılı olduysa, iletinin sahipliğini almak ya da sağlamak için `consume` veya `release` çağırmanız gerekir.

## <a name="unlink_target"></a>unlink_target

Hedef bloğunun bu `multitype_join` mesajlaşma bloğundan bağlantısını kaldırır.

```cpp
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu `multitype_join` mesajlaşma bloğundan bağlantısını kaldırmak için `ITarget` bloğuna yönelik bir işaretçi.

## <a name="unlink_targets"></a>unlink_targets

Bu `multitype_join` mesajlaşma bloğundan tüm hedeflerin bağlantısını kaldırır.

```cpp
virtual void unlink_targets();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[choice Sınıfı](choice-class.md)<br/>
[join Sınıfı](join-class.md)
