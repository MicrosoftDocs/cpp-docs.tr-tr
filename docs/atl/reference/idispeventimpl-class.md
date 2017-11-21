---
title: "IDispEventImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDispEventImpl
- ATLCOM/ATL::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::IDispEventImpl
- ATLCOM/ATL::IDispEventImpl::GetFuncInfoFromId
- ATLCOM/ATL::IDispEventImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventImpl::GetUserDefinedType
dev_langs: C++
helpviewer_keywords: IDispEventImpl class
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c51a305d1b858aaa31a9bf700e825848ba3eb563
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="idispeventimpl-class"></a>IDispEventImpl sınıfı
Bu sınıf uygulamaları sağlar `IDispatch` yöntemleri.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <UINT nID, class T,
    const IID* pdiid = &IID_NULL,
    const GUID* plibid = &GUID_NULL,
    WORD wMajor = 0,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE IDispEventImpl : public IDispEventSimpleImpl<nID, T, pdiid>
```  
  
#### <a name="parameters"></a>Parametreler  
 `nID`  
 Kaynak nesne için benzersiz bir tanımlayıcı. Zaman `IDispEventImpl` taban sınıf bileşik denetim için bu parametre için istenen kapsanan denetiminin kaynak Kimliğini kullanın. Diğer durumlarda, rasgele pozitif bir tamsayı kullanın.  
  
 `T`  
 Türetilmiş kullanıcının sınıfı `IDispEventImpl`.  
  
 `pdiid`  
 Bu sınıf tarafından uygulanan olay görüntüleme arabirimi IID yönelik işaretçi. Bu arabirim tarafından belirtilen tür kitaplığı tanımlanmalıdır `plibid`, `wMajor`, ve `wMinor`.  
  
 `plibid`  
 Tarafından için gönderme arabirimi tanımlar tür kitaplığı için bir işaretçi işaret `pdiid`. Varsa **& GUID_NULL**, tür kitaplığı olayları kaynak nesneden yüklenecek.  
  
 `wMajor`  
 Tür kitaplığı ana sürümü. Varsayılan değer 0’dır.  
  
 `wMinor`  
 Tür kitaplığı küçük sürümü. Varsayılan değer 0’dır.  
  
 `tihclass`  
 Tür bilgilerini yönetmek için kullanılan sınıf `T`. Varsayılan değer türü sınıfıdır `CComTypeInfoHolder`; ancak, bir türün bir sınıf dışında sağlayarak bu şablon parametresi geçersiz kılabilirsiniz `CComTypeInfoHolder`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IDispEventImpl::_tihclass](../../atl/reference/idispeventimpl-class.md)|Tür bilgilerini yönetmek için kullanılan bir sınıftır. Varsayılan olarak, `CComTypeInfoHolder`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IDispEventImpl::IDispEventImpl](#idispeventimpl)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IDispEventImpl::GetFuncInfoFromId](#getfuncinfofromid)|Belirtilen gönderme tanımlayıcısı işlevi dizini bulur.|  
|[IDispEventImpl::GetIDsOfNames](#getidsofnames)|Tek bir üyeyi ve isteğe bağlı bir bağımsız değişken adları kümesi tamsayı DISPID değerleri karşılık gelen bir dizi eşler.|  
|[IDispEventImpl::GetTypeInfo](#gettypeinfo)|Bir nesne türü bilgilerini alır.|  
|[IDispEventImpl::GetTypeInfoCount](#gettypeinfocount)|Tür bilgileri arabirimleri sayısını alır.|  
|[IDispEventImpl::GetUserDefinedType](#getuserdefinedtype)|Kullanıcı tanımlı bir türünün temel türünü alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IDispEventImpl`Bu arabirimdeki her yöntem/olay uygulama kodunu girmesini gerek olmadan bir olay görüntüleme arabirimi uygulayan bir yolunu sunar. `IDispEventImpl`uygulamaları sağlar `IDispatch` yöntemleri. Yalnızca işlemede ilgilenen olayları için uygulamaları sağlamanız gerekir.  
  
 `IDispEventImpl`Rota olaylar için uygun işleyiciyi işlevi sınıfınıza olay havuz eşlemesinde ile birlikte çalışır. Bu sınıf kullanmak için:  
  

 Ekleme bir [SINK_ENTRY](composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex) ele almak istediğiniz her nesne üzerinde her olay için olay havuz eşlemesi makrosuna. Kullanırken `IDispEventImpl` bileşik denetim temel sınıf olarak çağırabilirsiniz [AtlAdviseSinkMap](connection-point-global-functions.md#atladvisesinkmap) kurmak ve tüm girişleri olay eşlemesi havuz için olay kaynağı ile bağlantıyı kesin. Diğer durumlarda ya da daha fazla denetim için [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) kaynak nesne ile temel sınıf arasında bağlantı kurmak için. Çağrı [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise) bağlantıyı kesmek için.  

  
 Öğesinden türetilmelidir `IDispEventImpl` (için benzersiz bir değer kullanarak `nID`) ihtiyaç duyduğunuz olayları işlemek her nesne için. Farklı kaynak nesneyle bildiren bir kaynak nesne karşı unadvising tarafından temel sınıfı yeniden kullanabilirsiniz, ancak tek bir nesne tarafından aynı anda işlenebilir kaynak nesneleri maksimum sayısı sayısıyla sınırlıdır `IDispEventImpl` temel sınıflar.  
  
 `IDispEventImpl`aynı işlevselliği sunar [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md), sağlanan bir işaretçi olarak sahip olmak yerine bir tür kitaplığı arabirimi hakkında bilgi türü alır dışında bir [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) yapısı. Kullanım `IDispEventSimpleImpl` zaman bilgisayarınızda değil olay arabirimini açıklayan bir tür kitaplığı veya tür kitaplığını kullanma ile ilgili ek yükü önlemek istiyorsanız.  
  
> [!NOTE]
> `IDispEventImpl`ve `IDispEventSimpleImpl` kendi uygulamasını sağlamak **IUnknown::QueryInterface** her etkinleştirme `IDispEventImpl` ve `IDispEventSimpleImpl` temel hala sınıfı doğrudan erişim sağlarken ayrı bir COM kimliği olarak davranacak şekilde sınıfı Ana COM nesnesi üyeleri.  
  
 ActiveX olay havuzlarını yalnızca destekler dönüş türü değerleri HRESULT ya da olay işleyicisi yöntemlerden void uyarlamasını CE ATL; herhangi bir dönüş değeri desteklenmez ve davranışını tanımlanmadı.  
  
 Daha fazla bilgi için bkz: [destekleyen IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getfuncinfofromid"></a>IDispEventImpl::GetFuncInfoFromId  
 Belirtilen gönderme tanımlayıcısı işlevi dizini bulur.  
  
```
HRESULT GetFuncInfoFromId(
    const IID& iid,
    DISPID dispidMember,
    LCID lcid,
    _ATL_FUNC_INFO& info);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] İşlev Kimliğini referansı.  
  
 *dispidMember*  
 [in] İşlev gönderme kimliği.  
  
 `lcid`  
 [in] Yerel ayar bağlamı işlevi kimliği.  
  
 `info`  
 [in] İşlev nasıl çağrılır belirten yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="getidsofnames"></a>IDispEventImpl::GetIDsOfNames  
 Tamsayı yapılan sonraki çağrılar kullanılabilir DISPID değerleri karşılık gelen bir dizi tek bir üyeyi ve isteğe bağlı bir bağımsız değişken adları kümesi eşlendiği [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
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
  
##  <a name="gettypeinfo"></a>IDispEventImpl::GetTypeInfo  
 Bir nesne için tür bilgilerini alır ve bu da bir arabirimin tür bilgisini almak için kullanılabilir.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettypeinfocount"></a>IDispEventImpl::GetTypeInfoCount  
 Bir nesnenin sağladığı tür bilgisi arabirimlerinin sayısını alır (0 ya da 1).  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) Windows SDK.  
  
##  <a name="getuserdefinedtype"></a>IDispEventImpl::GetUserDefinedType  
 Kullanıcı tanımlı bir türünün temel türünü alır.  
  
```
VARTYPE GetUserDefinedType(
    ITypeInfo* pTI,
    HREFTYPE hrt);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTI`  
 [in] Bir işaretçi [ITypeInfo](http://msdn.microsoft.com/en-us/f3356463-3373-4279-bae1-953378aa2680) kullanıcı tanımlı tür içeren arabirimi.  
  
 *hrt*  
 [in] Alınacak türü açıklaması için bir tanıtıcı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Değişken türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ITypeInfo::GetRefTypeInfo](http://msdn.microsoft.com/en-us/61d3b31d-6591-4e55-9e82-5246a168be00).  
  
##  <a name="idispeventimpl"></a>IDispEventImpl::IDispEventImpl  
 Oluşturucu. Sınıf şablonu parametrelerinin değerlerini depolayan `plibid`, `pdiid`, `wMajor`, ve `wMinor`.  
  
```
IDispEventImpl();
```  
  
##  <a name="tihclass"></a>IDispEventImpl::tihclass  
 Bu typedef sınıfı şablon parametresi örneği olan `tihclass`.  
  
```
typedef tihclass _tihclass;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bir sınıftır `CComTypeInfoHolder`. `CComTypeInfoHolder`sınıf türü bilgilerini yönetir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_ATL_FUNC_INFO yapısı](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl sınıfı](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY](composite-control-macros.md#sink_entry)   
 [SINK_ENTRY_EX](composite-control-macros.md#sink_entry_ex)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)