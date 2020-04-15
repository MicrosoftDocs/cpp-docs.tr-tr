---
title: IConnectionPointContainerImpl Sınıfı
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
ms.openlocfilehash: f6009a1341d6715d6d2f170d3ff2aa1aa4ffcb96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329861"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl Sınıfı

Bu [sınıf, iConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) nesnelerin bir koleksiyon yönetmek için bir bağlantı noktası kapsayıcı uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IConnectionPointContainerImpl
   : public IConnectionPointContainer
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IConnectionPointContainerImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Bağlanabilir nesnede desteklenen bağlantı noktaları aracılığıyla yinelemek için bir sayısallaştırıcı oluşturur.|
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Belirtilen IID'yi destekleyen bağlantı noktasına bir arabirim işaretçisi alır.|

## <a name="remarks"></a>Açıklamalar

`IConnectionPointContainerImpl`[iConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) nesnelerinbir koleksiyon yönetmek için bir bağlantı noktası kapsayıcı uygular. `IConnectionPointContainerImpl`bağlanabilir bir nesne hakkında daha fazla bilgi almak için istemcinin çağırabileceği iki yöntem sağlar:

- `EnumConnectionPoints`istemci, nesnenin hangi giden arabirimleri desteklediğini belirlemesini sağlar.

- `FindConnectionPoint`nesnenin belirli bir giden arabirimi destekleyip desteklemediğini istemciye verir.

ATL'de bağlantı noktalarını kullanma hakkında bilgi için [Bağlantı Noktaları](../../atl/atl-connection-points.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IConnectionPointContainer`

`IConnectionPointContainerImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="iconnectionpointcontainerimplenumconnectionpoints"></a><a name="enumconnectionpoints"></a>IConnectionPointContainerImpl::EnumConnectionPoints

Bağlanabilir nesnede desteklenen bağlantı noktaları aracılığıyla yinelemek için bir sayısallaştırıcı oluşturur.

```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IConnectionPointContainer::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-enumconnectionpoints) SDK'daki EnumConnectionPoints.

## <a name="iconnectionpointcontainerimplfindconnectionpoint"></a><a name="findconnectionpoint"></a>IConnectionPointContainerImpl::FindConnectionPoint

Belirtilen IID'yi destekleyen bağlantı noktasına bir arabirim işaretçisi alır.

```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IConnectionPointContainer::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint) SDK'da Bağlantı Noktası'nı bulun.

## <a name="see-also"></a>Ayrıca bkz.

[ıconnectionpointcontainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
