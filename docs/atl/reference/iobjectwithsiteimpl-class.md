---
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
ms.openlocfilehash: e857f739e3ff7235c473e99abbef6aab0d3f4205
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495842"
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

*ŞI*<br/>
Sınıfınız, öğesinden `IObjectWithSiteImpl`türetilir.

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

[IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) arabirimi bir nesnenin sitesiyle iletişim kurmasına izin verir. Sınıfı `IObjectWithSiteImpl` , bu arabirimin varsayılan bir uygulamasını sağlar ve hata `IUnknown` ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

`IObjectWithSiteImpl`iki yöntemi belirtir. İstemci ilk kez çağırır `SetSite`ve `IUnknown` site işaretçisini geçiyor. Bu işaretçi nesne içinde depolanır ve daha sonra öğesine `GetSite`çağrısıyla alınabilir.

Genellikle, bir denetim olmayan bir nesne `IObjectWithSiteImpl` oluştururken sınıfınızı sınıfından türetirsiniz. Denetimler için, sınıfınızı bir site işaretçisi de sağlayan [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)' dan türetirsiniz. Sınıfınızı `IObjectWithSiteImpl` ve ' `IOleObjectImpl`den türemeyin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="getsite"></a>IObjectWithSiteImpl:: GetSite

Sitesini tarafından `riid`tanımlanan arabirime yönelik bir işaretçi için sorgular.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Açıklamalar

Site bu arabirimi destekliyorsa, işaretçi aracılığıyla `ppvSite`döndürülür. Aksi takdirde `ppvSite` , null olarak ayarlanır.

Windows SDK bkz. [IObjectWithSite:: GetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) .

##  <a name="m_spunksite"></a>IObjectWithSiteImpl:: m_spUnkSite

Sitenin `IUnknown` işaretçisini yönetir.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Açıklamalar

`m_spUnkSite`Başlangıçta bu işaretçiyi bir [SetSite](#setsite)çağrısıyla alır.

##  <a name="setchildsite"></a>IObjectWithSiteImpl:: SetChildSite

Nesneyi sitenin `IUnknown` işaretçiyle birlikte sağlar.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Parametreler

*pUnkSite*<br/>
'ndaki Bu nesneyi yöneten `IUnknown` sitenin arabirim işaretçisine yönelik işaretçi. NULL ise, nesne, nesnenin artık `IUnknown::Release` sitesini bilmediği, var olan herhangi bir sitede çağırmalıdır.

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

##  <a name="setsite"></a>IObjectWithSiteImpl:: SetSite

Nesneyi sitenin `IUnknown` işaretçiyle birlikte sağlar.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. ' de [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
