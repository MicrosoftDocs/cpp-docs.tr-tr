---
title: Iprovideclassınfo2ımpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: a7e0bd440e2e4bd8d32525fe4be6aaad2c401f6a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880628"
---
# <a name="iprovideclassinfo2impl-class"></a>Iprovideclassınfo2ımpl sınıfı
Bu sınıfın bir varsayılan uygulamayı sağlar [Iprovideclassınfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) ve [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) yöntemleri.  
  
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
 Coclass varsayılan dispinterface giden tanımlayıcısı için bir işaretçi.  
  
 *plibid*  
 Arabirimi hakkında bilgi içeren tür kitaplığının Kitaplık kimliği için bir işaretçi. Varsayılan olarak, sunucu düzeyinde tür kitaplığı geçirilir.  
  
 *wMajor*  
 Tür kitaplığının ana sürümü. Varsayılan değer 1’dir.  
  
 *wMinor*  
 Tür kitaplığının bir alt sürümü. Varsayılan değer 0’dır.  
  
 *tihclass*  
 Coclass tür bilgilerini yönetmek için kullanılan sınıf. Varsayılan değer `CComTypeInfoHolder` şeklindedir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Alır bir `ITypeInfo` coclass tür bilgileri işaretçisi.|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|Nesnenin giden dispinterface GUID'ini alır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|Coclass'ı için tür bilgilerini yönetir.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764) arabirimini genişletir [Iprovideclassınfo](http://msdn.microsoft.com/library/windows/desktop/ms687303) ekleyerek `GetGUID` yöntemi. Bir istemci kendi varsayılan olay kümesi için bir nesnenin giden arabirim IID'si almak bu yöntem sağlar. Sınıf `IProvideClassInfo2Impl` bir varsayılan uygulamayı sağlar `IProvideClassInfo` ve `IProvideClassInfo2` yöntemleri.  
  
 `IProvideClassInfo2Impl` statik bir üye türü içeren `CComTypeInfoHolder` , coclass'ı için tür bilgilerini yönetir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getclassinfo"></a>  IProvideClassInfo2Impl::GetClassInfo  
 Alır bir `ITypeInfo` coclass tür bilgileri işaretçisi.  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IProvideClassInfo::GetClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms690192) Windows SDK içinde.  
  
##  <a name="getguid"></a>  IProvideClassInfo2Impl::GetGUID  
 Nesnenin giden dispinterface GUID'ini alır.  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) Windows SDK içinde.  
  
##  <a name="iprovideclassinfo2impl"></a>  IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 Oluşturucu.  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları `AddRef` üzerinde [_tih](#_tih) üyesi. Yıkıcı çağrıları `Release`.  
  
##  <a name="_tih"></a>  IProvideClassInfo2Impl::_tih  
 Bu statik veri üyesi sınıfı şablon parametresi örneğidir *tihclass*, varsayılan olarak `CComTypeInfoHolder`.  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>Açıklamalar  
 `_tih` coclass'ı için tür bilgilerini yönetir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
