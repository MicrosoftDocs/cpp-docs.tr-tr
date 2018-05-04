---
title: IConnectionPointContainerImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af5e8b1bc1af0a515cc8fad0500c3f7d040b1eb9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl sınıfı
Bu sınıf koleksiyonu yönetmek için bir bağlantı noktası kapsayıcı uygulayan [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IConnectionPointContainerImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Bağlanılabilirlik nesnesinde desteklenen bağlantı noktaları yinelemek için bir numaralandırıcı oluşturur.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Belirtilen IID destekleyen bağlantı noktası için bir arabirim işaretçisi alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IConnectionPointContainerImpl` koleksiyonu yönetmek için bir bağlantı noktası kapsayıcı uygulayan [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) nesneleri. `IConnectionPointContainerImpl` bir istemci bağlanılabilirlik nesnesi hakkında daha fazla bilgi almak için çağırabileceği iki yöntem sunar:  
  
- `EnumConnectionPoints` hangi giden nesne destekler arabirimleri belirlemek istemcinin verir.  
  
- `FindConnectionPoint` Nesne belirli bir giden arabirim destekleyip desteklemediğini belirlemek istemcinin verir.  
  
 İçinde ATL bağlantı noktaları hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints  
 Bağlanılabilirlik nesnesinde desteklenen bağlantı noktaları yinelemek için bir numaralandırıcı oluşturur.  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPointContainer::EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) Windows SDK.  
  
##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint  
 Belirtilen IID destekleyen bağlantı noktası için bir arabirim işaretçisi alır.  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
