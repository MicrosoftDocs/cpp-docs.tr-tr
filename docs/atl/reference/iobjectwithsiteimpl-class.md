---
description: 'Daha fazla bilgi edinin: IObjectWithSiteImpl sınıfı'
title: IObjectWithSiteImpl sınıfı
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
ms.openlocfilehash: 100a4d16bea63d573fe4fb00bc37e656a7c2c483
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158302"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl sınıfı

Bu sınıf, bir nesnenin sitesiyle iletişim kurmasına izin veren yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IObjectWithSiteImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IObjectWithSiteImpl:: GetSite](#getsite)|Siteyi bir arabirim işaretçisi için sorgular.|
|[IObjectWithSiteImpl:: SetChildSite](#setchildsite)|Nesneyi sitenin `IUnknown` işaretçiyle birlikte sağlar.|
|[IObjectWithSiteImpl:: SetSite](#setsite)|Nesneyi sitenin `IUnknown` işaretçiyle birlikte sağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IObjectWithSiteImpl:: m_spUnkSite](#m_spunksite)|Sitenin `IUnknown` işaretçisini yönetir.|

## <a name="remarks"></a>Açıklamalar

[IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) arabirimi bir nesnenin sitesiyle iletişim kurmasına izin verir. Sınıfı, `IObjectWithSiteImpl` Bu arabirimin varsayılan bir uygulamasını sağlar ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

`IObjectWithSiteImpl` iki yöntemi belirtir. İstemci ilk kez çağırır `SetSite` ve site `IUnknown` işaretçisini geçiyor. Bu işaretçi nesne içinde depolanır ve daha sonra öğesine çağrısıyla alınabilir `GetSite` .

Genellikle, `IObjectWithSiteImpl` bir denetim olmayan bir nesne oluştururken sınıfınızı sınıfından türetirsiniz. Denetimler için, sınıfınızı bir site işaretçisi de sağlayan [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)' dan türetirsiniz. Sınıfınızı ve ' den türemeyin `IObjectWithSiteImpl` `IOleObjectImpl` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="iobjectwithsiteimplgetsite"></a><a name="getsite"></a> IObjectWithSiteImpl:: GetSite

Sitesini tarafından tanımlanan arabirime yönelik bir işaretçi için sorgular `riid` .

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Açıklamalar

Site bu arabirimi destekliyorsa, işaretçi aracılığıyla döndürülür `ppvSite` . Aksi takdirde, `ppvSite` null olarak ayarlanır.

Windows SDK bkz. [IObjectWithSite:: GetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) .

## <a name="iobjectwithsiteimplm_spunksite"></a><a name="m_spunksite"></a> IObjectWithSiteImpl:: m_spUnkSite

Sitenin `IUnknown` işaretçisini yönetir.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Açıklamalar

`m_spUnkSite` Başlangıçta bu işaretçiyi bir [SetSite](#setsite)çağrısıyla alır.

## <a name="iobjectwithsiteimplsetchildsite"></a><a name="setchildsite"></a> IObjectWithSiteImpl:: SetChildSite

Nesneyi sitenin `IUnknown` işaretçiyle birlikte sağlar.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Parametreler

*pUnkSite*<br/>
'ndaki `IUnknown` Bu nesneyi yöneten sitenin arabirim işaretçisine yönelik işaretçi. NULL ise, nesne, `IUnknown::Release` nesnenin artık sitesini bilmediği, var olan herhangi bir sitede çağırmalıdır.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

## <a name="iobjectwithsiteimplsetsite"></a><a name="setsite"></a> IObjectWithSiteImpl:: SetSite

Nesneyi sitenin `IUnknown` işaretçiyle birlikte sağlar.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. ' de [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
