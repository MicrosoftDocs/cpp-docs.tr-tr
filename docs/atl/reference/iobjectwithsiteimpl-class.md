---
title: IObjectWithSiteImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
ms.openlocfilehash: 034e5dd42f6e10286520bb2a08effc40b0aca71a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329640"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl Sınıfı

Bu sınıf, bir nesnenin kendi sitesiyle iletişim kurmasına izin veren yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IObjectWithSiteImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IObjectWithSiteImpl::GetSite](#getsite)|Bir arabirim işaretçisi için siteyi sorgular.|
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Nesneye sitenin `IUnknown` işaretçisini sağlar.|
|[IObjectWithSiteImpl::SetSite](#setsite)|Nesneye sitenin `IUnknown` işaretçisini sağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Sitenin `IUnknown` işaretçisini yönetir.|

## <a name="remarks"></a>Açıklamalar

[IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) arabirimi, bir nesnenin kendi sitesiyle iletişim kurmasını sağlar. Sınıf `IObjectWithSiteImpl` bu arabirimin varsayılan bir `IUnknown` uygulamasını sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

`IObjectWithSiteImpl`iki yöntem belirtir. İstemci `SetSite`ilk olarak sitenin `IUnknown` işaretçisini geçerek çağırır. Bu işaretçi nesneiçinde depolanır ve daha sonra `GetSite`bir çağrı yoluyla alınabilir.

Genellikle, denetim olmayan bir `IObjectWithSiteImpl` nesne oluştururken sınıfTürüntürün. Denetimler için, aynı zamanda bir site işaretçisi sağlar [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), sınıf türetmek. Sınıfınızı her ikisinden `IObjectWithSiteImpl` de `IOleObjectImpl`türetetmeyin ve.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="iobjectwithsiteimplgetsite"></a><a name="getsite"></a>IObjectWithSiteImpl::GetSite

Tarafından tanımlanan arabirimi işaretçisi `riid`için siteyi sorgular.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Açıklamalar

Site bu arabirimi destekliyorsa, `ppvSite`işaretçi . Aksi `ppvSite` takdirde, NULL olarak ayarlanır.

Bkz. [IObjectWithSite::Windows](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) SDK'daki Site.

## <a name="iobjectwithsiteimplm_spunksite"></a><a name="m_spunksite"></a>IObjectWithSiteImpl::m_spUnkSite

Sitenin `IUnknown` işaretçisini yönetir.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Açıklamalar

`m_spUnkSite`başlangıçta [SetSite'ye](#setsite)bir çağrı yoluyla bu işaretçi alır.

## <a name="iobjectwithsiteimplsetchildsite"></a><a name="setchildsite"></a>IObjectWithSiteImpl::SetChildSite

Nesneye sitenin `IUnknown` işaretçisini sağlar.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Parametreler

*pUnkSite*<br/>
[içinde] Bu nesneyi yöneten sitenin `IUnknown` arabirim işaretçisine işaretçi. NULL ise, nesne, `IUnknown::Release` nesnenin artık sitesini bilmediği herhangi bir varolan siteyi çağırmalıdır.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="iobjectwithsiteimplsetsite"></a><a name="setsite"></a>IObjectWithSiteImpl::SetSite

Nesneye sitenin `IUnknown` işaretçisini sağlar.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IObjectWithSite::Windows](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) SDK'da SetSite.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
