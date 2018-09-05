---
title: Iconnectionpointcontainerımpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: 17a66946ced067e720a7e907bf39ffdd10327bc5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760662"
---
# <a name="iconnectionpointcontainerimpl-class"></a>Iconnectionpointcontainerımpl sınıfı

Bu sınıfın uyguladığı bir koleksiyonu yönetmek için bir bağlantı noktası kapsayıcı [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) nesneleri.

## <a name="syntax"></a>Sözdizimi

```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>Parametreler

*T*  
Sınıfınız, türetilen `IConnectionPointContainerImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Bağlanılabilirlik nesnesinde desteklenen bağlantı noktaları üzerinden yinelemek için bir numaralandırıcı oluşturur.|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Belirtilen IID destekleyen bağlantı noktası için bir arabirim işaretçisi alır.|

## <a name="remarks"></a>Açıklamalar

`IConnectionPointContainerImpl` bir koleksiyonu yönetmek için bir bağlantı noktası kapsayıcı uygulayan [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) nesneleri. `IConnectionPointContainerImpl` bir istemci bir bağlanılabilirlik nesnesi hakkında daha fazla bilgi almak için çağırabileceğiniz iki yöntem sunar:

- `EnumConnectionPoints` hangi giden nesne destekler arabirimleri belirlemek istemcinin sağlar.

- `FindConnectionPoint` Nesne belirli bir giden arabirim destekleyip desteklemediğini belirlemek üzere istemci sağlar.

ATL bağlantı noktaları hakkında daha fazla bilgi için bkz [bağlantı noktaları](../../atl/atl-connection-points.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints

Bağlanılabilirlik nesnesinde desteklenen bağlantı noktaları üzerinden yinelemek için bir numaralandırıcı oluşturur.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IConnectionPointContainer::EnumConnectionPoints](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) Windows SDK içinde.

##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint

Belirtilen IID destekleyen bağlantı noktası için bir arabirim işaretçisi alır.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IConnectionPointContainer::FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca Bkz.

[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
