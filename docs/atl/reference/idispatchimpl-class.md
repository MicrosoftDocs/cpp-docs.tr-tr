---
title: Idispatchımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81feb345c25ea1c1e9d15dba8dceebb7a2cdb418
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709806"
---
# <a name="idispatchimpl-class"></a>Idispatchımpl sınıfı

Bir varsayılan uygulamasını sağlar `IDispatch` çift arabirim bir parçası.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0, 
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
[in] Çift arabirim.

*piid*<br/>
[in] Laboratuvardaki işaretçisi *T*.

*plibid*<br/>
[in] Arabirimi hakkında bilgi içeren tür kitaplığının Kitaplık kimliği için bir işaretçi. Varsayılan olarak, sunucu düzeyinde tür kitaplığı geçirilir.

*wMajor*<br/>
[in] Tür kitaplığının ana sürümü. Varsayılan değer 1'dir.

*wMinor*<br/>
[in] Tür kitaplığının bir alt sürümü. Varsayılan değer 0'dır.

*tihclass*<br/>
[in] İçin tür bilgilerini yönetmek için kullanılan sınıf *T*. Varsayılan değer olan `CComTypeInfoHolder`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Oluşturucu. Çağrıları `AddRef` çift arabirim için tür bilgilerini yöneten korumalı üye değişkeni üzerinde. Yıkıcı çağrıları `Release`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Bir ad kümesini karşılık gelen bir dağıtma tanımlayıcısı kümesine eşler.|
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Çift arabirim için tür bilgilerini alır.|
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Çift arabirim için tür bilgilerini olup olmadığını belirler.|
|[IDispatchImpl::Invoke](#invoke)|Çift arabirim tarafından kullanıma sunulan özellikler ve yöntemler erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

`IDispatchImpl` bir varsayılan uygulamasını sağlar `IDispatch` parçası olan bir nesne üzerinde herhangi bir çift arabirim. Çift arabirim türetildiği `IDispatch` ve yalnızca otomasyon uyumlu türleri kullanır. Bir dispinterface gibi çift arabirim bağlama erken ve geç bağlama destekler. Ancak, bir çift arabirim vtable bağlama de destekler.

Tipik bir uygulaması aşağıdaki örnekte `IDispatchImpl`.

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

Varsayılan olarak, `IDispatchImpl` sınıfı için tür bilgisi şuna *T* kayıt defteri. Bir kaydı arabirim uygulamak için kullanabileceğiniz `IDispatchImpl` önceden tanımlanmış sürüm numarasını kullanarak kayıt defteri erişim olmadan sınıfı. Oluşturursanız, bir `IDispatchImpl` 0xFFFF değeri olarak nesnesi *wMajor* ile 0xFFFF değeri olarak *wMinor*, `IDispatchImpl` sınıfı yerine .dll dosyasından tür kitaplığı alır kayıt defteri.

`IDispatchImpl` statik bir üye türü içeren `CComTypeInfoHolder` , çift arabirim için tür bilgilerini yönetir. Aynı çift uygulayan birden fazla nesneniz varsa arabirimi, yalnızca bir örneğini `CComTypeInfoHolder` kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`IDispatchImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="getidsofnames"></a>  IDispatchImpl::GetIDsOfNames

Bir ad kümesini karşılık gelen bir dağıtma tanımlayıcısı kümesine eşler.

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDispatch::getıdsofnames](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-getidsofnames) Windows SDK içinde.

##  <a name="gettypeinfo"></a>  IDispatchImpl::GetTypeInfo

Çift arabirim için tür bilgilerini alır.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDispatch::GetTypeInfo](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfo) Windows SDK içinde.

##  <a name="gettypeinfocount"></a>  IDispatchImpl::GetTypeInfoCount

Çift arabirim için tür bilgilerini olup olmadığını belirler.

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Açıklamalar

Bkz: `IDispatch::GetTypeInfoCount` Windows SDK içinde.

##  <a name="idispatchimpl"></a>  IDispatchImpl::IDispatchImpl

Oluşturucu. Çağrıları `AddRef` çift arabirim için tür bilgilerini yöneten korumalı üye değişkeni üzerinde. Yıkıcı çağrıları `Release`.

```
IDispatchImpl();
```

##  <a name="invoke"></a>  IDispatchImpl::Invoke

Çift arabirim tarafından kullanıma sunulan özellikler ve yöntemler erişim sağlar.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IDispatch::Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
