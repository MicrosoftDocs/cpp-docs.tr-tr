---
title: IDispEventSimpleImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl
- ATLCOM/ATL::IDispEventSimpleImpl::Advise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventAdvise
- ATLCOM/ATL::IDispEventSimpleImpl::DispEventUnadvise
- ATLCOM/ATL::IDispEventSimpleImpl::GetIDsOfNames
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfo
- ATLCOM/ATL::IDispEventSimpleImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispEventSimpleImpl::Invoke
- ATLCOM/ATL::IDispEventSimpleImpl::Unadvise
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89f565c1e32f1208fbb039321d26b9175596d57e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="idispeventsimpleimpl-class"></a>IDispEventSimpleImpl sınıfı
Bu sınıf uygulamaları sağlar `IDispatch` bir tür kitaplığından türü bilgileri alınıyor olmadan yöntemleri.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <UINT nID, class T, const IID* pdiid>  
class ATL_NO_VTABLE IDispEventSimpleImpl : public _IDispEventLocator<nID, pdiid>
```    
  
#### <a name="parameters"></a>Parametreler  
 `nID`  
 Kaynak nesne için benzersiz bir tanımlayıcı. Zaman `IDispEventSimpleImpl` taban sınıf bileşik denetim için bu parametre için istenen kapsanan denetiminin kaynak Kimliğini kullanın. Diğer durumlarda, rasgele pozitif bir tamsayı kullanın.  
  
 `T`  
 Türetilmiş kullanıcının sınıfı `IDispEventSimpleImpl`.  
  
 `pdiid`  
 Bu sınıf tarafından uygulanan olay görüntüleme arabirimi IID yönelik işaretçi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IDispEventSimpleImpl::Advise](#advise)|Varsayılan olay kaynağı ile bağlantı kurar.|  
|[IDispEventSimpleImpl::DispEventAdvise](#dispeventadvise)|Olay kaynağı ile bağlantı kurar.|  
|[IDispEventSimpleImpl::DispEventUnadvise](#dispeventunadvise)|Olay kaynağı ile bağlantıyı keser.|  
|[IDispEventSimpleImpl::GetIDsOfNames](#getidsofnames)|Döndürür **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfo](#gettypeinfo)|Döndürür **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::GetTypeInfoCount](#gettypeinfocount)|Döndürür **E_NOTIMPL**.|  
|[IDispEventSimpleImpl::Invoke](#invoke)|Olay işleyicileri çağrıları olay havuz harita listelenir.|  
|[IDispEventSimpleImpl::Unadvise](#unadvise)|Varsayılan olay kaynağı ile bağlantıyı keser.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IDispEventSimpleImpl` Bu arabirimdeki her yöntem/olay uygulama kodunu girmesini gerek olmadan bir olay görüntüleme arabirimi uygulayan bir yolunu sunar. `IDispEventSimpleImpl` uygulamaları sağlar `IDispatch` yöntemleri. Yalnızca işlemede ilgilenen olayları için uygulamaları sağlamanız gerekir.  
  
 `IDispEventSimpleImpl` Rota olaylar için uygun işleyiciyi işlevi sınıfınıza olay havuz eşlemesinde ile birlikte çalışır. Bu sınıf kullanmak için:  
  
-   Ekleme bir [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) ele almak istediğiniz her nesne üzerinde her olay için olay havuz eşlemesi makrosuna.  
  
-   Tür bilgileri her olay için bir işaretçi geçirerek tedarik bir [_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md) her giriş için bir parametre olarak yapısı. X86 üzerinde bir platform `_ATL_FUNC_INFO.cc` değeri __stdcall yöntemini çağırarak geri çağırma işlevi ile CC_CDECL olmalıdır.  
  
-   Çağrı [DispEventAdvise](#dispeventadvise) kaynak nesne ile temel sınıf arasında bağlantı kurmak için.  
  
-   Çağrı [DispEventUnadvise](#dispeventunadvise) bağlantıyı kesmek için.  
  
 Öğesinden türetilmelidir `IDispEventSimpleImpl` (için benzersiz bir değer kullanarak `nID`) ihtiyaç duyduğunuz olayları işlemek her nesne için. Farklı kaynak nesneyle bildiren bir kaynak nesne karşı unadvising tarafından temel sınıfı yeniden kullanabilirsiniz, ancak tek bir nesne tarafından aynı anda işlenebilir kaynak nesneleri maksimum sayısı sayısıyla sınırlıdır `IDispEventSimpleImpl` temel sınıflar.  
  
 **IDispEventSimplImpl** aynı işlevselliği sunar [IDispEventImpl](../../atl/reference/idispeventimpl-class.md), tür bilgilerini arabirimi hakkında bir tür kitaplığından almaz dışında. Yalnızca temel kod sihirbazları oluşturma `IDispEventImpl`, ancak kullanabilirsiniz `IDispEventSimpleImpl` kodu el ile ekleyerek. Kullanım `IDispEventSimpleImpl` zaman yok olay arabirimini açıklayan bir tür kitaplığı kurduğunuz veya tür kitaplığını kullanma ile ilgili ek yükü önlemek istiyorsanız.  
  
> [!NOTE]
> `IDispEventImpl` ve `IDispEventSimpleImpl` kendi uygulamasını sağlamak **IUnknown::QueryInterface** her etkinleştirme `IDispEventImpl` veya `IDispEventSimpleImpl` temel hala sınıfı üyeleri doğrudan erişim sağlarken ayrı bir COM kimliği olarak davranacak şekilde sınıfı ana, COM nesnesi.  
  
 ActiveX olay havuzlarını yalnızca destekler dönüş türü değerleri HRESULT ya da olay işleyicisi yöntemlerden void uyarlamasını CE ATL; herhangi bir dönüş değeri desteklenmez ve davranışını tanımlanmadı.  
  
 Daha fazla bilgi için bkz: [destekleyen IDispEventImpl](../../atl/supporting-idispeventimpl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="advise"></a>  IDispEventSimpleImpl::Advise  
 Tarafından temsil edilen olay kaynağı ile bağlantı kurmak için bu yöntemi çağırın *pUnk*.  
  
```
HRESULT Advise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] Bir işaretçi **IUnknown** olay kaynağı nesnesinin arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` veya herhangi bir hata `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantı kurulduktan sonra gelen olaylar *pUnk* olay havuz eşlemesi yapmamanız sınıfınızda işleyicilere yönlendirilir.  
  
> [!NOTE]
>  Birden çok from sınıfınız türetilen varsa `IDispEventSimpleImpl` sınıfları, bu yönteme çağrıları ilgilendiğiniz belirli bir temel sınıf çağrısıyla kapsamı tarafından belirsizliğini ortadan kaldırmak gerekir.  
  
 `Advise` bir bağlantı kurar isteğe bağlı olarak varsayılan olay kaynağı ile nesnesi tarafından belirlenen varsayılan olay kaynağı IID alır [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).  
  
##  <a name="dispeventadvise"></a>  IDispEventSimpleImpl::DispEventAdvise  
 Tarafından temsil edilen olay kaynağı ile bağlantı kurmak için bu yöntemi çağırın *pUnk*.  
  
```
HRESULT DispEventAdvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] Bir işaretçi **IUnknown** olay kaynağı nesnesinin arabirimi.  
  
 `piid`  
 Olay kaynağı nesnesine IID gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` veya herhangi bir hata `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuç olarak, gelen olaylar *pUnk* olay havuz eşlemesi yapmamanız sınıfınızda işleyicilere yönlendirilir.  
  
> [!NOTE]
>  Birden çok from sınıfınız türetilen varsa `IDispEventSimpleImpl` sınıfları, bu yönteme çağrıları ilgilendiğiniz belirli bir temel sınıf çağrısıyla kapsamı tarafından belirsizliğini ortadan kaldırmak gerekir.  
  
 `DispEventAdvise` Belirtilen olay kaynağı ile bağlantı kurar `pdiid`.  
  
##  <a name="dispeventunadvise"></a>  IDispEventSimpleImpl::DispEventUnadvise  
 Tarafından temsil edilen olay kaynağı ile bağlantıyı keser *pUnk*.  
  
```
HRESULT DispEventUnadvise(IUnknown* pUnk  const IID* piid);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] Bir işaretçi **IUnknown** olay kaynağı nesnesinin arabirimi.  
  
 `piid`  
 Olay kaynağı nesnesine IID gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` veya herhangi bir hata `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantı kesildiğinde sonra olayları olay havuz eşlemesinde listelenen işleyici işlevleri artık yönlendirilir.  
  
> [!NOTE]
>  Birden çok from sınıfınız türetilen varsa `IDispEventSimpleImpl` sınıfları, bu yönteme çağrıları ilgilendiğiniz belirli bir temel sınıf çağrısıyla kapsamı tarafından belirsizliğini ortadan kaldırmak gerekir.  
  
 `DispEventAdvise` Belirtilen olay kaynağı ile kurulan bağlantıyı keser `pdiid`.  
  
##  <a name="getidsofnames"></a>  IDispEventSimpleImpl::GetIDsOfNames  
 Bu uygulaması, **IDispatch::GetIDsOfNames** döndürür **E_NOTIMPL**.  
  
```
STDMETHOD(GetIDsOfNames)(
    REFIID /* riid */,
    LPOLESTR* /* rgszNames */,
    UINT /* cNames */,
    LCID /* lcid */,
    DISPID* /* rgdispid */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDispatch::GetIDsOfNames](http://msdn.microsoft.com/en-us/6f6cf233-3481-436e-8d6a-51f93bf91619) Windows SDK.  
  
##  <a name="gettypeinfo"></a>  IDispEventSimpleImpl::GetTypeInfo  
 Bu uygulaması, **IDispatch::GetTypeInfo** döndürür **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfo)(
    UINT /* itinfo */,
    LCID /* lcid */,
    ITypeInfo** /* pptinfo */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDispatch::GetTypeInfo](http://msdn.microsoft.com/en-us/cc1ec9aa-6c40-4e70-819c-a7c6dd6b8c99) Windows SDK.  
  
##  <a name="gettypeinfocount"></a>  IDispEventSimpleImpl::GetTypeInfoCount  
 Bu uygulaması, **IDispatch::GetTypeInfoCount** döndürür **E_NOTIMPL**.  
  
```
STDMETHOD(GetTypeInfoCount)(UINT* /* pctinfo */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12) Windows SDK.  
  
##  <a name="invoke"></a>  IDispEventSimpleImpl::Invoke  
 Bu uygulaması, **IDispatch::Invoke** olay işleyicileri listelenen olay havuz harita çağrıları.  
  
```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID /* riid */,
    LCID lcid,
    WORD /* wFlags */,
    DISPPARMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* /* pexcepinfo */,
    UINT* /* puArgErr */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
##  <a name="unadvise"></a>  IDispEventSimpleImpl::Unadvise  
 Tarafından temsil edilen olay kaynağı ile bağlantıyı keser *pUnk*.  
  
```
HRESULT Unadvise(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] Bir işaretçi **IUnknown** olay kaynağı nesnesinin arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `S_OK` veya herhangi bir hata `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantı kesildiğinde sonra olayları olay havuz eşlemesinde listelenen işleyici işlevleri artık yönlendirilir.  
  
> [!NOTE]
>  Birden çok from sınıfınız türetilen varsa `IDispEventSimpleImpl` sınıfları, bu yönteme çağrıları ilgilendiğiniz belirli bir temel sınıf çağrısıyla kapsamı tarafından belirsizliğini ortadan kaldırmak gerekir.  
  
 `Unadvise` Belirtilen varsayılan olay kaynağı ile kurulan bağlantıyı keser `pdiid`.  
  
 **Unavise** sonları bir varsayılan olay kaynağı ile bağlantı nesnesi tarafından belirlenen varsayılan olay kaynağı IID alır [AtlGetObjectSourceInterface](composite-control-global-functions.md#atlgetobjectsourceinterface).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_ATL_FUNC_INFO yapısı](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl sınıfı](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl sınıfı](../../atl/reference/idispeventimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
