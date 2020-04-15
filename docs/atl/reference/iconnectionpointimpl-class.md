---
title: IConnectionPointImpl Sınıfı
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
ms.openlocfilehash: c62ac3310a579379674674a7a9a517e3f2fd60e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329848"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl Sınıfı

Bu sınıf bir bağlantı noktası uygular.

## <a name="syntax"></a>Sözdizimi

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IConnectionPointImpl`türetilmiştir.

*piid*<br/>
Bağlantı noktası nesnesi tarafından temsil edilen arabirimin IID'sine işaretçi.

*Cdv*<br/>
Bağlantıları yöneten bir sınıf. Varsayılan değer [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), sınırsız bağlantı sağlar. Sabit sayıda bağlantı belirten [CComUnkArray'i](../../atl/reference/ccomunkarray-class.md)de kullanabilirsiniz.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IConnectionPointImpl::Tavsiye](#advise)|Bağlantı noktası ve lavabo arasında bir bağlantı kurar.|
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Bağlantı noktası nın bağlantıları aracılığıyla yinelemek için bir sayısallaştırıcı oluşturur.|
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Bağlantı noktası tarafından temsil edilen arabirimin IID'sini alır.|
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Bağlanabilir nesneye bir arabirim işaretçisi alır.|
|[IConnectionPointImpl::Tavsiye siz](#unadvise)|Daha önce kurulan bir bağlantıyı `Advise`sonlandırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[IConnectionPointImpl::m_vec](#m_vec)|Bağlantı noktasının bağlantılarını yönetir.|

## <a name="remarks"></a>Açıklamalar

`IConnectionPointImpl`bir nesnenin giden arabirimi istemciye maruz bırakmasını sağlayan bir bağlantı noktası uygular. İstemci bu arabirimi lavabo adı verilen bir nesneye uygular.

ATL, bağlanabilir nesneyi uygulamak için [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) kullanır. Bağlanabilir nesne içindeki her bağlantı noktası *piid*tarafından tanımlanan giden bir arabirimi temsil eder. Sınıf *CDV* bağlantı noktası ve lavabo arasındaki bağlantıları yönetir. Her bağlantı benzersiz bir "çerez" ile tanımlanır.

ATL'de bağlantı noktalarını kullanma hakkında daha fazla bilgi için [Bağlantı Noktaları](../../atl/atl-connection-points.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="iconnectionpointimpladvise"></a><a name="advise"></a>IConnectionPointImpl::Tavsiye

Bağlantı noktası ve lavabo arasında bir bağlantı kurar.

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>Açıklamalar

Bağlantı çağrısını sonlandırmak için [Unadvise'ı](#unadvise) kullanın.

Bkz. [IConnectionPoint::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) SDK'da tavsiye de bulunun.

## <a name="iconnectionpointimplenumconnections"></a><a name="enumconnections"></a>IConnectionPointImpl::EnumConnections

Bağlantı noktası nın bağlantıları aracılığıyla yinelemek için bir sayısallaştırıcı oluşturur.

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IConnectionPoint::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) SDK'daki EnumConnections.

## <a name="iconnectionpointimplgetconnectioninterface"></a><a name="getconnectioninterface"></a>IConnectionPointImpl::GetConnectionInterface

Bağlantı noktası tarafından temsil edilen arabirimin IID'sini alır.

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IConnectionPoint::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) SDK'da GetConnectionInterface.

## <a name="iconnectionpointimplgetconnectionpointcontainer"></a><a name="getconnectionpointcontainer"></a>IConnectionPointImpl::GetConnectionPointContainer

Bağlanabilir nesneye bir arabirim işaretçisi alır.

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IConnectionPoint::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) SDK'da GetConnectionPointContainer.

## <a name="iconnectionpointimplm_vec"></a><a name="m_vec"></a>IConnectionPointImpl::m_vec

Bağlantı noktası nesnesi ile lavabo arasındaki bağlantıları yönetir.

```
CDV m_vec;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `m_vec` [ccomdynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)türüdür.

## <a name="iconnectionpointimplunadvise"></a><a name="unadvise"></a>IConnectionPointImpl::Tavsiye siz

Daha önce [Advise](#advise)aracılığıyla kurulan bağlantıyı sonlandırır.

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IConnectionPoint::Windows](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) SDK'da tavsiye dışı.

## <a name="see-also"></a>Ayrıca bkz.

[ıconnectionpoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
