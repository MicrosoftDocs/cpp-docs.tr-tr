---
description: 'Daha fazla bilgi edinin: seçim sınıfı'
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
ms.openlocfilehash: a7597a3bd530185e316cdc42ebbc4696162d498f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254475"
---
# <a name="choice-class"></a>seçenek Sınıfı

`choice`İleti bloğu, bir kaynak kümesiyle denetim akışı etkileşimini temsil eden çok kaynaklı, tek hedef bir bloğudur. Seçim bloğu, birden fazla kaynağın bir ileti oluşturmasını ve iletiyi üreten kaynağın dizinini yaymasını bekler.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    class T
>
class choice: public ISource<size_t>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
`tuple`Giriş kaynaklarının yüklerini temsil eden tabanlı bir tür.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|İçin bir tür diğer adı `T` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[seçe](#ctor)|Fazla Yüklendi. `choice`İleti bloğu oluşturur.|
|[~ Choice yok edici](#dtor)|`choice`Mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ettiğinizde](#accept)|Bu blok tarafından sunulan `choice` ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[acquire_ref](#acquire_ref)|`choice`Silmeyi engellemek için bu mesajlaşma bloğunda bir başvuru sayısı alır.|
|[kullanan](#consume)|Bu mesajlaşma bloğunun daha önce sunduğu `choice` ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.|
|[has_value](#has_value)|Bu `choice` mesajlaşma bloğunun henüz bir değer ile başlatılmış olup olmadığını denetler.|
|[indeks](#index)|`tuple`İleti bloğu tarafından seçilen öğeyi temsil eden öğesine bir dizin döndürür `choice` .|
|[link_target](#link_target)|Bu mesajlaşma bloğuna bir hedef bloğu bağlar `choice` .|
|[Yayın](#release)|Önceki başarılı bir ileti ayırmasını serbest bırakır.|
|[release_ref](#release_ref)|Bu mesajlaşma bloğunda bir başvuru sayısı yayınlar `choice` .|
|[Rezerve et](#reserve)|Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `choice` .|
|[unlink_target](#unlink_target)|Bu mesajlaşma bloğundan bir hedef bloğunun bağlantısını kaldırır `choice` .|
|[unlink_targets](#unlink_targets)|Bu mesajlaşma bloğundan tüm hedeflerin bağlantısını kaldırır `choice` . ( [ISource:: unlink_targets](isource-class.md#unlink_targets)geçersiz kılar)|
|[değer](#value)|Dizini mesajlaşma bloğu tarafından seçilmiş olan iletiyi alır `choice` .|

## <a name="remarks"></a>Açıklamalar

Seçim bloğu, gelen iletilerden yalnızca birinin tüketilmesini sağlar.

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept"></a><a name="accept"></a> ettiğinizde

Bu blok tarafından sunulan `choice` ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `accept` .

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

## <a name="acquire_ref"></a><a name="acquire_ref"></a> acquire_ref

`choice`Silmeyi engellemek için bu mesajlaşma bloğunda bir başvuru sayısı alır.

```cpp
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `ITarget` , yöntemi sırasında bu kaynağa bağlanan bir nesne tarafından çağırılır `link_target` .

## <a name="choice"></a><a name="ctor"></a> seçe

`choice`İleti bloğu oluşturur.

```cpp
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
`tuple`Seçim için bir kaynak.

*_PScheduler*<br/>
`Scheduler` `choice` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne.

*_PScheduleGroup*<br/>
`ScheduleGroup` `choice` Mesajlaşma bloğunun yayma görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

*_Choice*<br/>
`choice`Kopyalamanın bir ileti bloğu. Özgün nesnenin yalnız bırakılmış olduğunu ve bunu bir taşıma Oluşturucusu yapmayı unutmayın.

### <a name="remarks"></a>Açıklamalar

Veya parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır `_PScheduler` `_PScheduleGroup` .

Taşıma işlemi bir kilit altında gerçekleştirilmez, bu, taşıma sırasında uçuş kapsamında hiçbir hafif görev olmadığından emin olmak için kullanıcıya ait olduğu anlamına gelir. Aksi takdirde, çok sayıda özel durum ortaya çıkabilir, bu durum istisnalara veya tutarsız duruma gelebilir.

## <a name="choice"></a><a name="dtor"></a> ~ Choice

`choice`Mesajlaşma bloğunu yok eder.

```cpp
~choice();
```

## <a name="consume"></a><a name="consume"></a> kullanan

Bu mesajlaşma bloğunun daha önce sunduğu `choice` ve hedefi tarafından başarıyla ayrılmış olan bir iletiyi tüketir ve sahipliği çağırana aktarmıştır.

```cpp
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

## <a name="has_value"></a><a name="has_value"></a> has_value

Bu `choice` mesajlaşma bloğunun henüz bir değer ile başlatılmış olup olmadığını denetler.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** blok bir değer aldıysa, **`false`** tersi durumda.

## <a name="index"></a><a name="index"></a> indeks

`tuple`İleti bloğu tarafından seçilen öğeyi temsil eden öğesine bir dizin döndürür `choice` .

```cpp
size_t index();
```

### <a name="return-value"></a>Dönüş Değeri

İleti dizini.

### <a name="remarks"></a>Açıklamalar

İleti yükü yöntemi kullanılarak ayıklanabilir `get` .

## <a name="link_target"></a><a name="link_target"></a> link_target

Bu mesajlaşma bloğuna bir hedef bloğu bağlar `choice` .

```cpp
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
`ITarget`Bu mesajlaşma bloğuna bağlanacak bloğa yönelik bir işaretçi `choice` .

## <a name="release"></a><a name="release"></a> Yayın

Önceki başarılı bir ileti ayırmasını serbest bırakır.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` `message` Serbest bırakılmakta olan nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `release` .

## <a name="release_ref"></a><a name="release_ref"></a> release_ref

Bu mesajlaşma bloğunda bir başvuru sayısı yayınlar `choice` .

```cpp
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `ITarget` Bu kaynaktan bağlantısı kesilmekte olan bir nesne tarafından çağırılır. Kaynak bloğunun hedef blok için ayrılan kaynakları serbest bırakmaya izin verilir.

## <a name="reserve"></a><a name="reserve"></a> ayırmaya

Bu mesajlaşma bloğu tarafından daha önce sunulan bir iletiyi ayırır `choice` .

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

## <a name="unlink_target"></a><a name="unlink_target"></a> unlink_target

Bu mesajlaşma bloğundan bir hedef bloğunun bağlantısını kaldırır `choice` .

```cpp
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
`ITarget`Bu mesajlaşma bloğunun bağlantısını kaldırmak için bir blok işaretçisi `choice` .

## <a name="unlink_targets"></a><a name="unlink_targets"></a> unlink_targets

Bu mesajlaşma bloğundan tüm hedeflerin bağlantısını kaldırır `choice` .

```cpp
virtual void unlink_targets();
```

### <a name="remarks"></a>Açıklamalar

İç bloğun yıkıcısı doğru şekilde kaldırılacak olduğundan, bu yöntemin yıkıcıdan çağrılması gerekmez `single_assignment` .

## <a name="value"></a><a name="value"></a> deeri

Dizini mesajlaşma bloğu tarafından seçilmiş olan iletiyi alır `choice` .

```cpp
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>Parametreler

*_Payload_type*<br/>
İleti yükünün türü.

### <a name="return-value"></a>Dönüş Değeri

İleti yükü.

### <a name="remarks"></a>Açıklamalar

`choice`İleti bloğu farklı yük türlerine sahip girişler götürebildiğinden, yük alma noktasındaki yükün türünü belirtmeniz gerekir. Yöntemin sonucuna göre türü belirleyebilirsiniz `index` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[JOIN sınıfı](join-class.md)<br/>
[single_assignment sınıfı](single-assignment-class.md)
