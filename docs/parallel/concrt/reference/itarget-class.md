---
description: 'Şu konuda daha fazla bilgi edinin: ITarget Sınıfı'
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
ms.openlocfilehash: 6a1e900fa67ac5ee72305f18679e7a0fc38a2386
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334406"
---
# <a name="itarget-class"></a>ITarget Sınıfı

`ITarget`Sınıfı tüm hedef bloklara yönelik arabirimdir. Hedef bloklar bunlara bloklar tarafından sunulan iletileri tüketir `ISource` .

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T>
class ITarget;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Hedef bloğunun kabul ettiği iletiler içindeki yükün veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`filter_method`|**`bool`** Sunulan bir iletinin kabul edilip edilmeyeceğini belirlemede bir değer döndüren blok tarafından kullanılan herhangi bir yöntemin imzası.|
|`type`|İçin bir tür diğer adı `T` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ IComparer yıkıcısı](#dtor)|Nesneyi yok eder `ITarget` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[aktarabilirsiniz](#propagate)|Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir iletiyi bu hedef bloğa bir kaynak bloğundan geçirir.|
|[Gönder](#send)|Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumlu olarak hedef bloğuna bir ileti geçirir.|
|[supports_anonymous_source](#supports_anonymous_source)|Türetilmiş bir sınıfta geçersiz kılınırsa, ileti bloğunun kendisine bağlı olmayan bir kaynak tarafından sunulan iletileri kabul edip etmediğine bağlı olarak true veya false değerini döndürür. Geçersiz kılınan Yöntem döndürüyorsa **`true`** , daha sonraki bir zamanda ertelenen iletinin tüketimi kaynağın kaynak bağlantısı kayıt defterinde tanımlanmasını gerektirdiğinden hedef, sunulan bir iletiyi erteleyemiyor.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[link_source](#link_source)|Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen kaynak bloğunu bu `ITarget` bloğa bağlar.|
|[unlink_source](#unlink_source)|Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen kaynak bloğunun bu bloğundan bağlantısını kaldırır `ITarget` .|
|[unlink_sources](#unlink_sources)|Türetilmiş bir sınıfta geçersiz kılınırsa, bu bloktaki tüm kaynak bloklarını kaldırır `ITarget` .|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz Ileti blokları](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ITarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="itarget"></a><a name="dtor"></a> ~ ITarget

Nesneyi yok eder `ITarget` .

```cpp
virtual ~ITarget();
```

## <a name="link_source"></a><a name="link_source"></a> link_source

Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen kaynak bloğunu bu `ITarget` bloğa bağlar.

```cpp
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
`ISource`Bu bloğa bağlanmakta olan blok `ITarget` .

### <a name="remarks"></a>Açıklamalar

Bu işlev doğrudan bir blok üzerinde çağrılmamalıdır `ITarget` . Bloklar, `link_target` `ISource` ilgili hedefte yöntemi çağıran bloklar üzerindeki yöntemi kullanılarak birbirine bağlanmalıdır `link_source` .

## <a name="propagate"></a><a name="propagate"></a> aktarabilirsiniz

Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir iletiyi bu hedef bloğa bir kaynak bloğundan geçirir.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

Ya da parametresi ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum `_PMessage` oluşturur `_PSource` `NULL` .

## <a name="send"></a><a name="send"></a> Gönder

Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumlu olarak hedef bloğuna bir ileti geçirir.

```cpp
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PMessage*<br/>
Nesneye yönelik bir işaretçi `message` .

*_PSource*<br/>
İletiyi sunan kaynak bloğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Hedefin iletiyle ne işe karar verdiği [message_status](concurrency-namespace-enums.md) göstergesi.

### <a name="remarks"></a>Açıklamalar

Ya da parametresi ise Yöntem [invalid_argument](../../../standard-library/invalid-argument-class.md) bir özel durum `_PMessage` oluşturur `_PSource` `NULL` .

`send`Yönteminin ileti başlatma dışında kullanılması ve iletileri bir ağ içinde yayılması tehlikelidir ve kilitlenmeye neden olabilir.

Döndürüldüğünde `send` , ileti zaten kabul edilmiştir ve hedef bloğa aktarılır ya da hedef tarafından reddedildi.

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a> supports_anonymous_source

Türetilmiş bir sınıfta geçersiz kılınırsa, ileti bloğunun kendisine bağlı olmayan bir kaynak tarafından sunulan iletileri kabul edip etmediğine bağlı olarak true veya false değerini döndürür. Geçersiz kılınan Yöntem döndürüyorsa **`true`** , daha sonraki bir zamanda ertelenen iletinin tüketimi kaynağın sourse bağlantı kayıt defterinde tanımlanmasını gerektirdiğinden hedef, sunulan bir iletiyi erteleyemiyor.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** blok, bu kaynağa bağlı olmayan bir kaynaktaki iletiyi kabul edebilir **`false`** .

## <a name="unlink_source"></a><a name="unlink_source"></a> unlink_source

Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen kaynak bloğunun bu bloğundan bağlantısını kaldırır `ITarget` .

```cpp
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parametreler

*_PSource*<br/>
`ISource`Bu bloktan bağlantısının kesilme `ITarget` .

### <a name="remarks"></a>Açıklamalar

Bu işlev doğrudan bir blok üzerinde çağrılmamalıdır `ITarget` . Blokları, `unlink_target` `unlink_targets` `ISource` ilgili hedefte yöntemi çağırmak için veya bloklarda yöntemler kullanılarak kesilmelidir `unlink_source` .

## <a name="unlink_sources"></a><a name="unlink_sources"></a> unlink_sources

Türetilmiş bir sınıfta geçersiz kılınırsa, bu bloktaki tüm kaynak bloklarını kaldırır `ITarget` .

```cpp
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[ISource Sınıfı](isource-class.md)
