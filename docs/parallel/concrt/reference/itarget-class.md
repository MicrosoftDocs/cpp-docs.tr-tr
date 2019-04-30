---
title: ITarget Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
ms.openlocfilehash: 59a0f66a0ba3b10c3307a835ff6ccaa216596538
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339543"
---
# <a name="itarget-class"></a>ITarget Sınıfı

`ITarget` Tüm hedef blokları için sınıf, arabirim. Hedef blokları tarafından kendilerine sunulan iletileri kullanma `ISource` engeller.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ITarget;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Akıştaki yükün bir hedef bloğu tarafından kabul iletileri veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`filter_method`|Döndüren bloğu tarafından kullanılan herhangi bir yöntem imzası bir `bool` sunulan bir iletiye kabul edilip edilmeyeceğini belirlemek için değer.|
|`type`|Bir tür diğer adı için `T`.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ Itarget yok Edicisi](#dtor)|Yok eder `ITarget` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Yay](#propagate)|Zaman uyumsuz olarak türetilen bir sınıfta geçersiz kılındığında, bir ileti bir kaynak bloktaki bu hedef bloğa aktarır.|
|[Gönder](#send)|Zaman uyumlu olarak türetilen bir sınıfta geçersiz kılındığında, bir ileti hedef bloğa aktarır.|
|[supports_anonymous_source](#supports_anonymous_source)|Türetilen bir sınıfta geçersiz kılındığında, true veya false ileti bloğu kendisine bağlı olmayan bir kaynak tarafından sunulan iletileri kabul edip etmemesine bağlı olarak döndürür. Geçersiz kılınan yöntemi döndürürse **true**, ertelenmiş bir iletiyi kullanımını daha sonra kendi sourse bağlantı kayıt defterinde tanımlanması için kaynak olarak sunulan bir iletiye hedef erteleyemiyor.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[link_source](#link_source)|Türetilen bir sınıfta geçersiz kılındığında, belirtilen kaynak bloğu için bağlantı `ITarget` blok.|
|[unlink_source](#unlink_source)|Türetilen bir sınıfta geçersiz kılındığında, bu bir belirtilen kaynak blok olan bağlantısını kesen `ITarget` blok.|
|[unlink_sources](#unlink_sources)|Türetilen bir sınıfta geçersiz kılındığında, bu tüm kaynak bloklardan olan bağlantısını kesen `ITarget` blok.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [zaman uyumsuz ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITarget`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> ~ Itarget

Yok eder `ITarget` nesne.

```
virtual ~ITarget();
```

##  <a name="link_source"></a> link_source

Türetilen bir sınıfta geçersiz kılındığında, belirtilen kaynak bloğu için bağlantı `ITarget` blok.

```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
`ISource` Engellemek için bu bağlantı kurulan `ITarget` blok.

### <a name="remarks"></a>Açıklamalar

Bu işlev üzerinde doğrudan çağrılmamalıdır bir `ITarget` blok. Blokları kullanarak birbirine bağlanması `link_target` metodunda `ISource` çağıracağı blokları, `link_source` karşılık gelen hedef yöntemi.

##  <a name="propagate"></a> Yay

Zaman uyumsuz olarak türetilen bir sınıfta geçersiz kılındığında, bir ileti bir kaynak bloktaki bu hedef bloğa aktarır.

```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) ya da özel durum `_PMessage` veya `_PSource` parametresi `NULL`.

##  <a name="send"></a> Gönder

Zaman uyumlu olarak türetilen bir sınıfta geçersiz kılındığında, bir ileti hedef bloğa aktarır.

```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Bir işaretçi `message` nesne.

*_PSource*<br/>
İletiyi sunmayı kaynak blok için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

A [message_status](concurrency-namespace-enums.md) hedef iletinin yapmak karar göstergesi.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_argument](../../../standard-library/invalid-argument-class.md) ya da özel durum `_PMessage` veya `_PSource` parametresi `NULL`.

Kullanarak `send` yöntemi dışında iletisi başlatma ve iletileri bir ağdaki yayılması tehlikelidir ve kilitlenmesine yol açabilir.

Zaman `send` ileti algıladı ya da zaten kabul edildi ve hedef blok aktarılan veya hedef tarafından reddedilen döndürür.

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

Türetilen bir sınıfta geçersiz kılındığında, true veya false ileti bloğu kendisine bağlı olmayan bir kaynak tarafından sunulan iletileri kabul edip etmemesine bağlı olarak döndürür. Geçersiz kılınan yöntemi döndürürse **true**, ertelenmiş bir iletiyi kullanımını daha sonra kendi sourse bağlantı kayıt defterinde tanımlanması için kaynak olarak sunulan bir iletiye hedef erteleyemiyor.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** blok iletiyi kendisine bağlı olmayan bir kaynaktan kabul edebiliyorsa **false** Aksi takdirde.

##  <a name="unlink_source"></a> unlink_source

Türetilen bir sınıfta geçersiz kılındığında, bu bir belirtilen kaynak blok olan bağlantısını kesen `ITarget` blok.

```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
`ISource` Bu ayrılmış block `ITarget` blok.

### <a name="remarks"></a>Açıklamalar

Bu işlev üzerinde doğrudan çağrılmamalıdır bir `ITarget` blok. Blokları bağlantısı kullanarak `unlink_target` veya `unlink_targets` yöntemlerde `ISource` çağıracağı blokları, `unlink_source` karşılık gelen hedef yöntemi.

##  <a name="unlink_sources"></a> unlink_sources

Türetilen bir sınıfta geçersiz kılındığında, bu tüm kaynak bloklardan olan bağlantısını kesen `ITarget` blok.

```
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ISource Sınıfı](isource-class.md)
