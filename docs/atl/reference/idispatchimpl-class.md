---
title: IDispatchImpl sınıfı
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
ms.openlocfilehash: 7e9cb903742cdc31c1d9bba2c4aabbb0472407c1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495959"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl sınıfı

İkili arabirimin `IDispatch` parçası için varsayılan bir uygulama sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

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

*ŞI*<br/>
'ndaki Çift arabirim.

*piıd*<br/>
'ndaki *T*IID 'sine yönelik bir işaretçi.

*plibıd*<br/>
'ndaki Arabirim hakkında bilgi içeren tür kitaplığının LIBıD işaretçisi. Varsayılan olarak, sunucu düzeyi tür kitaplığı geçirilir.

*Wana*<br/>
'ndaki Tür kitaplığının ana sürümü. Varsayılan olarak değer 1 ' dir.

*wMinor*<br/>
'ndaki Tür kitaplığının ikincil sürümü. Varsayılan olarak, değeri 0 ' dır.

*tihclass*<br/>
'ndaki *T*için tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan olarak, değeri `CComTypeInfoHolder`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[IDispatchImpl:: IDispatchImpl](#idispatchimpl)|Oluşturucu. Korumalı `AddRef` üye değişkeninde çift arabirim için tür bilgilerini yöneten çağrılar. Yıkıcı çağırır `Release`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IDispatchImpl:: GetIDsOfNames](#getidsofnames)|Bir ad kümesini karşılık gelen bir dağıtma tanımlayıcısı kümesine eşler.|
|[IDispatchImpl:: GetTypeInfo](#gettypeinfo)|Çift arabirim için tür bilgilerini alır.|
|[IDispatchImpl:: GetTypeInfoCount](#gettypeinfocount)|Çift arabirim için kullanılabilir tür bilgisi olup olmadığını belirler.|
|[IDispatchImpl:: Invoke](#invoke)|Çift arabirim tarafından kullanıma sunulan yöntemlere ve özelliklere erişim sağlar.|

## <a name="remarks"></a>Açıklamalar

`IDispatchImpl`bir nesne üzerinde herhangi bir çift `IDispatch` arabirimin parçası için varsayılan bir uygulama sağlar. Çift arabirim ' dan `IDispatch` türetilir ve yalnızca otomasyon ile uyumlu türleri kullanır. Bir dispınterface gibi, bir ikili arabirim erken bağlamayı ve geç bağlamayı destekler; Ancak, çift bir arabirim vtable bağlamasını da destekler.

Aşağıdaki örnek, öğesinin `IDispatchImpl`tipik bir uygulamasını gösterir.

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

Varsayılan olarak, `IDispatchImpl` sınıfı, kayıt defterindeki *T* için tür bilgilerini arar. Kayıtlı olmayan bir arabirim uygulamak için, önceden tanımlanmış bir `IDispatchImpl` sürüm numarası kullanarak bu sınıfı, kayıt defterine erişmeden kullanabilirsiniz. *Wana* için değer `IDispatchImpl` olarak 0xFFFF olan bir nesne oluşturursanız ve *wMinor*için değer olarak 0xFFFF yazarsanız, `IDispatchImpl` sınıf kayıt defteri yerine. dll dosyasından tür kitaplığını alır.

`IDispatchImpl`Çift arabirim için tür bilgilerini yöneten `CComTypeInfoHolder` türün statik bir üyesini içerir. Aynı çift arabirimi uygulayan birden fazla nesneniz varsa, yalnızca bir örneği `CComTypeInfoHolder` kullanılır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`IDispatchImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="getidsofnames"></a>IDispatchImpl:: GetIDsOfNames

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

Windows SDK için bkz. [IDispatch:: GetIDsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) .

##  <a name="gettypeinfo"></a>IDispatchImpl:: GetTypeInfo

Çift arabirim için tür bilgilerini alır.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [IDispatch:: GetTypeInfo](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) bölümüne bakın.

##  <a name="gettypeinfocount"></a>IDispatchImpl:: GetTypeInfoCount

Çift arabirim için kullanılabilir tür bilgisi olup olmadığını belirler.

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK `IDispatch::GetTypeInfoCount` bakın.

##  <a name="idispatchimpl"></a>IDispatchImpl:: IDispatchImpl

Oluşturucu. Korumalı `AddRef` üye değişkeninde çift arabirim için tür bilgilerini yöneten çağrılar. Yıkıcı çağırır `Release`.

```
IDispatchImpl();
```

##  <a name="invoke"></a>IDispatchImpl:: Invoke

Çift arabirim tarafından kullanıma sunulan yöntemlere ve özelliklere erişim sağlar.

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

Windows SDK için bkz. [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
