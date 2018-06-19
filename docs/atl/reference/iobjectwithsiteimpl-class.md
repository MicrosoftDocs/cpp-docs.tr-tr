---
title: IObjectWithSiteImpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: 6c626db62a02fba70f926776ea214e664d2f7f82
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362045"
---
# <a name="iobjectwithsiteimpl-class"></a>IObjectWithSiteImpl sınıfı
Bu sınıf, siteyle iletişim için bir nesne sağlayan yöntemlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IObjectWithSiteImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|Site için bir arabirim işaretçisi sorgular.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Sitenin nesneyi sağlar **IUnknown** işaretçi.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|Sitenin nesneyi sağlar **IUnknown** işaretçi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Sitenin yönetir **IUnknown** işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) arabirimi kendi sitesiyle iletişim kurmak bir nesne izin verir. Sınıf `IObjectWithSiteImpl` bu arabirimin varsayılan uygulamasını sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 `IObjectWithSiteImpl` iki yöntemlerini belirtir. İstemci ilk çağrıları `SetSite`, sitenin geçirme **IUnknown** işaretçi. Bu işaretçinin nesnesi içinde depolanır ve daha sonra bir çağrıyla alınabilir `GetSite`.  
  
 Tipik olarak sizin sınıfından türetilen `IObjectWithSiteImpl` zaman, nesneyi, oluşturduğunuz bir denetim değil. Denetimler için sınıfından türetilen [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), ayrıca sağlayan bir site işaretçi. Sınıfınızda hem de türetilmiş olmayan `IObjectWithSiteImpl` ve `IOleObjectImpl`.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite  
 Site tarafından tanımlanan arayüzü için bir işaretçi için sorgular `riid`.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu arabirim sitenin desteklediği işaretçinin aracılığıyla döndürülür `ppvSite`. Aksi takdirde, `ppvSite` ayarlanır **NULL**.  
  
 Bkz: [IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452) Windows SDK.  
  
##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite  
 Sitenin yönetir **IUnknown** işaretçi.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_spUnkSite` Bu işaretçinin çağrısıyla başlangıçta aldığı [SetSite](#setsite).  
  
##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite  
 Sitenin nesneyi sağlar **IUnknown** işaretçi.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnkSite*  
 [in] İşaretçi **IUnknown** bu nesne yönetme site arabirimi işaretçisi. NULL ise nesne çağırmalıdır `IUnknown::Release` hangi noktada nesne artık kendi site bilir herhangi bir varolan sitede.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite  
 Sitenin nesneyi sağlar **IUnknown** işaretçi.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
