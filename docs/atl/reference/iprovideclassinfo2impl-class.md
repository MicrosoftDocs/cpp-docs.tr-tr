---
title: IProvideClassInfo2Impl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
dev_langs:
- C++
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a970b0258c8d353dabad96d712598416caf2acb4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361351"
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl sınıfı
Bu sınıf, bir varsayılan uygulamasını sağlar [IProvideClassInfo'yu](http://msdn.microsoft.com/library/windows/desktop/ms687303) ve [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) yöntemleri.  
  
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
 *pcoclsid*  
 Coclass tanımlayıcısı için bir işaretçi.  
  
 *psrcid*  
 Coclass varsayılan görüntüleme arabirimi giden tanımlayıcısı için bir işaretçi.  
  
 `plibid`  
 Arabirimi hakkında bilgi içeren tür kitaplığı kimliği için bir işaretçi. Varsayılan olarak, sunucu düzeyi tür kitaplığı geçirilir.  
  
 `wMajor`  
 Tür kitaplığı ana sürümü. Varsayılan değer 1’dir.  
  
 `wMinor`  
 Tür kitaplığı küçük sürümü. Varsayılan değer 0’dır.  
  
 `tihclass`  
 Coclass tür bilgilerini yönetmek için kullanılan bir sınıftır. Varsayılan değer `CComTypeInfoHolder` şeklindedir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Alır bir **ITypeInfo** coclass tür bilgileri işaretçi.|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Nesnenin giden görüntüleme arabirimi için GUID alır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|Coclass'ı türü bilgilerini yönetir.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) arabirimi genişletiyor [IProvideClassInfo'yu](http://msdn.microsoft.com/library/windows/desktop/ms687303) ekleyerek `GetGUID` yöntemi. Bu yöntem, varsayılan olay kümesi için bir nesnenin giden arabirimi IID almak bir istemcinin sağlar. Sınıf `IProvideClassInfo2Impl` bir varsayılan uygulamayı sağlar **IProvideClassInfo'yu** ve `IProvideClassInfo2` yöntemleri.  
  
 `IProvideClassInfo2Impl` statik bir üyenin türü içeren `CComTypeInfoHolder` coclass'ı için tür bilgisi yönetir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getclassinfo"></a>  IProvideClassInfo2Impl::GetClassInfo  
 Alır bir `ITypeInfo` coclass tür bilgileri işaretçi.  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IProvideClassInfo::GetClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms690192) Windows SDK.  
  
##  <a name="getguid"></a>  IProvideClassInfo2Impl::GetGUID  
 Nesnenin giden görüntüleme arabirimi için GUID alır.  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) Windows SDK.  
  
##  <a name="iprovideclassinfo2impl"></a>  IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 Oluşturucu.  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları `AddRef` üzerinde [_tih](#_tih) üyesi. Yıkıcı çağrıları **sürüm**.  
  
##  <a name="_tih"></a>  IProvideClassInfo2Impl::_tih  
 Bu statik veri üyesi sınıfı şablon parametresi örneği olan `tihclass`, varsayılan olarak `CComTypeInfoHolder`.  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>Açıklamalar  
 `_tih` Coclass'ı türü bilgilerini yönetir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
