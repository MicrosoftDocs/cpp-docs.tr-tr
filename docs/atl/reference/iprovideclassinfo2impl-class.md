---
description: 'Daha fazla bilgi edinin: IProvideClassInfo2Impl Class'
title: IProvideClassInfo2Impl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
ms.openlocfilehash: 9c3422c98ebd857231f492efb77d51a0a49acb76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139263"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl sınıfı

Bu sınıf, [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) ve [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) yöntemlerinin varsayılan bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>Parametreler

*pcoclsıd*<br/>
Coclass 'ın tanımlayıcısına yönelik bir işaretçi.

*psrcıd*<br/>
' Coclass ' varsayılan giden görüntüleme arabirimi tanımlayıcısına yönelik bir işaretçi.

*plibıd*<br/>
Arabirim hakkında bilgi içeren tür kitaplığının LIBıD işaretçisi. Varsayılan olarak, sunucu düzeyi tür kitaplığı geçirilir.

*Wana*<br/>
Tür kitaplığının ana sürümü. Varsayılan değer 1’dir.

*wMinor*<br/>
Tür kitaplığının ikincil sürümü. Varsayılan değer 0’dır.

*tihclass*<br/>
Coclass 'ın tür bilgilerini yönetmek için kullanılan sınıf. `CComTypeInfoHolder` varsayılan değerdir.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IProvideClassInfo2Impl:: GetClassInfo](#getclassinfo)|`ITypeInfo`Coclass 'ın tür bilgilerine bir işaretçi alır.|
|[IProvideClassInfo2Impl:: GetGUID](#getguid)|Nesnenin giden dispınterface için GUID 'YI alır.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IProvideClassInfo2Impl:: _tih](#_tih)|Coclass için tür bilgilerini yönetir.|

## <a name="remarks"></a>Açıklamalar

[IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) arabirimi, yöntemini ekleyerek [IProvideClassInfo 'yu](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) genişletir `GetGUID` . Bu yöntem, bir istemcinin varsayılan olay kümesi için bir nesnenin giden arabirim IID 'sini almasına izin verir. Sınıfı `IProvideClassInfo2Impl` , ve yöntemlerinin varsayılan bir uygulamasını `IProvideClassInfo` sağlar `IProvideClassInfo2` .

`IProvideClassInfo2Impl``CComTypeInfoHolder`coclass için tür bilgilerini yöneten türün statik bir üyesini içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="iprovideclassinfo2implgetclassinfo"></a><a name="getclassinfo"></a> IProvideClassInfo2Impl:: GetClassInfo

`ITypeInfo`Coclass 'ın tür bilgilerine bir işaretçi alır.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IProvideClassInfo:: GetClassInfo](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) .

## <a name="iprovideclassinfo2implgetguid"></a><a name="getguid"></a> IProvideClassInfo2Impl:: GetGUID

Nesnenin giden dispınterface için GUID 'YI alır.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IProvideClassInfo2:: GetGUID](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) .

## <a name="iprovideclassinfo2impliprovideclassinfo2impl"></a><a name="iprovideclassinfo2impl"></a> IProvideClassInfo2Impl::IProvideClassInfo2Impl

Oluşturucu.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Açıklamalar

`AddRef` [_Tih](#_tih) üyesinde çağrılar. Yıkıcı çağırır `Release` .

## <a name="iprovideclassinfo2impl_tih"></a><a name="_tih"></a> IProvideClassInfo2Impl:: _tih

Bu statik veri üyesi, varsayılan olarak, *tihclass* sınıf şablonu parametresinin bir örneğidir `CComTypeInfoHolder` .

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Açıklamalar

`_tih` coclass için tür bilgilerini yönetir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
