---
title: Isource sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e53f8999b4559a221b335528ec20b6034de269d3
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162210"
---
# <a name="isource-class"></a>ISource Sınıfı

`ISource` Tüm kaynak bloklar için sınıf, arabirim. Kaynak bloklar yayma iletileri `ITarget` engeller.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ISource;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Akıştaki yükün kaynak blok tarafından üretilen iletileri veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`source_type`|Bir tür diğer adı için `T`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ Isource yok Edicisi](#dtor)|Yok eder `ISource` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kabul et](#accept)|Türetilen bir sınıfta geçersiz kılındığında, bu tarafından sunulan bir iletiyi kabul `ISource` engelleme, arayana sahipliğini aktarma.|
|[acquire_ref](#acquire_ref)|Türetilen bir sınıfta geçersiz kılındığında, bir başvuru sayısı bu edinme `ISource` silinmesini engellemek için bloğu.|
|[kullanma](#consume)|Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan iletiyi tüketir `ISource` engelleme ve çağırana sahipliğini aktarma hedefi, başarılı bir şekilde ayrılmıştır.|
|[link_target](#link_target)|Türetilen bir sınıfta geçersiz kılındığında, bir hedef bloğu için bağlantı `ISource` blok.|
|[Yayın](#release)|Türetilen bir sınıfta geçersiz kılındığında, bir önceki başarılı iletisi ayırma serbest bırakır.|
|[release_ref](#release_ref)|Türetilen bir sınıfta geçersiz kılındığında, bir başvuru sayısı bu sürümleri `ISource` blok.|
|[ayırma](#reserve)|Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir iletiyi ayırdıktan `ISource` blok.|
|[unlink_target](#unlink_target)|Türetilen bir sınıfta geçersiz kılındığında, bu hedef bloğun olan bağlantısını kesen `ISource` olursa engellemek daha önce bağlantı kurulacak bulunamadı.|
|[unlink_targets](#unlink_targets)|Türetilen bir sınıfta geçersiz kılındığında, bu tüm hedef bloklara olan bağlantısını kesen `ISource` blok.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISource`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="accept"></a> Kabul et

Türetilen bir sınıfta geçersiz kılındığında, bu tarafından sunulan bir iletiyi kabul `ISource` engelleme, arayana sahipliğini aktarma.

```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `accept` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Arayanın artık sahipliğini olan iletisi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`accept` Yöntemi, bir hedef tarafından çağrıldığında, bir ileti bu edilmeksizin sunulacaktır ancak `ISource` blok. İleti işaretçi döndürülen yöntemlere geçirilen olandan farklı olabilir `propagate` yöntemi `ITarget` iletinin bir kopyasını oluşturmak bu kaynak karar verirse, engelleyin.

##  <a name="acquire_ref"></a> acquire_ref

Türetilen bir sınıfta geçersiz kılındığında, bir başvuru sayısı bu edinme `ISource` silinmesini engellemek için bloğu.

```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran bir hedef blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran bir `ITarget` sırasında bu kaynağa bağlı nesnesi `link_target` yöntemi.

##  <a name="consume"></a> kullanma

Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan iletiyi tüketir `ISource` engelleme ve çağırana sahipliğini aktarma hedefi, başarılı bir şekilde ayrılmıştır.

```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
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

##  <a name="dtor"></a> ~ Isource

Yok eder `ISource` nesne.

```
virtual ~ISource();
```

##  <a name="link_target"></a> link_target

Türetilen bir sınıfta geçersiz kılındığında, bir hedef bloğu için bağlantı `ISource` blok.

```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Hedef blok için bağlantı kurulan bir işaretçiye `ISource` blok.

##  <a name="release"></a> Yayın

Türetilen bir sınıfta geçersiz kılındığında, bir önceki başarılı iletisi ayırma serbest bırakır.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Ayrılmış, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `release` yöntemi.

##  <a name="release_ref"></a> release_ref

Türetilen bir sınıfta geçersiz kılındığında, bir başvuru sayısı bu sürümleri `ISource` blok.

```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu yöntemi çağıran bir hedef blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran bir `ITarget` bu kaynaktan bağlantısız bir nesne. Kaynak blok için hedef blok ayrılmış tüm kaynakları serbest bırakmak için kullanılabilir.

##  <a name="reserve"></a> ayırma

Türetilen bir sınıfta geçersiz kılındığında, daha önce bu tarafından sunulan bir iletiyi ayırdıktan `ISource` blok.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_MsgId*<br/>
`runtime_object_identity` Sunulan, `message` nesne.

*_PTarget*<br/>
Çağıran bir hedef blok için işaretçi `reserve` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** ileti başarıyla ayrıldı, **false** Aksi takdirde. Ayırmalar dahil olmak üzere çeşitli nedenlerle başarısız olabilir: ileti zaten ayrılmış veya kaynak ayırmaları Reddet vb. başka bir hedef tarafından kabul.

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra `reserve`, başarılı olursa ya da çağırmalıdır `consume` veya `release` alabilir veya ileti, bir elinde sırasıyla vermek için.

##  <a name="unlink_target"></a> unlink_target

Türetilen bir sınıfta geçersiz kılındığında, bu hedef bloğun olan bağlantısını kesen `ISource` olursa engellemek daha önce bağlantı kurulacak bulunamadı.

```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu ayrılmış hedef blok için işaretçi `ISource` blok.

##  <a name="unlink_targets"></a> unlink_targets

Türetilen bir sınıfta geçersiz kılındığında, bu tüm hedef bloklara olan bağlantısını kesen `ISource` blok.

```
virtual void unlink_targets() = 0;
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ITarget Sınıfı](itarget-class.md)
