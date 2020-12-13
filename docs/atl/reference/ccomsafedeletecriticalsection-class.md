---
description: 'Daha fazla bilgi edinin: Ccomsafedeletekritiksection sınıfı'
title: Ccomsafedeletekritiksection sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
ms.openlocfilehash: 73e27fb267cbfc8cde248c7ac896d29de2a91f77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142175"
---
# <a name="ccomsafedeletecriticalsection-class"></a>Ccomsafedeletekritiksection sınıfı

Bu sınıf, kritik bir bölüm nesnesinin sahipliğini almak ve serbest bırakmak için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Ccomsafedeletekritiksection:: Ccomsafedeletecriticalhandle bölümü](#ccomsafedeletecriticalsection)|Oluşturucu.|
|[Ccomsafedeletecriticalhandle bölümü:: ~ Ccomsafedeletekritiksection](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ccomsafedeletecriticalhandle bölümü:: Init](#init)|Kritik bir bölüm nesnesi oluşturur ve başlatır.|
|[Ccomsafedeletekritiksection:: Lock](#lock)|Kritik bölüm nesnesinin sahipliğini edinir.|
|[Ccomsafedeletecriticalhandle bölümü:: Term](#term)|Kritik bölüm nesnesi tarafından kullanılan sistem kaynaklarını serbest bırakır.|

### <a name="data-members"></a>Veri üyeleri

|Veri üyesi|Açıklama|
|-|-|
|[m_bInitialized](#m_binitialized)|İç nesnenin başlatılmış olup olmadığını işaretler `CRITICAL_SECTION` .|

## <a name="remarks"></a>Açıklamalar

`CComSafeDeleteCriticalSection`[Ccomkritiksection](../../atl/reference/ccomcriticalsection-class.md)sınıfından türetilir. Ancak, `CComSafeDeleteCriticalSection` [Ccomcriticalhandle bölümü](../../atl/reference/ccomcriticalsection-class.md)üzerinde ek güvenlik mekanizmaları sağlar.

Bir örneği `CComSafeDeleteCriticalSection` kapsam dışına geçtiğinde veya bellekten açıkça silindiğinde, temel alınan kritik bölüm nesnesi hala geçerliyse otomatik olarak temizlenir. Ayrıca, temel alınan kritik bölüm nesnesi henüz ayrılmadıysa veya bellekten zaten serbest bırakılmışsa [Ccomsafedeletecriticalhandle bölümü:: Term](#term) yöntemi sorunsuz bir şekilde çıkış olur.

Kritik bölüm yardımcı sınıfları hakkında daha fazla bilgi için bkz. [Ccomcriticalhandle bölümü](../../atl/reference/ccomcriticalsection-class.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Ccomcriticalhandle bölümü](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a> Ccomsafedeletekritiksection:: Ccomsafedeletecriticalhandle bölümü

Oluşturucu.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

[M_bInitialized](#m_binitialized) VERI üyesini false olarak ayarlar.

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a> Ccomsafedeletecriticalhandle bölümü:: ~ Ccomsafedeletekritiksection

Yok edicisi.

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

`CRITICAL_SECTION` [M_bInitialized](#m_binitialized) veri üyesi true olarak ayarlanmışsa, bellekten iç nesne yayınlar.

## <a name="ccomsafedeletecriticalsectioninit"></a><a name="init"></a> Ccomsafedeletecriticalhandle bölümü:: Init

[Init](/visualstudio/debugger/init) 'in temel sınıf uygulamasını çağırır ve başarılı olursa true olarak ayarlar [m_bInitialized](#m_binitialized) .

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

[Ccomcriticalhandle Section:: Init](../../atl/reference/ccomcriticalsection-class.md#init)sonucunu döndürür.

## <a name="ccomsafedeletecriticalsectionlock"></a><a name="lock"></a> Ccomsafedeletekritiksection:: Lock

[Kilidin](ccomcriticalsection-class.md#lock)temel sınıf uygulamasını çağırır.

```
HRESULT Lock();
```

### <a name="return-value"></a>Dönüş Değeri

[Ccomcriticalhandle Section:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock)sonucunu döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, girişte [m_bInitialized](#m_binitialized) VERI üyesinin true olarak ayarlandığını varsayar. Bu koşul karşılanmazsa hata ayıklama yapılarında bir onaylama oluşturulur.

İşlevin davranışı hakkında daha fazla bilgi için [Ccomcriticalhandle Section:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock)öğesine bakın.

## <a name="ccomsafedeletecriticalsectionm_binitialized"></a><a name="m_binitialized"></a> Ccomsafedeletecriticalhandle bölümü:: m_bInitialized

İç nesnenin başlatılmış olup olmadığını işaretler `CRITICAL_SECTION` .

```
bool m_bInitialized;
```

### <a name="remarks"></a>Açıklamalar

`m_bInitialized`Veri üyesi, `CRITICAL_SECTION` [Ccomsafedeletecriticalhandle bölüm](../../atl/reference/ccomsafedeletecriticalsection-class.md) sınıfıyla ilişkili temel alınan nesnenin geçerliliğini izlemek için kullanılır. `CRITICAL_SECTION`Bu bayrak true olarak ayarlanmamışsa temeldeki nesnenin bellekten serbest bırakılması denenmez.

## <a name="ccomsafedeletecriticalsectionterm"></a><a name="term"></a> Ccomsafedeletecriticalhandle bölümü:: Term

İç nesne geçerliyse [Ccomcriticalhandle Section:: Term](../../atl/reference/ccomcriticalsection-class.md#term) öğesinin temel sınıf uygulamasını çağırır `CRITICAL_SECTION` .

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Girişten sonra [M_BINITIALIZED](#m_binitialized) false olarak ayarlandıysa, [Ccomcriticalhandle Section:: Term](../../atl/reference/ccomcriticalsection-class.md#term)sonucunu döndürür veya S_OK.

### <a name="remarks"></a>Açıklamalar

İç nesne geçerli olmasa bile bu yöntemi çağırmak güvenlidir `CRITICAL_SECTION` . [M_bInitialized](#m_binitialized) Data member değeri true olarak ayarlandıysa, bu sınıfın yıkıcısı bu yöntemi çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Ccomcriticalhandle bölüm sınıfı](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
