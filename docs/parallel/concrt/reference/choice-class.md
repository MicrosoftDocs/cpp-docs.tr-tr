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
ms.openlocfilehash: 3e718d0d34580d3bf2f13937159e431134631218
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142212"
---
# <a name="choice-class"></a>seçenek Sınıfı

`choice` mesajlaşma bloğu, bir kaynak kümesiyle denetim akışı etkileşimini temsil eden çok kaynaklı, tek hedef bir bloğudur. Seçim bloğu, birden fazla kaynağın bir ileti oluşturmasını ve iletiyi üreten kaynağın dizinini yaymasını bekler.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    class T
>
class choice: public ISource<size_t>;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Giriş kaynaklarının yüklerini temsil eden `tuple`tabanlı bir tür.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`type`|`T`için bir tür diğer adı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[seçe](#ctor)|Fazla Yüklendi. `choice` mesajlaşma bloğu oluşturur.|
|[~ Choice yok edici](#dtor)|`choice` mesajlaşma bloğunu yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ettiğinizde](#accept)|Bu `choice` bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.|
|[acquire_ref](#acquire_ref)|Silmeyi engellemek için bu `choice` mesajlaşma bloğunda bir başvuru sayısı alır.|
|[kullanan](#consume)|Daha önce bu `choice` mesajlaşma bloğunun sunduğu ve hedef tarafından başarıyla ayrılmış olan bir ileti tüketir ve bu, sahipliği çağırana aktarılarak.|
|[has_value](#has_value)|Bu `choice` mesajlaşma bloğunun henüz bir değer ile başlatılmış olup olmadığını denetler.|
|[indeks](#index)|`choice` mesajlaşma bloğunun seçtiği öğeyi temsil eden `tuple` bir dizin döndürür.|
|[link_target](#link_target)|Hedef bloğu bu `choice` mesajlaşma bloğuna bağlar.|
|[Yayın](#release)|Önceki başarılı bir ileti ayırmasını serbest bırakır.|
|[release_ref](#release_ref)|Bu `choice` mesajlaşma bloğunda bir başvuru sayısı yayınlar.|
|[ayırmaya](#reserve)|Daha önce bu `choice` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.|
|[unlink_target](#unlink_target)|Hedef bloğunun bu `choice` mesajlaşma bloğundan bağlantısını kaldırır.|
|[unlink_targets](#unlink_targets)|Bu `choice` mesajlaşma bloğundan tüm hedeflerin bağlantısını kaldırır. ( [ISource:: unlink_targets](isource-class.md#unlink_targets)geçersiz kılar)|
|[value](#value)|`choice` mesajlaşma bloğu tarafından dizini seçilmiş olan iletiyi alır.|

## <a name="remarks"></a>Açıklamalar

Seçim bloğu, gelen iletilerden yalnızca birinin tüketilmesini sağlar.

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept"></a>ettiğinizde

Bu `choice` bloğu tarafından sunulan ve sahipliği çağırana aktaran bir iletiyi kabul eder.

```cpp
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`accept` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

## <a name="acquire_ref"></a>acquire_ref

Silmeyi engellemek için bu `choice` mesajlaşma bloğunda bir başvuru sayısı alır.

```cpp
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `link_target` yöntemi sırasında bu kaynağa bağlanmakta olan bir `ITarget` nesnesi tarafından çağırılır.

## <a name="ctor"></a>seçe

`choice` mesajlaşma bloğu oluşturur.

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
Seçim için kaynakların `tuple`.

*_PScheduler*<br/>
`choice` mesajlaşma bloğunun yayma görevinin içinde `Scheduler` nesnesi zamanlandı.

*_PScheduleGroup*<br/>
`choice` mesajlaşma bloğunun yayma görevinin içinde `ScheduleGroup` nesnesi zamanlandı. Kullanılan `Scheduler` nesnesi, zamanlama grubu tarafından kapsanıyor.

*_Choice*<br/>
Kopyalamanın `choice` bir mesajlaşma bloğu. Özgün nesnenin yalnız bırakılmış olduğunu ve bunu bir taşıma Oluşturucusu yapmayı unutmayın.

### <a name="remarks"></a>Açıklamalar

`_PScheduler` veya `_PScheduleGroup` parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır.

Taşıma işlemi bir kilit altında gerçekleştirilmez, bu, taşıma sırasında uçuş kapsamında hiçbir hafif görev olmadığından emin olmak için kullanıcıya ait olduğu anlamına gelir. Aksi takdirde, çok sayıda özel durum ortaya çıkabilir, bu durum istisnalara veya tutarsız duruma gelebilir.

## <a name="dtor"></a>~ Choice

`choice` mesajlaşma bloğunu yok eder.

```cpp
~choice();
```

## <a name="consume"></a>kullanan

Daha önce bu `choice` mesajlaşma bloğunun sunduğu ve hedef tarafından başarıyla ayrılmış olan bir ileti tüketir ve bu, sahipliği çağırana aktarılarak.

```cpp
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

## <a name="has_value"></a>has_value

Bu `choice` mesajlaşma bloğunun henüz bir değer ile başlatılmış olup olmadığını denetler.

```cpp
bool has_value() const;
```

### <a name="return-value"></a>Dönüş Değeri

blok bir değer aldıysa **true** , aksi takdirde **false** .

## <a name="index"></a>indeks

`choice` mesajlaşma bloğunun seçtiği öğeyi temsil eden `tuple` bir dizin döndürür.

```cpp
size_t index();
```

### <a name="return-value"></a>Dönüş Değeri

İleti dizini.

### <a name="remarks"></a>Açıklamalar

İleti yükü `get` yöntemi kullanılarak ayıklanabilir.

## <a name="link_target"></a>link_target

Hedef bloğu bu `choice` mesajlaşma bloğuna bağlar.

```cpp
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu `choice` mesajlaşma bloğuna bağlantı için `ITarget` bloğuna yönelik bir işaretçi.

## <a name="release"></a>Yayın

Önceki başarılı bir ileti ayırmasını serbest bırakır.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Yayımlanmakta olan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`release` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

## <a name="release_ref"></a>release_ref

Bu `choice` mesajlaşma bloğunda bir başvuru sayısı yayınlar.

```cpp
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu kaynaktan bağlantısı kesilmekte olan bir `ITarget` nesnesi tarafından çağırılır. Kaynak bloğunun hedef blok için ayrılan kaynakları serbest bırakmaya izin verilir.

## <a name="reserve"></a>ayırmaya

Daha önce bu `choice` mesajlaşma bloğunun sunduğu bir iletiyi ayırır.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`reserve` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

ileti başarıyla ayrıldıysa **true** , aksi takdirde **false** . Ayırmalar, aşağıdakiler dahil olmak üzere birçok nedenden dolayı başarısız olabilir: ileti zaten ayrılmış veya başka bir hedef tarafından kabul edildi, kaynak rezervasyonları reddedebilir ve bu şekilde devam eder.

### <a name="remarks"></a>Açıklamalar

`reserve`çağırdıktan sonra, başarılı olduysa, iletinin sahipliğini almak ya da sağlamak için `consume` veya `release` çağırmanız gerekir.

## <a name="unlink_target"></a>unlink_target

Hedef bloğunun bu `choice` mesajlaşma bloğundan bağlantısını kaldırır.

```cpp
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu `choice` mesajlaşma bloğundan bağlantısını kaldırmak için `ITarget` bloğuna yönelik bir işaretçi.

## <a name="unlink_targets"></a>unlink_targets

Bu `choice` mesajlaşma bloğundan tüm hedeflerin bağlantısını kaldırır.

```cpp
virtual void unlink_targets();
```

### <a name="remarks"></a>Açıklamalar

İç `single_assignment` bloğunun yıkıcısı doğru şekilde kaldırılacak olduğundan, bu yöntemin yıkıcıdan çağrılması gerekmez.

## <a name="value"></a>deeri

`choice` mesajlaşma bloğu tarafından dizini seçilmiş olan iletiyi alır.

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

İletinin yükü.

### <a name="remarks"></a>Açıklamalar

`choice` mesajlaşma bloğu farklı yük türlerine sahip girişler götürebildiğinden, yük alma noktasındaki yükün türünü belirtmeniz gerekir. `index` yönteminin sonucuna göre türü belirleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[join Sınıfı](join-class.md)<br/>
[single_assignment Sınıfı](single-assignment-class.md)
