---
title: IProvideClassInfo2Impl Sınıfı
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
ms.openlocfilehash: 0d1ee9acc1cfabc71ecf33fcb5919d826899c671
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329564"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl Sınıfı

Bu [sınıf, IProvideClassInfo ve IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) yöntemlerinin varsayılan bir uygulamasını sağlar. [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2)

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

*pcoclsid*<br/>
Coclass tanımlayıcısına bir işaretçi.

*psrcid*<br/>
Coclass'ın varsayılan giden dispinterface için tanımlayıcıiçin bir işaretçi.

*plibid*<br/>
Arabirimi hakkında bilgi içeren tür kitaplığı LIBID için bir işaretçi. Varsayılan olarak, sunucu düzeyinde tür kitaplığı geçirilir.

*wMajor*<br/>
Tür kitaplığın ana sürümü. Varsayılan değer 1’dir.

*wMinor*<br/>
Tür kitaplığın küçük sürümü. Varsayılan değer 0’dır.

*tihclass*<br/>
Grup sınıfının tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan değer: `CComTypeInfoHolder`.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Coclass'ın tür bilgileriiçin bir `ITypeInfo` işaretçi alır.|
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Nesnenin giden dispinterface için GUID alır.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[IProvideClassInfo2Impl::_tih](#_tih)|Coclass'ın tür bilgilerini yönetir.|

## <a name="remarks"></a>Açıklamalar

[IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) arabirimi `GetGUID` yöntemi ekleyerek [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) genişletir. Bu yöntem, istemcinin varsayılan olay kümesi için bir nesnenin giden arabirimi IID'yi almasına olanak tanır. Sınıf `IProvideClassInfo2Impl` `IProvideClassInfo` ve `IProvideClassInfo2` yöntemlerin varsayılan bir uygulama sağlar.

`IProvideClassInfo2Impl`grup sınıfının tür `CComTypeInfoHolder` bilgilerini yöneten statik bir tür üyesi içerir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="iprovideclassinfo2implgetclassinfo"></a><a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo

Coclass'ın tür bilgileriiçin bir `ITypeInfo` işaretçi alır.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IProvideClassInfo::Windows](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) SDK'da GetClassInfo.

## <a name="iprovideclassinfo2implgetguid"></a><a name="getguid"></a>IProvideClassInfo2Impl::GetGUID

Nesnenin giden dispinterface için GUID alır.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IProvideClassInfo2::Windows](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) SDK'da GETGUID.

## <a name="iprovideclassinfo2impliprovideclassinfo2impl"></a><a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl

Oluşturucu.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Açıklamalar

`AddRef` [_tih](#_tih) üyeyi arar. Yıkıcı arıyor. `Release`

## <a name="iprovideclassinfo2impl_tih"></a><a name="_tih"></a>IProvideClassInfo2Impl::_tih

Bu statik veri üyesi sınıf şablonparametresi, *tihclass*, `CComTypeInfoHolder`varsayılan olarak bir örneğidir .

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Açıklamalar

`_tih`grup sınıfının tür bilgilerini yönetir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
