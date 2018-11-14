---
title: seçenek Sınıfı
ms.date: 11/04/2016
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
ms.openlocfilehash: 60b09b674bec58a7d35a9a37d9a8f4c40d8cd522
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522733"
---
# <a name="choice-class"></a>seçenek Sınıfı

A `choice` ileti bloğu bir kaynak kümesi denetim akışı etkileşim temsil eden çok kaynak, hedef tek bir blok. Seçim bloğu bir iletisi oluşturmak üzere birden çok kaynaktan herhangi biri için bekleyeceği ve ileti üretilen kaynak dizinini yayılır.

## <a name="syntax"></a>Sözdizimi

```
template<
    class T
>
class choice: public ISource<size_t>;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
A `tuple`-yüklerini giriş kaynakları temsil eden türüne göre.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`type`|Bir tür diğer adı için `T`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Seçim](#ctor)|Fazla Yüklendi. Oluşturur bir `choice` ileti bloğu.|
|[~ choice yok Edicisi](#dtor)|Yok eder `choice` ileti bloğu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kabul et](#accept)|Bu tarafından sunulan bir iletiyi kabul `choice` engelleme, arayana sahipliğini aktarma.|
|[acquire_ref](#acquire_ref)|Bu başvuru sayısını alması `choice` silinmesini engellemek için ileti bloğu.|
|[kullanma](#consume)|Daha önce bu tarafından sunulan iletiyi tüketir `choice` blok Mesajlaşma ve çağırana sahipliğini aktarma hedefi, başarılı bir şekilde ayrılmıştır.|
|[has_value](#has_value)|Denetler olup bu `choice` ileti bloğu başlatıldıysa bir değerle henüz.|
|[Dizin](#index)|Bir dizine döndürür `tuple` tarafından seçilen öğeyi temsil eden `choice` ileti bloğu.|
|[link_target](#link_target)|Bir hedef bloğu için bağlantı `choice` ileti bloğu.|
|[Yayın](#release)|Önceki bir başarılı iletisi ayırma serbest bırakır.|
|[release_ref](#release_ref)|Bir başvuru sayısı bu sürümleri `choice` ileti bloğu.|
|[ayırma](#reserve)|Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `choice` ileti bloğu.|
|[unlink_target](#unlink_target)|Bu hedef bloğun olan bağlantısını kesen `choice` ileti bloğu.|
|[unlink_targets](#unlink_targets)|Bu tüm hedefleri olan bağlantısını kesen `choice` ileti bloğu. (Geçersiz kılmaları [Isource::unlink_targets](isource-class.md#unlink_targets).)|
|[value](#value)|Dizini tarafından seçilmedi iletisini alır `choice` ileti bloğu.|

## <a name="remarks"></a>Açıklamalar

Gelen iletiler yalnızca biri tüketilir seçim bloğu sağlar.

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Isource](isource-class.md)

`choice`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept"></a> Kabul et

Bu tarafından sunulan bir iletiyi kabul `choice` engelleme, arayana sahipliğini aktarma.

```
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `accept` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Arayanın artık sahipliğini olan iletisi için bir işaretçi.

##  <a name="acquire_ref"></a> acquire_ref

Bu başvuru sayısını alması `choice` silinmesini engellemek için ileti bloğu.

```
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran bir hedef blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran bir `ITarget` sırasında bu kaynağa bağlı nesnesi `link_target` yöntemi.

##  <a name="ctor"></a> Seçim

Oluşturur bir `choice` ileti bloğu.

```
explicit choice(
    T _Tuple);

choice(
    Scheduler& _PScheduler,
    T _Tuple);

choice(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

choice(
    choice&& _Choice);
```

### <a name="parameters"></a>Parametreler

*_Tuple*<br/>
A `tuple` seçimi için kaynaklar.

*_PScheduler*<br/>
`Scheduler` İçinde Yayma görevi için nesne `choice` ileti bloğu zamanlandı.

*_PScheduleGroup*<br/>
`ScheduleGroup` İçinde Yayma görevi için nesne `choice` ileti bloğu zamanlandı. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.

*_Choice*<br/>
A `choice` kopyalamak için ileti bloğu. Orijinal nesneyi, bu bir taşıma Oluşturucusu yapma yalnız bırakılmış olduğunu unutmayın.

### <a name="remarks"></a>Açıklamalar

Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_PScheduler` veya `_PScheduleGroup` parametreleri.

Basit görev uçuşta taşıma sırasında emin olmak için kullanıcı en fazla olduğunu gösterir bir kilidi altında taşıma oluşturma yapılmaz. Aksi takdirde, özel durumlar veya tutarsız için önde gelen çok sayıda yarışa hazır oluşabilir.

##  <a name="dtor"></a> ~ Seçim

Yok eder `choice` ileti bloğu.

```
~choice();
```

##  <a name="consume"></a> kullanma

Daha önce bu tarafından sunulan iletiyi tüketir `choice` blok Mesajlaşma ve çağırana sahipliğini aktarma hedefi, başarılı bir şekilde ayrılmıştır.

```
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

##  <a name="has_value"></a> has_value

Denetler olup bu `choice` ileti bloğu başlatıldıysa bir değerle henüz.

```
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** blok bir değer aldıysa **false** Aksi takdirde.

##  <a name="index"></a> Dizin

Bir dizine döndürür `tuple` tarafından seçilen öğeyi temsil eden `choice` ileti bloğu.

```
size_t index();
```

### <a name="return-value"></a>Dönüş Değeri

İleti dizini.

### <a name="remarks"></a>Açıklamalar

İleti yükü kullanarak ayıklanabileceği `get` yöntemi.

##  <a name="link_target"></a> link_target

Bir hedef bloğu için bağlantı `choice` ileti bloğu.

```
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bir işaretçi bir `ITarget` bloğu için bağlantı `choice` ileti bloğu.

##  <a name="release"></a> Yayın

Önceki bir başarılı iletisi ayırma serbest bırakır.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Yayımlanan nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `release` yöntemi.

##  <a name="release_ref"></a> release_ref

Bir başvuru sayısı bu sürümleri `choice` ileti bloğu.

```
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran bir hedef blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran bir `ITarget` bu kaynaktan bağlantısız bir nesne. Kaynak blok için hedef blok ayrılmış tüm kaynakları serbest bırakmak için kullanılabilir.

##  <a name="reserve"></a> ayırma

Daha önce bu tarafından sunulan bir iletiyi ayırdıktan `choice` ileti bloğu.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` , `message` Ayrılan nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `reserve` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ileti başarıyla ayrıldı, **false** Aksi takdirde. Ayırmalar dahil olmak üzere çeşitli nedenlerle başarısız olabilir: ileti zaten ayrılmış veya kaynak ayırmaları Reddet vb. başka bir hedef tarafından kabul.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra `reserve`, başarılı olursa ya da çağırmalıdır `consume` veya `release` alabilir veya ileti, bir elinde sırasıyla vermek için.

##  <a name="unlink_target"></a> unlink_target

Bu hedef bloğun olan bağlantısını kesen `choice` ileti bloğu.

```
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bir işaretçi bir `ITarget` buradan bağlantısını kaldırmak için bloğu `choice` ileti bloğu.

##  <a name="unlink_targets"></a> unlink_targets

Bu tüm hedefleri olan bağlantısını kesen `choice` ileti bloğu.

```
virtual void unlink_targets();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, çünkü yok ediciden çağrılması gerekmez. iç için yıkıcı `single_assignment` blok bağlantısını doğru.

##  <a name="value"></a> Değer

Dizini tarafından seçilmedi iletisini alır `choice` ileti bloğu.

```
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>Parametreler

*_Payload_type*<br/>
İleti yükü türü.

### <a name="return-value"></a>Dönüş Değeri

İletinin yükü.

### <a name="remarks"></a>Açıklamalar

Çünkü bir `choice` ileti engelleme, farklı yük türleri ile girişleri alabilir, yükü alma noktasında türünü belirtmeniz gerekir. Sonucuna göre türü belirleyebilir `index` yöntemi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[join Sınıfı](join-class.md)<br/>
[single_assignment Sınıfı](single-assignment-class.md)
