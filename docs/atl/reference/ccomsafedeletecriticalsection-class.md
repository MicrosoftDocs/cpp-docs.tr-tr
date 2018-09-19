---
title: CComSafeDeleteCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
dev_langs:
- C++
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b9c82f1d9b4b1a46d134b94842fffe56f457afa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118647"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection sınıfı

Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|Oluşturucu.|
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::Init](#init)|Oluşturur ve kritik bölüm nesnesi başlatır.|
|[CComSafeDeleteCriticalSection::Lock](#lock)|Kritik bölüm nesne sahipliğini alır.|
|[CComSafeDeleteCriticalSection::Term](#term)|Kritik bölüm nesne tarafından kullanılan sistem kaynaklarını serbest bırakır.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_bInitialized](#m_binitialized)|Bayrakları olmadığını iç `CRITICAL_SECTION` nesne başlatıldı.|

## <a name="remarks"></a>Açıklamalar

`CComSafeDeleteCriticalSection` sınıfından türetilen [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Ancak, `CComSafeDeleteCriticalSection` üzerinden ek güvenlik mekanizmaları sağlar [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).

Örneği `CComSafeDeleteCriticalSection` kapsamın dışına çıkıncaya veya açıkça hala geçerliyse bellekten silinir, kritik bölüm nesnesini otomatik olarak temizlenir. Ayrıca, [CComSafeDeleteCriticalSection::Term](#term) yöntemi kritik bölüm nesnesini henüz atanmamış veya bellekten piyasaya Sürüldü düzgün bir şekilde çıkılacak.

Bkz: [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) kritik bölüm yardımcı sınıfları hakkında daha fazla bilgi için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="ccomsafedeletecriticalsection"></a>  CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection

Oluşturucu.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

Kümeleri [m_bInitialized](#m_binitialized) veri üyesi false.

##  <a name="dtor"></a>  CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection

Yıkıcı.

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

İç sürümleri `CRITICAL_SECTION` bellekten nesne [m_bInitialized](#m_binitialized) veri üyesi, TRUE olarak ayarlanır.

##  <a name="init"></a>  CComSafeDeleteCriticalSection::Init

Temel sınıf uygulamasına çağırır [Init](/visualstudio/debugger/init) ve ayarlar [m_bInitialized](#m_binitialized) başarılı olursa TRUE.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init).

##  <a name="lock"></a>  CComSafeDeleteCriticalSection::Lock

Temel sınıf uygulamasına çağırır [kilit](ccomcriticalsection-class.md#lock).  

```
HRESULT Lock();
```

### <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

### <a name="remarks"></a>Açıklamalar

Bu yöntem varsayar [m_bInitialized](#m_binitialized) veri üyesi üzerinde giriş TRUE olarak ayarlanır. Bu condidtion karşılanmadığında onaylama, hata ayıklama yapılarında oluşturulur.

İşlev davranışını daha fazla bilgi için [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

##  <a name="m_binitialized"></a>  CComSafeDeleteCriticalSection::m_bInitialized

Bayrakları olmadığını iç `CRITICAL_SECTION` nesne başlatıldı.

```
bool m_bInitialized;
```

### <a name="remarks"></a>Açıklamalar

`m_bInitialized` Arka plandaki geçerlilik izlemek için kullanılan veri üyesi `CRITICAL_SECTION` ilişkili nesne [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) sınıfı. Arka plandaki `CRITICAL_SECTION` nesne değil deneneceğini bu bayrağı TRUE olarak ayarlanmazsa bellekten yayımlanacak.

##  <a name="term"></a>  CComSafeDeleteCriticalSection::Term

Temel sınıf uygulamasına çağırır [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) , iç `CRITICAL_SECTION` nesne geçerlidir.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Sonucunu döndürür [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), veya S_OK varsa [m_bInitialized](#m_binitialized) giriş üzerinde FALSE olarak ayarlanmış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem olsa bile iç çağrılması güvenlidir `CRITICAL_SECTION` nesnesi geçerli değil. Bu sınıfın yok Edicisi varsa bu yöntemi çağırır [m_bInitialized](#m_binitialized) veri üyesi, TRUE olarak ayarlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
