---
title: Iconnectionpointımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d578aeea847ff04bf29fab11ecf7db2a1776b04f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217609"
---
# <a name="iconnectionpointimpl-class"></a>Iconnectionpointımpl sınıfı
Bu sınıf, bir bağlantı noktası uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `IConnectionPointImpl`.  
  
 *piid*  
 Bağlantı noktası nesnesiyle temsil edilen arabirimi Laboratuvardaki bir işaretçi.  
  
 *CDV*  
 Bağlantıları yöneten bir sınıf. Varsayılan değer [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), sınırsız sayıda bağlantı sağlar. Ayrıca [CComUnkArray](../../atl/reference/ccomunkarray-class.md), sabit sayıda bağlantı belirtir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|Bağlantı noktası ve bir havuz arasında bir bağlantı kurar.|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Bağlantılar için bağlantı noktası üzerinden yinelemek için bir numaralandırıcı oluşturur.|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Bağlantı noktası tarafından temsil edilen arabirimi Laboratuvardaki alır.|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Bağlanılabilirlik nesnesine bir arabirim işaretçisi alır.|  
|[IConnectionPointImpl::Unadvise](#unadvise)|Daha önce aracılığıyla kurulan bir bağlantıyı sonlandırır `Advise`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|Bağlantı noktası için bağlantıları yönetir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IConnectionPointImpl` istemciye giden bir arabirim ortaya çıkarmak bir nesne sağlayan bir bağlantı noktası uygular. İstemci, bir havuz olarak adlandırılan bir nesne üzerinde bu arabirimi uygular.  
  
 ATL kullanan [Iconnectionpointcontainerımpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) bağlanılabilirlik nesne uygulamak için. Bağlanılabilirlik nesnesi içindeki her bir bağlantı noktası, giden bir arabirim tarafından tanımlanan temsil eden *piid*. Sınıf *CDV* bağlantı noktası ve bir havuz arasındaki bağlantıları yönetir. Her bağlantı bir "tanımlama bilgisi tarafından" benzersiz olarak tanımlanır  
  
 ATL bağlantı noktaları hakkında daha fazla bilgi için bkz [bağlantı noktaları](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="advise"></a>  IConnectionPointImpl::Advise  
 Bağlantı noktası ve bir havuz arasında bir bağlantı kurar.  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [Unadvise](#unadvise) bağlantı çağrıyı sonlandırmak için.  
  
 Bkz: [IConnectionPoint::Advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise) Windows SDK içinde.  
  
##  <a name="enumconnections"></a>  IConnectionPointImpl::EnumConnections  
 Bağlantılar için bağlantı noktası üzerinden yinelemek için bir numaralandırıcı oluşturur.  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPoint::EnumConnections](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) Windows SDK içinde.  
  
##  <a name="getconnectioninterface"></a>  IConnectionPointImpl::GetConnectionInterface  
 Bağlantı noktası tarafından temsil edilen arabirimi Laboratuvardaki alır.  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPoint::GetConnectionInterface](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) Windows SDK içinde.  
  
##  <a name="getconnectionpointcontainer"></a>  IConnectionPointImpl::GetConnectionPointContainer  
 Bağlanılabilirlik nesnesine bir arabirim işaretçisi alır.  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPoint::GetConnectionPointContainer](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) Windows SDK içinde.  
  
##  <a name="m_vec"></a>  IConnectionPointImpl::m_vec  
 Bağlantı noktası nesnesi ve bir havuz arasındaki bağlantıları yönetir.  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `m_vec` türünde [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).  
  
##  <a name="unadvise"></a>  IConnectionPointImpl::Unadvise  
 Daha önce aracılığıyla kurulan bir bağlantıyı sonlandırır [öneri](#advise).  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPoint::Unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
