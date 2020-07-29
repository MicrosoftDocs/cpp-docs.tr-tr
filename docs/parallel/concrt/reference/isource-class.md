---
title: ISource Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
ms.openlocfilehash: df592e965b436ed5a1d60702f9e57088887d5a94
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222712"
---
# <a name="isource-class"></a>ISource Sınıfı

`ISource`Sınıfı, tüm kaynak blokları için arabirimidir. Kaynak blokları iletileri `ITarget` bloklara yayar.

## <a name="syntax"></a>Söz dizimi

```cpp
template<class T>
class ISource;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Kaynak bloğu tarafından üretilen iletiler içindeki yükün veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`source_type`|İçin bir tür diğer adı `T` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ ISource yok edici](#dtor)|Nesneyi yok eder `ISource` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ettiğinizde](#accept)|Türetilmiş bir sınıfta geçersiz kılındığında, bu blok tarafından sunulan bir iletiyi kabul eder `ISource` ve sahipliği çağırana aktarmaz.|
|[acquire_ref](#acquire_ref)|Türetilmiş bir sınıfta geçersiz kılınırsa, silme işlemini engellemek için bu blok üzerinde bir başvuru sayısı elde edin `ISource` .|
|[kullanan](#consume)|Türetilmiş bir sınıfta geçersiz kılındığında, bu blok tarafından daha önce sunulan `ISource` ve hedef tarafından başarıyla ayrılmış bir ileti kullanır ve sahipliği çağırana aktarılarak.|
|[link_target](#link_target)|Türetilmiş bir sınıfta geçersiz kılınırsa, hedef bloğu bu `ISource` bloğa bağlar.|
|[Yayın](#release)|Türetilmiş bir sınıfta geçersiz kılınırsa, önceki başarılı ileti ayırmasını yayınlar.|
|[release_ref](#release_ref)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu blok üzerinde bir başvuru sayısı yayınlar `ISource` .|
|[Rezerve et](#reserve)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu blok tarafından daha önce sunulan bir iletiyi ayırır `ISource` .|
|[unlink_target](#unlink_target)|Türetilmiş bir sınıfta geçersiz `ISource` kılınırsa, daha önceden bağlanacak şekilde bulunursa, bu bloktaki hedef bloğunun bağlantısını kaldırır.|
|[unlink_targets](#unlink_targets)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu bloktaki tüm hedef blokların bağlantısını kaldırır `ISource` .|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept"></a><a name="accept"></a>ettiğinizde

Türetilmiş bir sınıfta geçersiz kılındığında, bu blok tarafından sunulan bir iletiyi kabul eder `ISource` ve sahipliği çağırana aktarmaz.

```cpp
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `accept` .

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

`accept`Bu blok tarafından bir ileti sunulduğunda yöntemi bir hedef tarafından çağırılır `ISource` . Döndürülen ileti işaretçisi, `propagate` `ITarget` Bu kaynak iletinin bir kopyasını oluşturmak için karar verirse, bloğun yöntemine geçirilen yöntemden farklı olabilir.

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

Türetilmiş bir sınıfta geçersiz kılınırsa, silme işlemini engellemek için bu blok üzerinde bir başvuru sayısı elde edin `ISource` .

```cpp
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `ITarget` , yöntemi sırasında bu kaynağa bağlanan bir nesne tarafından çağırılır `link_target` .

## <a name="consume"></a><a name="consume"></a>kullanan

Türetilmiş bir sınıfta geçersiz kılındığında, bu blok tarafından daha önce sunulan `ISource` ve hedef tarafından başarıyla ayrılmış bir ileti kullanır ve sahipliği çağırana aktarılarak.

```cpp
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
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

## <a name="isource"></a><a name="dtor"></a>~ ISource

Nesneyi yok eder `ISource` .

```cpp
virtual ~ISource();
```

## <a name="link_target"></a><a name="link_target"></a>link_target

Türetilmiş bir sınıfta geçersiz kılınırsa, hedef bloğu bu `ISource` bloğa bağlar.

```cpp
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Hedef bloğunun bu bloğa bağlanmakta olan bir işaretçisi `ISource` .

## <a name="release"></a><a name="release"></a>Yayın

Türetilmiş bir sınıfta geçersiz kılınırsa, önceki başarılı ileti ayırmasını yayınlar.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Ayrılan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `release` .

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

Türetilmiş bir sınıfta geçersiz kılınırsa, bu blok üzerinde bir başvuru sayısı yayınlar `ISource` .

```cpp
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `ITarget` Bu kaynaktan bağlantısı kesilmekte olan bir nesne tarafından çağırılır. Kaynak bloğunun hedef blok için ayrılan kaynakları serbest bırakmaya izin verilir.

## <a name="reserve"></a><a name="reserve"></a>ayırmaya

Türetilmiş bir sınıfta geçersiz kılınırsa, bu blok tarafından daha önce sunulan bir iletiyi ayırır `ISource` .

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity`Sunulan `message` nesne.

*_PTarget*<br/>
Yöntemi çağıran hedef bloğa yönelik bir işaretçi `reserve` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** ileti başarıyla ayrıldıysa, **`false`** tersi durumda. Ayırmalar, aşağıdakiler dahil olmak üzere birçok nedenden dolayı başarısız olabilir: ileti zaten ayrılmış veya başka bir hedef tarafından kabul edildi, kaynak rezervasyonları reddedebilir ve bu şekilde devam eder.

### <a name="remarks"></a>Açıklamalar

Öğesini çağırdıktan sonra, başarılı olursa, `reserve` `consume` `release` sırasıyla iletinin sahipliğini almak veya vermek için ya da ' i çağırmanız gerekir.

## <a name="unlink_target"></a><a name="unlink_target"></a>unlink_target

Türetilmiş bir sınıfta geçersiz `ISource` kılınırsa, daha önceden bağlanacak şekilde bulunursa, bu bloktaki hedef bloğunun bağlantısını kaldırır.

```cpp
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Hedef bloğunun Bu bloktan bağlantısının kesilmekte olan bir işaretçisi `ISource` .

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

Türetilmiş bir sınıfta geçersiz kılınırsa, bu bloktaki tüm hedef blokların bağlantısını kaldırır `ISource` .

```cpp
virtual void unlink_targets() = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[IComparer sınıfı](itarget-class.md)
