---
title: Iobjectwithsiteımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
dev_langs:
- C++
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1684c8fa380a7d17c802ad404c38c59f2257c979
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752033"
---
# <a name="iobjectwithsiteimpl-class"></a>Iobjectwithsiteımpl sınıfı

Bu sınıf, siteyle iletişim için bir nesne sağlayan yöntemlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>Parametreler

*T*  
Sınıfınız, türetilen `IObjectWithSiteImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IObjectWithSiteImpl::GetSite](#getsite)|Site bir arabirim işaretçisi için sorgular.|
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Sitenin nesneyi sağlar `IUnknown` işaretçi.|
|[IObjectWithSiteImpl::SetSite](#setsite)|Sitenin nesneyi sağlar `IUnknown` işaretçi.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Sitenin yönetir `IUnknown` işaretçi.|

## <a name="remarks"></a>Açıklamalar

[IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) nesnenin kendi sitesiyle iletişim kurmak arabirim sağlar. Sınıf `IObjectWithSiteImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

`IObjectWithSiteImpl` iki yöntem belirtir. İstemci ilk çağrı `SetSite`, sitenin geçirme `IUnknown` işaretçi. Bu işaretçinin nesnesinde depolanır ve daha sonra yapılan bir çağrıyla alınabilir `GetSite`.

Genellikle, sizin sınıfınızdan türetilen `IObjectWithSiteImpl` ne zaman bir nesne, oluşturmakta olduğunuz bir denetimi değil. Denetimler için sizin sınıfınızdan türetilen [Ioleobjectımpl](../../atl/reference/ioleobjectimpl-class.md), da sağlayan bir site işaretçi. Sınıfınıza hem de türetilmiş olmayan `IObjectWithSiteImpl` ve `IOleObjectImpl`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite

Site tarafından tanımlanan bir arabirim işaretçisi için sorgular `riid`.

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Açıklamalar

Bu arabirim sitenin desteklediği, işaretçi aracılığıyla döndürülür `ppvSite`. Aksi takdirde, `ppvSite` NULL olarak ayarlandı.

Bkz: [IObjectWithSite::GetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-getsite) Windows SDK içinde.

##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite

Sitenin yönetir `IUnknown` işaretçi.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Açıklamalar

`m_spUnkSite` this işaretçisi yapılan bir çağrıyla başlangıçta aldığı [SetSite](#setsite).

##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite

Sitenin nesneyi sağlar `IUnknown` işaretçi.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Parametreler

*pUnkSite*  
[in] İşaretçi `IUnknown` arayüz işaretçisinden bir sitenin bu nesne yönetme. NULL ise, nesne çağırmalıdır `IUnknown::Release` herhangi bir mevcut sitede hangi noktada nesne artık kendi site bilir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite

Sitenin nesneyi sağlar `IUnknown` işaretçi.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
