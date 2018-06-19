---
title: IDispatchImpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: 7fddf556eba07264f6ea0b01edea3e3d1e8a3a7b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364372"
---
# <a name="idispatchimpl-class"></a>IDispatchImpl sınıfı
Bir varsayılan uygulamasını sağlar `IDispatch` çift arabirim parçası.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
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
 [in] `T`  
 Çift arabirim.  
  
 [in] `piid`  
 Bir işaretçi IID `T`.  
  
 [in] `plibid`  
 Arabirimi hakkında bilgi içeren tür kitaplığı kimliği için bir işaretçi. Varsayılan olarak, sunucu düzeyi tür kitaplığı geçirilir.  
  
 [in] `wMajor`  
 Tür kitaplığı ana sürümü. Varsayılan değer 1'dir.  
  
 [in] `wMinor`  
 Tür kitaplığı küçük sürümü. Varsayılan olarak, değeri 0'dır.  
  
 [in] `tihclass`  
 Tür bilgilerini yönetmek için kullanılan sınıf `T`. Varsayılan değer olan `CComTypeInfoHolder`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Oluşturucu. Çağrıları `AddRef` çift arabirim türü bilgilerini yöneten korumalı üye değişkeni üzerinde. Yıkıcı çağrıları `Release`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IDispatchImpl::GetIDsOfNames](#getidsofnames)|Bir ad kümesini karşılık gelen bir dağıtma tanımlayıcısı kümesine eşler.|  
|[IDispatchImpl::GetTypeInfo](#gettypeinfo)|Çift arabirim türü bilgilerini alır.|  
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Tür bilgileri çift arabirim için kullanılabilir olup olmadığını belirler.|  
|[IDispatchImpl::Invoke](#invoke)|Çift arabirim tarafından kullanıma sunulan özellikler ve yöntemler erişim sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IDispatchImpl` bir varsayılan uygulamasını sağlar `IDispatch` herhangi bir nesne üzerinde çift arabirim parçası. Çift arabirim türetilen `IDispatch` ve yalnızca otomasyon uyumlu türleri kullanır. Bir görüntüleme arabirimi gibi erken bağlama ve geç bağlama çift arabirim destekler; Ancak, bir çift arabirim vtable bağlama destekler.  
  
 Aşağıdaki örnek, tipik bir uyarlamasını gösterir `IDispatchImpl`.  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]  
  
 Varsayılan olarak, `IDispatchImpl` sınıfı için tür bilgisi arayan `T` kayıt defterinde. Bir kaydı arabirimi uygulamak için kullanabileceğiniz `IDispatchImpl` önceden tanımlı sürüm numarası kullanarak kayıt defterini erişim olmadan sınıfı. Oluşturursanız, bir `IDispatchImpl` değeri olarak 0xFFFF olan nesneyi `wMajor` ve 0xFFFF değeri olarak `wMinor`, `IDispatchImpl` sınıfı, kayıt defteri yerine .dll dosyasından tür kitaplığı alır.  
  
 `IDispatchImpl` statik bir üyenin türü içeren `CComTypeInfoHolder` çift arabirim türü bilgilerini yönetir. Aynı çift uygulayan birden fazla nesne varsa, arabirim, yalnızca bir örneği `CComTypeInfoHolder` kullanılır.  
  
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
 Bkz: [IDispatch::GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) Windows SDK.  
  
##  <a name="gettypeinfo"></a>  IDispatchImpl::GetTypeInfo  
 Çift arabirim türü bilgilerini alır.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDispatch::GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) Windows SDK.  
  
##  <a name="gettypeinfocount"></a>  IDispatchImpl::GetTypeInfoCount  
 Tür bilgileri çift arabirim için kullanılabilir olup olmadığını belirler.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: `IDispatch::GetTypeInfoCount` Windows SDK.  
  
##  <a name="idispatchimpl"></a>  IDispatchImpl::IDispatchImpl  
 Oluşturucu. Çağrıları `AddRef` çift arabirim türü bilgilerini yöneten korumalı üye değişkeni üzerinde. Yıkıcı çağrıları **sürüm**.  
  
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
 Bkz: [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
