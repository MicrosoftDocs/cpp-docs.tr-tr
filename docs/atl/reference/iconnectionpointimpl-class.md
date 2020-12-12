---
description: 'Şu konuda daha fazla bilgi edinin: ınewctionpointımpl sınıfı'
title: Inewctionpointımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
ms.openlocfilehash: d87eb0821a3a48d171c196c891b5f5c7aacb9cdf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139587"
---
# <a name="iconnectionpointimpl-class"></a>Inewctionpointımpl sınıfı

Bu sınıf bir bağlantı noktası uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IConnectionPointImpl` .

*piıd*<br/>
Bağlantı noktası nesnesi tarafından temsil edilen arabirimin IID 'sine yönelik bir işaretçi.

*CDV*<br/>
Bağlantıları yöneten bir sınıf. Varsayılan değer, sınırsız bağlantılara izin veren [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)' dir. Ayrıca, sabit sayıda bağlantıyı belirten [CComUnkArray](../../atl/reference/ccomunkarray-class.md)' i de kullanabilirsiniz.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Inewctionpointımpl:: Advise](#advise)|Bağlantı noktası ve havuz arasında bir bağlantı kurar.|
|[Inewctionpointımpl:: EnumConnections](#enumconnections)|Bağlantı noktası bağlantılarında yinelemek için bir Numaralandırıcı oluşturur.|
|[Inewctionpointımpl:: GetConnectionInterface](#getconnectioninterface)|Bağlantı noktası tarafından temsil edilen arabirimin IID 'sini alır.|
|[Inewctionpointımpl:: GetConnectionPointContainer](#getconnectionpointcontainer)|Bağlanılabilir nesnesine bir arabirim işaretçisi alır.|
|[Inewctionpointımpl:: Unadvise](#unadvise)|Daha önce tarafından kurulan bir bağlantıyı sonlandırır `Advise` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Inewctionpointımpl:: m_vec](#m_vec)|Bağlantı noktası için bağlantıları yönetir.|

## <a name="remarks"></a>Açıklamalar

`IConnectionPointImpl` bir bağlantı noktası uygular ve bu, bir nesnenin istemciye giden bir arabirimi kullanıma almasına olanak tanır. İstemci bu arabirimi havuz adlı bir nesne üzerinde uygular.

ATL, bağlanılabilir nesneyi uygulamak için [ınewctionpointcontainerımpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) kullanır. Bağlanılabilir nesne içindeki her bağlantı noktası, *pIID* tarafından tanımlanan bir giden arabirimi temsil eder. *CDV* sınıfı bağlantı noktası ve havuz arasındaki bağlantıları yönetir. Her bağlantı, "tanımlama bilgisi" tarafından benzersiz bir şekilde tanımlanır.

ATL 'de bağlantı noktalarını kullanma hakkında daha fazla bilgi için, [bağlantı noktaları](../../atl/atl-connection-points.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="iconnectionpointimpladvise"></a><a name="advise"></a> Inewctionpointımpl:: Advise

Bağlantı noktası ve havuz arasında bir bağlantı kurar.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>Açıklamalar

Bağlantı çağrısını sonlandırmak için [Unadvise](#unadvise) kullanın.

Windows SDK bkz. [ınewctionpoint:: Advise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) .

## <a name="iconnectionpointimplenumconnections"></a><a name="enumconnections"></a> Inewctionpointımpl:: EnumConnections

Bağlantı noktası bağlantılarında yinelemek için bir Numaralandırıcı oluşturur.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [ınewctionpoint:: EnumConnections](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) .

## <a name="iconnectionpointimplgetconnectioninterface"></a><a name="getconnectioninterface"></a> Inewctionpointımpl:: GetConnectionInterface

Bağlantı noktası tarafından temsil edilen arabirimin IID 'sini alır.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK ' de [IConnectionPoint:: GetConnectionInterface](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) öğesine bakın.

## <a name="iconnectionpointimplgetconnectionpointcontainer"></a><a name="getconnectionpointcontainer"></a> Inewctionpointımpl:: GetConnectionPointContainer

Bağlanılabilir nesnesine bir arabirim işaretçisi alır.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [ınewctionpoint:: GetConnectionPointContainer](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) .

## <a name="iconnectionpointimplm_vec"></a><a name="m_vec"></a> Inewctionpointımpl:: m_vec

Bağlantı noktası nesnesi ve havuz arasındaki bağlantıları yönetir.

```
CDV m_vec;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `m_vec` [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)türüdür.

## <a name="iconnectionpointimplunadvise"></a><a name="unadvise"></a> Inewctionpointımpl:: Unadvise

Daha önce [öneri](#advise)aracılığıyla kurulan bir bağlantıyı sonlandırır.

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [ınewctionpoint:: Unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) .

## <a name="see-also"></a>Ayrıca bkz.

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
