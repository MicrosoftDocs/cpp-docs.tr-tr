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
ms.openlocfilehash: c648e77e404cf39eab281a93e03d8b427da375f8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87205866"
---
# <a name="multitype_join-class"></a>multitype_join Sınıfı

`multitype_join`Mesajlaşma bloğu, kaynaklarından her birinin farklı türlerindeki iletileri birleştiren ve hedeflerine Birleşik iletilerin bir listesini sunan çok kaynaklı, tek hedef mesajlaşma bloğudur.

## <a name="syntax"></a>Söz dizimi

```cpp
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
`tuple`Blok tarafından birleştirilen ve yayılan iletilerin yük türü.

*_Jtype*<br/>
`join`Bu blok türü, `greedy` ya da`non_greedy`

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|İçin bir tür diğer adı `T` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[multitype_join](#ctor)|Fazla Yüklendi. `multitype_join`İleti bloğu oluşturur.|
|[~ multitype_join yok edici](#dtor)|`multitype_join`Mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ettiğinizde](#accept)|Bu blok tarafından sunulan `multitype_join` ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[acquire_ref](#acquire_ref)|`multitype_join`Silmeyi engellemek için bu mesajlaşma bloğunda bir başvuru sayısı alır.|
|[kullanan](#consume)|İleti bloğu tarafından daha önce sunulan `multitype_join` ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.|
|[link_target](#link_target)|Bu mesajlaşma bloğuna bir hedef bloğu bağlar `multitype_join` .|
|[Yayın](#release)|Önceki başarılı bir ileti ayırmasını serbest bırakır.|
|[release_ref](#release_ref)|Bu mesajlaşma bloğunda bir başvuru sayısı yayınlar `multiple_join` .|
|[Rezerve et](#reserve)|Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `multitype_join` .|
|[unlink_target](#unlink_target)|Bu mesajlaşma bloğundan bir hedef bloğunun bağlantısını kaldırır `multitype_join` .|
|[unlink_targets](#unlink_targets)|Bu mesajlaşma bloğundan tüm hedeflerin bağlantısını kaldırır `multitype_join` . ( [ISource:: unlink_targets](isource-class.md#unlink_targets)geçersiz kılar)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept"></a><a name="accept"></a>ettiğinizde

Bu blok tarafından sunulan `multitype_join` ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `accept` .

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

`multitype_join`Silmeyi engellemek için bu mesajlaşma bloğunda bir başvuru sayısı alır.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `ITarget` , yöntemi sırasında bu kaynağa bağlanan bir nesne tarafından çağırılır `link_target` .

## <a name="consume"></a><a name="consume"></a>kullanan

İleti bloğu tarafından daha önce sunulan `multitype_join` ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Ayrılan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `consume` .

### <a name="return-value"></a>Dönüş Değeri

`message`Çağıranın artık sahipliği olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`consume`Yöntemi öğesine benzerdir `accept` , ancak her zaman döndürülen bir çağrı gelmelidir `reserve` **`true`** .

## <a name="link_target"></a><a name="link_target"></a>link_target

Bu mesajlaşma bloğuna bir hedef bloğu bağlar `multitype_join` .

```cpp
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
`ITarget`Bu mesajlaşma bloğuna bağlanacak bloğa yönelik bir işaretçi `multitype_join` .

## <a name="multitype_join"></a><a name="ctor"></a>multitype_join

`multitype_join`İleti bloğu oluşturur.

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
`tuple`Bu mesajlaşma bloğuna yönelik bir kaynak `multitype_join` .

*_PScheduler*<br/>
`Scheduler` `multitype_join` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_PScheduleGroup*<br/>
`ScheduleGroup` `multitype_join` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

*_Join*<br/>
`multitype_join`Kopyalamanın bir ileti bloğu. Özgün nesnenin yalnız bırakılmış olduğunu ve bunu bir taşıma Oluşturucusu yapmayı unutmayın.

### <a name="remarks"></a>Açıklamalar

Veya parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır `_PScheduler` `_PScheduleGroup` .

Taşıma işlemi bir kilit altında gerçekleştirilmez, bu, taşıma sırasında uçuş kapsamında hiçbir hafif görev olmadığından emin olmak için kullanıcıya ait olduğu anlamına gelir. Aksi takdirde, çok sayıda özel durum ortaya çıkabilir, bu durum istisnalara veya tutarsız duruma gelebilir.

## <a name="multitype_join"></a><a name="dtor"></a>~ multitype_join

`multitype_join`Mesajlaşma bloğunu yok eder.

```cpp
~multitype_join();
```

## <a name="release"></a><a name="release"></a>Yayın

Önceki başarılı bir ileti ayırmasını serbest bırakır.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Serbest bırakılmakta olan nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `release` .

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

Bu mesajlaşma bloğunda bir başvuru sayısı yayınlar `multiple_join` .

```cpp
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `ITarget` Bu kaynaktan bağlantısı kesilmekte olan bir nesne tarafından çağırılır. Kaynak bloğunun hedef blok için ayrılan kaynakları serbest bırakmaya izin verilir.

## <a name="reserve"></a><a name="reserve"></a>ayırmaya

Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `multitype_join` .

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Ayrılan nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `reserve` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** ileti başarıyla ayrıldıysa, **`false`** tersi durumda. Ayırmalar, aşağıdakiler dahil olmak üzere birçok nedenden dolayı başarısız olabilir: ileti zaten ayrılmış veya başka bir hedef tarafından kabul edildi, kaynak rezervasyonları reddedebilir ve bu şekilde devam eder.

### <a name="remarks"></a>Açıklamalar

Öğesini çağırdıktan sonra, başarılı olursa, `reserve` `consume` `release` sırasıyla iletinin sahipliğini almak veya vermek için ya da ' i çağırmanız gerekir.

## <a name="unlink_target"></a><a name="unlink_target"></a>unlink_target

Bu mesajlaşma bloğundan bir hedef bloğunun bağlantısını kaldırır `multitype_join` .

```cpp
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
`ITarget`Bu mesajlaşma bloğunun bağlantısını kaldırmak için bir blok işaretçisi `multitype_join` .

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

Bu mesajlaşma bloğundan tüm hedeflerin bağlantısını kaldırır `multitype_join` .

```cpp
virtual void unlink_targets();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[seçim sınıfı](choice-class.md)<br/>
[JOIN sınıfı](join-class.md)
