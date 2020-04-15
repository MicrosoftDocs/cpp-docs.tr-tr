---
title: CComSafeDeleteCriticalSection Sınıfı
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
ms.openlocfilehash: cb0dc440fc0e79e0023b5fbd6e4ca2345d031d3d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327364"
---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection Sınıfı

Bu sınıf, kritik bir bölüm nesnesinin sahipliğini almak ve serbest bırakmak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomSafeDeleteCriticalSection::ccomsafedeletecriticalsection](#ccomsafedeletecriticalsection)|Oluşturucu.|
|[CcomSafeDeleteCriticalSection::~ccomsafedeletecriticalsection](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::Init](#init)|Kritik bir bölüm nesnesi oluşturur ve başharfe bleştirir.|
|[CcomSafeDeleteCriticalSection::Kilit](#lock)|Kritik bölüm nesnesinin sahipliğini alır.|
|[CcomSafeDeleteCriticalSection::Terim](#term)|Kritik bölüm nesnesi tarafından kullanılan sistem kaynaklarını serbest bırakır.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|[m_bInitialized](#m_binitialized)|İç `CRITICAL_SECTION` nesnenin baş harfe mi başlandığını bayraklar.|

## <a name="remarks"></a>Açıklamalar

`CComSafeDeleteCriticalSection`sınıf [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)türetilmiştir. Ancak, `CComSafeDeleteCriticalSection` [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)üzerinde ek güvenlik mekanizmaları sağlar.

Bir örneği `CComSafeDeleteCriticalSection` kapsam dışına çıktığında veya bellekten açıkça silindiğinde, altta yatan kritik bölüm nesnesi hala geçerliyse otomatik olarak temizlenir. Buna ek olarak, [CComSafeDeleteCriticalSection::Terim](#term) yöntemi, temel kritik bölüm nesnesi henüz tahsis edilmemişse veya bellekten zaten serbest bırakılmışsa, düzgün bir şekilde çıkar.

Kritik bölüm yardımcı sınıfları hakkında daha fazla bilgi için [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Ccomcriticalsection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="ccomsafedeletecriticalsection"></a>CcomSafeDeleteCriticalSection::ccomsafedeletecriticalsection

Oluşturucu.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

[m_bInitialized](#m_binitialized) veri üyesini FALSE olarak ayarlar.

## <a name="ccomsafedeletecriticalsectionccomsafedeletecriticalsection"></a><a name="dtor"></a>CcomSafeDeleteCriticalSection::~ccomsafedeletecriticalsection

Yıkıcı.

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

m_bInitialized veri `CRITICAL_SECTION` üyesi TRUE [m_bInitialized](#m_binitialized) olarak ayarlanmışsa iç nesneyi bellekten serbest bırakır.

## <a name="ccomsafedeletecriticalsectioninit"></a><a name="init"></a>CComSafeDeleteCriticalSection::Init

[Init'in](/visualstudio/debugger/init) taban sınıf uygulamasını çağırır ve başarılı olursa [m_bInitialized](#m_binitialized) TRUE'ya ayarlar.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComCriticalSection sonucunu verir::Init](../../atl/reference/ccomcriticalsection-class.md#init).

## <a name="ccomsafedeletecriticalsectionlock"></a><a name="lock"></a>CcomSafeDeleteCriticalSection::Kilit

[Kilit'in](ccomcriticalsection-class.md#lock)taban sınıf uygulamasını çağırır.

```
HRESULT Lock();
```

### <a name="return-value"></a>Dönüş Değeri

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md#lock)sonucunu döndürür::Kilit .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [veri](#m_binitialized) üyesinin girişte M_BINITIALIZED TRUE olarak ayarlandığını varsayar. Bu koşul yerine getirilmezse Hata Ayıklama oluşturur'da bir iddia oluşturulur.

İşlevin davranışı hakkında daha fazla bilgi için [CComCriticalSection bakın:Kilit](../../atl/reference/ccomcriticalsection-class.md#lock).

## <a name="ccomsafedeletecriticalsectionm_binitialized"></a><a name="m_binitialized"></a>CComSafeDeleteCriticalSection::m_bInitialized

İç `CRITICAL_SECTION` nesnenin baş harfe mi başlandığını bayraklar.

```
bool m_bInitialized;
```

### <a name="remarks"></a>Açıklamalar

`m_bInitialized` Veri üyesi [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) sınıfı ile ilişkili altta yatan `CRITICAL_SECTION` nesnenin geçerliliğini izlemek için kullanılır. Bu `CRITICAL_SECTION` bayrak TRUE olarak ayarlanmazsa, temel nesne bellekten serbest bırakılmaya çalışılacak.

## <a name="ccomsafedeletecriticalsectionterm"></a><a name="term"></a>CcomSafeDeleteCriticalSection::Terim

CComCriticalSection taban sınıf uygulaması [çağırır::Terim](../../atl/reference/ccomcriticalsection-class.md#term) `CRITICAL_SECTION` iç nesne geçerli ise.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term)veya [m_bInitialized](#m_binitialized) girişte FALSE olarak ayarlanmışsa S_OK sonucunu verir.

### <a name="remarks"></a>Açıklamalar

İç `CRITICAL_SECTION` nesne geçerli olmasa bile bu yöntemi aramak güvenlidir. [m_bInitialized](#m_binitialized) veri üyesi TRUE olarak ayarlanmışsa, bu sınıfın yıkıcısı bu yöntemi çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
