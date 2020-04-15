---
title: IDispatchImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
ms.openlocfilehash: 3b3899a0c4a49aa7fb1bd82af330f5f1cc7329c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329801"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl Sınıfı

Çift arabirimin `IDispatch` parçası için varsayılan bir uygulama sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

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
[içinde] Çift arayüz.

*piid*<br/>
[içinde] *T*IID için bir işaretçi .

*plibid*<br/>
[içinde] Arabirimi hakkında bilgi içeren tür kitaplığı LIBID için bir işaretçi. Varsayılan olarak, sunucu düzeyinde tür kitaplığı geçirilir.

*wMajor*<br/>
[içinde] Tür kitaplığın ana sürümü. Varsayılan olarak, değer 1'dir.

*wMinor*<br/>
[içinde] Tür kitaplığın küçük sürümü. Varsayılan olarak, değer 0'dır.

*tihclass*<br/>
[içinde] *T.* için tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan olarak, değer `CComTypeInfoHolder`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Oluşturucu. Çift `AddRef` arabirimin tür bilgilerini yöneten korumalı üye değişkenini çağırır. Yıkıcı arıyor. `Release`|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Bir ad kümesini karşılık gelen bir dağıtma tanımlayıcısı kümesine eşler.|
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Çift arabirimin tür bilgilerini alır.|
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Çift arabirim için tür bilgisi olup olmadığını belirler.|
|[IDispatchImpl::Invoke](#invoke)|Çift arabirimin maruz kaçtığı yöntem ve özelliklere erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

`IDispatchImpl`bir nesne üzerinde `IDispatch` herhangi bir çift arabirim parçası için varsayılan bir uygulama sağlar. Çift arabirim yalnızca `IDispatch` Otomasyon uyumlu türlerden kaynaklanır ve kullanır. Bir dispinterface gibi, çift arabirim erken bağlama ve geç bağlama destekler; ancak, çift arabirim de vtable bağlama destekler.

Aşağıdaki örnekte tipik bir `IDispatchImpl`uygulama gösterir.

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

Varsayılan olarak, `IDispatchImpl` sınıf kayıt defterinde *T'nin* tür bilgilerini arar. Kayıtsız bir arabirim uygulamak için, `IDispatchImpl` önceden tanımlanmış bir sürüm numarası kullanarak kayıt defterine erişmeden sınıfı kullanabilirsiniz. WMajor değeri `IDispatchImpl` olarak 0xFFFF ve *wMinor* değeri olarak 0xFFFF *wMinor*olan bir `IDispatchImpl` nesne oluşturursanız, sınıf kayıt defteri yerine .dll dosyasından tür kitaplığını alır.

`IDispatchImpl`çift arabirimin tür `CComTypeInfoHolder` bilgilerini yöneten statik bir tür üyesi içerir. Aynı çift arabirimi uygulayan birden çok nesneniz varsa, yalnızca bir örneği `CComTypeInfoHolder` kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`IDispatchImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="idispatchimplgetidsofnames"></a><a name="getidsofnames"></a>IDispatchImpl::GetIDsOfNames

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

Bkz. IDispatch::Windows SDK'daki [GetIDsOfNames.](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames)

## <a name="idispatchimplgettypeinfo"></a><a name="gettypeinfo"></a>IDispatchImpl::GetTypeInfo

Çift arabirimin tür bilgilerini alır.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IDispatch::Windows SDK'da [TypeInfo'yu alın.](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo)

## <a name="idispatchimplgettypeinfocount"></a><a name="gettypeinfocount"></a>IDispatchImpl::GetTypeInfoCount

Çift arabirim için tür bilgisi olup olmadığını belirler.

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Açıklamalar

Windows `IDispatch::GetTypeInfoCount` SDK'da bkz.

## <a name="idispatchimplidispatchimpl"></a><a name="idispatchimpl"></a>IDispatchImpl::IDispatchImpl

Oluşturucu. Çift `AddRef` arabirimin tür bilgilerini yöneten korumalı üye değişkenini çağırır. Yıkıcı arıyor. `Release`

```
IDispatchImpl();
```

## <a name="idispatchimplinvoke"></a><a name="invoke"></a>IDispatchImpl::Invoke

Çift arabirimin maruz kaçtığı yöntem ve özelliklere erişim sağlar.

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

Bkz. [IDispatch::Windows](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) SDK'da çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
