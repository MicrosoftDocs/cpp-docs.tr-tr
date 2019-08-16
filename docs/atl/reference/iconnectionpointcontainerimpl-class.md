---
title: Inewctionpointcontainerımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
ms.openlocfilehash: 278ca6b1b9aac9539680d90b6fa0b18df22fc2f0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496017"
---
# <a name="iconnectionpointcontainerimpl-class"></a>Inewctionpointcontainerımpl sınıfı

Bu sınıf, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) nesnelerinin bir koleksiyonunu yönetmek için bir bağlantı noktası kapsayıcısı uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız, öğesinden `IConnectionPointContainerImpl`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Inewctionpointcontainerımpl:: EnumConnectionPoints](#enumconnectionpoints)|Bağlanılabilir nesnede desteklenen bağlantı noktalarında yinelemek için bir Numaralandırıcı oluşturur.|
|[Inewctionpointcontainerımpl:: FindConnectionPoint](#findconnectionpoint)|Bağlantı noktasına belirtilen IID 'yi destekleyen bir arabirim işaretçisi alır.|

## <a name="remarks"></a>Açıklamalar

`IConnectionPointContainerImpl`[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) nesnelerinin bir koleksiyonunu yönetmek için bir bağlantı noktası kapsayıcısı uygular. `IConnectionPointContainerImpl`, bir istemcinin bağlanılabilir bir nesne hakkında daha fazla bilgi almak için çağıraalabileceği iki yöntem sunar:

- `EnumConnectionPoints`istemcinin nesnenin desteklediği giden arabirimleri belirlemesine izin verir.

- `FindConnectionPoint`istemcinin, nesnenin belirli bir giden arabirimi destekleyip desteklemediğini belirlemesine izin verir.

ATL 'de bağlantı noktalarını kullanma hakkında daha fazla bilgi için, [bağlantı noktaları](../../atl/atl-connection-points.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="enumconnectionpoints"></a>Inewctionpointcontainerımpl:: EnumConnectionPoints

Bağlanılabilir nesnede desteklenen bağlantı noktalarında yinelemek için bir Numaralandırıcı oluşturur.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IConnectionPointContainer:: EnumConnectionPoints](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) .

##  <a name="findconnectionpoint"></a>Inewctionpointcontainerımpl:: FindConnectionPoint

Bağlantı noktasına belirtilen IID 'yi destekleyen bir arabirim işaretçisi alır.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IConnectionPointContainer:: FindConnectionPoint](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
