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
ms.openlocfilehash: a9ef9990db6376536f2f2a15c053b3b1d4ed12cf
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139313"
---
# <a name="isource-class"></a>ISource Sınıfı

`ISource` sınıfı tüm kaynak blokları için arabirimidir. Kaynak blokları iletileri `ITarget` bloklara yayar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class ISource;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Kaynak bloğu tarafından üretilen iletiler içindeki yükün veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`source_type`|`T`için bir tür diğer adı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ ISource yok edici](#dtor)|`ISource` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ettiğinizde](#accept)|Türetilmiş bir sınıfta geçersiz kılındığında, bu `ISource` bloğu tarafından sunulan bir iletiyi kabul eder ve sahipliği çağırana aktarmaz.|
|[acquire_ref](#acquire_ref)|Türetilmiş bir sınıfta geçersiz kılınırsa, silme işlemini engellemek için bu `ISource` bloğunda bir başvuru sayısı elde edin.|
|[kullanan](#consume)|Türetilmiş bir sınıfta geçersiz kılındığında, daha önce bu `ISource` bloğu tarafından sunulan ve hedefi tarafından başarıyla ayrılmış bir ileti kullanır ve sahipliği çağırana aktarmaz.|
|[link_target](#link_target)|Türetilmiş bir sınıfta geçersiz kılınırsa, hedef bloğu bu `ISource` bloğuna bağlar.|
|[Yayın](#release)|Türetilmiş bir sınıfta geçersiz kılınırsa, önceki başarılı ileti ayırmasını yayınlar.|
|[release_ref](#release_ref)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu `ISource` bloğunda bir başvuru sayısı yayınlar.|
|[ayırmaya](#reserve)|Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce bu `ISource` bloğu tarafından sunulan bir iletiyi ayırır.|
|[unlink_target](#unlink_target)|Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce bağlanmış olması halinde bu `ISource` bloğundan bir hedef bloğunun bağlantısını kaldırır.|
|[unlink_targets](#unlink_targets)|Türetilmiş bir sınıfta geçersiz kılınırsa, tüm hedef blokların bu `ISource` bloğundan bağlantısını kaldırır.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="accept"></a>ettiğinizde

Türetilmiş bir sınıfta geçersiz kılındığında, bu `ISource` bloğu tarafından sunulan bir iletiyi kabul eder ve sahipliği çağırana aktarmaz.

```cpp
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`accept` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çağıranın artık sahipliği olan iletinin bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu `ISource` bloğu tarafından bir ileti sunulduğunda `accept` yöntemi bir hedef tarafından çağırılır. Döndürülen ileti işaretçisi, bu kaynak iletinin bir kopyasını oluşturmak için karar verirse, `ITarget` bloğunun `propagate` metoduna geçirilen yöntemden farklı olabilir.

## <a name="acquire_ref"></a>acquire_ref

Türetilmiş bir sınıfta geçersiz kılınırsa, silme işlemini engellemek için bu `ISource` bloğunda bir başvuru sayısı elde edin.

```cpp
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `link_target` yöntemi sırasında bu kaynağa bağlanmakta olan bir `ITarget` nesnesi tarafından çağırılır.

## <a name="consume"></a>kullanan

Türetilmiş bir sınıfta geçersiz kılındığında, daha önce bu `ISource` bloğu tarafından sunulan ve hedefi tarafından başarıyla ayrılmış bir ileti kullanır ve sahipliği çağırana aktarmaz.

```cpp
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
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

## <a name="dtor"></a>~ ISource

`ISource` nesnesini yok eder.

```cpp
virtual ~ISource();
```

## <a name="link_target"></a>link_target

Türetilmiş bir sınıfta geçersiz kılınırsa, hedef bloğu bu `ISource` bloğuna bağlar.

```cpp
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Hedef bloğunun bu `ISource` bloğuna bağlanmakta olan bir işaretçisi.

## <a name="release"></a>Yayın

Türetilmiş bir sınıfta geçersiz kılınırsa, önceki başarılı ileti ayırmasını yayınlar.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Ayrılmış `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`release` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

## <a name="release_ref"></a>release_ref

Türetilmiş bir sınıfta geçersiz kılınırsa, bu `ISource` bloğunda bir başvuru sayısı yayınlar.

```cpp
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran hedef bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bu kaynaktan bağlantısı kesilmekte olan bir `ITarget` nesnesi tarafından çağırılır. Kaynak bloğunun hedef blok için ayrılan kaynakları serbest bırakmaya izin verilir.

## <a name="reserve"></a>ayırmaya

Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce bu `ISource` bloğu tarafından sunulan bir iletiyi ayırır.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
Sunulan `message` nesnesinin `runtime_object_identity`.

*_PTarget*<br/>
`reserve` yöntemini çağıran hedef bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

ileti başarıyla ayrıldıysa **true** , aksi takdirde **false** . Ayırmalar, aşağıdakiler dahil olmak üzere birçok nedenden dolayı başarısız olabilir: ileti zaten ayrılmış veya başka bir hedef tarafından kabul edildi, kaynak rezervasyonları reddedebilir ve bu şekilde devam eder.

### <a name="remarks"></a>Açıklamalar

`reserve`çağırdıktan sonra, başarılı olduysa, iletinin sahipliğini almak ya da sağlamak için `consume` veya `release` çağırmanız gerekir.

## <a name="unlink_target"></a>unlink_target

Türetilmiş bir sınıfta geçersiz kılınırsa, daha önce bağlanmış olması halinde bu `ISource` bloğundan bir hedef bloğunun bağlantısını kaldırır.

```cpp
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Hedef bloğunun bu `ISource` bloğundan bağlantısı kesilmekte olan bir işaretçisi.

## <a name="unlink_targets"></a>unlink_targets

Türetilmiş bir sınıfta geçersiz kılınırsa, tüm hedef blokların bu `ISource` bloğundan bağlantısını kaldırır.

```cpp
virtual void unlink_targets() = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ITarget Sınıfı](itarget-class.md)
