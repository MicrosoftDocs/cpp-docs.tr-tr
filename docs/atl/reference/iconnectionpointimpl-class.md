---
title: "IConnectionPointImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c49057153a23f0e17d09032df8781b64cef8677
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl sınıfı
Bu sınıf, bir bağlantı noktası uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IConnectionPointImpl`.  
  
 `piid`  
 Bağlantı noktası nesnesinin temsil ettiği arabirimi IID gösteren bir işaretçi.  
  
 `CDV`  
 Bağlantıları yöneten bir sınıf. Varsayılan değer [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), sınırsız izin verir. Aynı zamanda [CComUnkArray](../../atl/reference/ccomunkarray-class.md), sabit bir bağlantı sayısını belirtir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|Bağlantı noktası ve bir havuz arasında bir bağlantı kurar.|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Bağlantı noktası için bağlantıları yinelemek için bir numaralandırıcı oluşturur.|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Bağlantı noktası tarafından temsil edilen arabirim IID alır.|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Arabirim işaretçisi bağlanılabilirlik nesnesine alır.|  
|[IConnectionPointImpl::Unadvise](#unadvise)|Üzerinden daha önce oluşturulmuş bir bağlantıyı sonlandırır `Advise`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|Bağlantı noktası yönelik bağlantıları yönetir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IConnectionPointImpl`istemciye giden bir arabirimi kullanıma sunmak bir nesne sağlayan bir bağlantı noktası uygular. İstemci bir havuz adlı bir nesne üzerinde bu arabirimi uygular.  
  
 ATL kullanan [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) bağlanılabilirlik nesne uygulamak için. Her bağlantı noktası bağlanılabilirlik nesne içinde tarafından tanımlanan, giden bir arabirimi temsil eder `piid`. Sınıf *CDV* bağlantı noktası ve bir havuz arasındaki bağlantıları yönetir. Her bağlantı "tanımlama bilgisi tarafından." benzersiz olarak tanımlanır  
  
 İçinde ATL bağlantı noktaları hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="advise"></a>IConnectionPointImpl::Advise  
 Bağlantı noktası ve bir havuz arasında bir bağlantı kurar.  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [Unadvise](#unadvise) bağlantı aramayı sonlandırmak için.  
  
 Bkz: [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) Windows SDK.  
  
##  <a name="enumconnections"></a>IConnectionPointImpl::EnumConnections  
 Bağlantı noktası için bağlantıları yinelemek için bir numaralandırıcı oluşturur.  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPoint::EnumConnections](http://msdn.microsoft.com/library/windows/desktop/ms680755) Windows SDK.  
  
##  <a name="getconnectioninterface"></a>IConnectionPointImpl::GetConnectionInterface  
 Bağlantı noktası tarafından temsil edilen arabirim IID alır.  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPoint::GetConnectionInterface](http://msdn.microsoft.com/library/windows/desktop/ms693468) Windows SDK.  
  
##  <a name="getconnectionpointcontainer"></a>IConnectionPointImpl::GetConnectionPointContainer  
 Arabirim işaretçisi bağlanılabilirlik nesnesine alır.  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPoint::GetConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms679669) Windows SDK.  
  
##  <a name="m_vec"></a>IConnectionPointImpl::m_vec  
 Bağlantı noktası nesnesi ve bir havuz arasındaki bağlantıları yönetir.  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `m_vec` türü [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).  
  
##  <a name="unadvise"></a>IConnectionPointImpl::Unadvise  
 Üzerinden daha önce oluşturulmuş bir bağlantıyı sonlandırır [öneri](#advise).  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
