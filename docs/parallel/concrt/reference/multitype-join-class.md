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
ms.openlocfilehash: 7a0c68c2c017eedfa23548bee1d17177e8eaaa1e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409953"
---
# <a name="multitypejoin-class"></a>multitype_join Sınıfı

A `multitype_join` ileti bloğu her kaynaklarının farklı türdeki iletileri birleştirir ve hedeflerine birleşik iletileri tanımlama grubu sunar bir çok kaynak, hedef tek ileti bloğu.

## <a name="syntax"></a>Sözdizimi

```
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
`tuple` Yük türü iletileri birleştirilmiş ve blok tarafından yayılır.

*_Jtype*<br/>
Tür, `join` ya da bu, blok `greedy` veya `non_greedy`

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`type`|Bir tür diğer adı için `T`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[multitype_join](#ctor)|Fazla Yüklendi. Oluşturur bir `multitype_join` ileti bloğu.|
|[~ multitype_join yok Edicisi](#dtor)|Yok eder `multitype_join` ileti bloğu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kabul et](#accept)|Bu tarafından sunulan bir iletiyi kabul `multitype_join` engelleme, arayana sahipliğini aktarma.|
|[acquire_ref](#acquire_ref)|Bu başvuru sayısını alması `multitype_join` silinmesini engellemek için ileti bloğu.|
|[kullanma](#consume)|Daha önce tarafından sunulan iletiyi tüketir `multitype_join` blok Mesajlaşma ve çağırana sahipliğini aktarma hedefi, başarılı bir şekilde ayrılmıştır.|
|[link_target](#link_target)|Bir hedef bloğu için bağlantı `multitype_join` ileti bloğu.|
|[Yayın](#release)|Önceki bir başarılı iletisi ayırma serbest bırakır.|
|[release_ref](#release_ref)|Bir başvuru sayısı bu sürümleri `multiple_join` ileti bloğu.|
|[ayırma](#reserve)|Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `multitype_join` ileti bloğu.|
|[unlink_target](#unlink_target)|Bu hedef bloğun olan bağlantısını kesen `multitype_join` ileti bloğu.|
|[unlink_targets](#unlink_targets)|Bu tüm hedefleri olan bağlantısını kesen `multitype_join` ileti bloğu. (Geçersiz kılmaları [Isource::unlink_targets](isource-class.md#unlink_targets).)|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept"></a> Kabul et

Bu tarafından sunulan bir iletiyi kabul `multitype_join` engelleme, arayana sahipliğini aktarma.

```
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `accept` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Arayanın artık sahipliğini olan iletisi için bir işaretçi.

##  <a name="acquire_ref"></a> acquire_ref

Bu başvuru sayısını alması `multitype_join` silinmesini engellemek için ileti bloğu.

```
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran bir hedef blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran bir `ITarget` sırasında bu kaynağa bağlı nesnesi `link_target` yöntemi.

##  <a name="consume"></a> kullanma

Daha önce tarafından sunulan iletiyi tüketir `multitype_join` blok Mesajlaşma ve çağırana sahipliğini aktarma hedefi, başarılı bir şekilde ayrılmıştır.

```
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Ayrılmış, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `consume` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `message` nesne arayan sahipliğini artık sahiptir.

### <a name="remarks"></a>Açıklamalar

`consume` Yöntemi benzer `accept`, ancak her zaman bir çağrı tarafından gelmelidir `reserve` döndürülen **true**.

##  <a name="link_target"></a> link_target

Bir hedef bloğu için bağlantı `multitype_join` ileti bloğu.

```
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bir işaretçi bir `ITarget` bloğu için bağlantı `multitype_join` ileti bloğu.

##  <a name="ctor"></a> multitype_join

Oluşturur bir `multitype_join` ileti bloğu.

```
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
A `tuple` bu kaynakları `multitype_join` ileti bloğu.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `multitype_join` ileti bloğu zamanlandı.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `multitype_join` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

*_Join*<br/>
A `multitype_join` kopyalamak için ileti bloğu. Orijinal nesneyi, bu bir taşıma Oluşturucusu yapma yalnız bırakılmış olduğunu unutmayın.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.

Basit görev uçuşta taşıma sırasında emin olmak için kullanıcı en fazla olduğunu gösterir bir kilidi altında taşıma oluşturma yapılmaz. Aksi takdirde, özel durumlar veya tutarsız için önde gelen çok sayıda yarışa hazır oluşabilir.

##  <a name="dtor"></a> ~ multitype_join

Yok eder `multitype_join` ileti bloğu.

```
~multitype_join();
```

##  <a name="release"></a> Yayın

Önceki bir başarılı iletisi ayırma serbest bırakır.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Yayımlanan nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `release` yöntemi.

##  <a name="release_ref"></a> release_ref

Bir başvuru sayısı bu sürümleri `multiple_join` ileti bloğu.

```
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran bir hedef blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran bir `ITarget` bu kaynaktan bağlantısız bir nesne. Kaynak blok için hedef blok ayrılmış tüm kaynakları serbest bırakmak için kullanılabilir.

##  <a name="reserve"></a> ayırma

Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `multitype_join` ileti bloğu.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Ayrılan nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `reserve` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

`true` iletinin başarıyla ayrıldı, `false` Aksi takdirde. Ayırmalar dahil olmak üzere çeşitli nedenlerle başarısız olabilir: ileti zaten ayrılmış veya kaynak ayırmaları Reddet vb. başka bir hedef tarafından kabul.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra `reserve`, başarılı olursa ya da çağırmalıdır `consume` veya `release` alabilir veya ileti, bir elinde sırasıyla vermek için.

##  <a name="unlink_target"></a> unlink_target

Bu hedef bloğun olan bağlantısını kesen `multitype_join` ileti bloğu.

```
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bir işaretçi bir `ITarget` buradan bağlantısını kaldırmak için bloğu `multitype_join` ileti bloğu.

##  <a name="unlink_targets"></a> unlink_targets

Bu tüm hedefleri olan bağlantısını kesen `multitype_join` ileti bloğu.

```
virtual void unlink_targets();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[choice Sınıfı](choice-class.md)<br/>
[join Sınıfı](join-class.md)
