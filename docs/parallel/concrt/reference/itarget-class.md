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
ms.openlocfilehash: dc9eacad744536e640417a4ebf51b975bd05bcc7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142027"
---
# <a name="itarget-class"></a>ITarget Sınıfı

`ITarget` sınıfı tüm hedef blokların arabirimidir. Hedef bloklar, `ISource` blokları tarafından bunlara sunulan iletileri tüketir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class ITarget;
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Hedef bloğunun kabul ettiği iletiler içindeki yükün veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`filter_method`|Sunulan bir iletinin kabul edilip edilmeyeceğini tespit etmek için bir `bool` değeri döndüren blok tarafından kullanılan herhangi bir yöntemin imzası.|
|`type`|`T`için bir tür diğer adı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ IComparer yıkıcısı](#dtor)|`ITarget` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[aktarabilirsiniz](#propagate)|Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir iletiyi bu hedef bloğa bir kaynak bloğundan geçirir.|
|[Gönder](#send)|Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumlu olarak hedef bloğuna bir ileti geçirir.|
|[supports_anonymous_source](#supports_anonymous_source)|Türetilmiş bir sınıfta geçersiz kılınırsa, ileti bloğunun kendisine bağlı olmayan bir kaynak tarafından sunulan iletileri kabul edip etmediğine bağlı olarak true veya false değerini döndürür. Geçersiz kılınan yöntem **true**değerini döndürürse, daha sonraki bir zamanda ertelenmiş bir iletinin tüketimi kaynağın kaynak bağlantısı kayıt defterinde tanımlanmasını gerektirdiğinden hedef, sunulan bir iletiyi erteleyemiyor.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[link_source](#link_source)|Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen kaynak bloğunu bu `ITarget` bloğuna bağlar.|
|[unlink_source](#unlink_source)|Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen kaynak bloğunun bu `ITarget` bloğundan bağlantısını kaldırır.|
|[unlink_sources](#unlink_sources)|Türetilmiş bir sınıfta geçersiz kılınırsa, tüm kaynak bloklarından Bu `ITarget` bloğundan bağlantıyı kaldırır.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="dtor"></a>~ ITarget

`ITarget` nesnesini yok eder.

```cpp
virtual ~ITarget();
```

## <a name="link_source"></a>link_source

Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen kaynak bloğunu bu `ITarget` bloğuna bağlar.

```cpp
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
`ISource` bloğu bu `ITarget` bloğuna bağlanmakta.

### <a name="remarks"></a>Açıklamalar

Bu işlev doğrudan bir `ITarget` bloğunda çağrılmamalıdır. Bloklar, ilgili hedefte `link_source` yöntemini çağıracak `ISource` blokları üzerinde `link_target` yöntemi kullanılarak birbirine bağlanmalıdır.

## <a name="propagate"></a>aktarabilirsiniz

Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir iletiyi bu hedef bloğa bir kaynak bloğundan geçirir.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

`_PMessage` veya `_PSource` parametresi `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

## <a name="send"></a>Gönder

Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumlu olarak hedef bloğuna bir ileti geçirir.

```cpp
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
`message` nesnesine yönelik bir işaretçi.

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

`_PMessage` veya `_PSource` parametresi `NULL`ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum oluşturur.

`send` yönteminin ileti başlatma dışında kullanılması ve iletilerin bir ağ içinde yayılması tehlikelidir ve kilitlenmeye yol açabilir.

`send` döndürüldüğünde ileti zaten kabul edilmiştir ve hedef bloğa aktarılır ya da hedef tarafından reddedildi.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Türetilmiş bir sınıfta geçersiz kılınırsa, ileti bloğunun kendisine bağlı olmayan bir kaynak tarafından sunulan iletileri kabul edip etmediğine bağlı olarak true veya false değerini döndürür. Geçersiz kılınan yöntem **true**değerini döndürürse, daha sonraki bir zamanda ertelenen iletinin tüketimi kaynağın sourse bağlantı kayıt defterinde tanımlanmasını gerektirdiğinden hedef, sunulan bir iletiyi erteleyemiyor.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

blok, onunla bağlantılı olmayan bir kaynaktan ileti kabul edebiliyorsa **true** , aksi takdirde **false** .

## <a name="unlink_source"></a>unlink_source

Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen kaynak bloğunun bu `ITarget` bloğundan bağlantısını kaldırır.

```cpp
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
`ISource` bloğunun bu `ITarget` bloğundan bağlantısının kesilme.

### <a name="remarks"></a>Açıklamalar

Bu işlev doğrudan bir `ITarget` bloğunda çağrılmamalıdır. Blokları `ISource` blokları üzerinde `unlink_target` veya `unlink_targets` yöntemleri kullanılarak kesilmelidir, bu da ilgili hedefte `unlink_source` yöntemini çağırır.

## <a name="unlink_sources"></a>unlink_sources

Türetilmiş bir sınıfta geçersiz kılınırsa, tüm kaynak bloklarından Bu `ITarget` bloğundan bağlantıyı kaldırır.

```cpp
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ISource Sınıfı](isource-class.md)
