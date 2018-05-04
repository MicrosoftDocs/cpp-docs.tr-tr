---
title: IViewObjectExImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c51bc9e5feb02d837c37341b82a1fc19a3cea558
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve varsayılan uygulamalarını sağlar [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), ve [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)arabirimleri.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IViewObjectExImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|Bir cihaz bağlamı üzerine denetim gösterimini çizer.|  
|[IViewObjectExImpl::Freeze](#freeze)|Bir denetim çizilmiş gösterimini kadar değişmeyeceği şekilde donuyor bir `Unfreeze`. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|Varsa mevcut bir danışma havuz bağlantı denetimi alır.|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|Çizim için denetim tarafından kullanılan mantıksal palet döndürür. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetExtent](#getextent)|Denetimin görüntüleme boyutu HIMETRIC birimler (birim başına 0,01 milimetre) denetim sınıfı veri üyesi alır [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|Kullanıcı yeniden boyutlandırır olarak kullanılmak üzere nesnesinin kapsayıcısından boyutlandırma ipuçlarını sağlar.|  
|[IViewObjectExImpl::GetRect](#getrect)|İstenen bir çizim yönü açıklayan bir dikdörtgen döndürür. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|Nesne ve hangi çizim yönlerini desteklenen opaklık hakkındaki bilgileri döndürür.|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|Belirtilen nokta belirtilen dikdörtgenin nedir ve döndürür denetler bir [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) değeri `pHitResult`.|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|Denetimin görüntüleme dikdörtgenini çakışıyor belirtilen konum dikdörtgenin içindeki herhangi bir noktasını döndürür olup olmadığını denetler ve bir **HITRESULT** değeri `pHitResult`.|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|Havuz değişiklikleri denetimin görünüm hakkında bildirim almak için denetimi ve bir öneri havuz arasında bir bağlantı kurar.|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|Denetim çizilmiş gösterimini canlandırır. ATL uygulamasını döndürür **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763), [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318), ve [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) arabirimleri kendisini doğrudan görüntülemek ve oluşturmak ve bildirmek için bir öneri havuz yönetmek bir denetimini etkinleştirme Denetim görüntüleme değişiklikleri kapsayıcısı. **IViewObjectEx** arabirimi titreşimsiz çizim, dikdörtgen olmayan ve saydam denetimleri ve (örneğin, ne kadar yakın bir fare tıklatma üzerinde olarak kabul edilmesi için olmalıdır isabet sınaması gibi genişletilmiş denetim özellikleri için destek sağlar Denetim). Sınıf `IViewObjectExImpl` bu arabirimleri bir varsayılan uygulamayı sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="draw"></a>  IViewObjectExImpl::Draw  
 Bir cihaz bağlamı üzerine denetim gösterimini çizer.  
  
```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır **CComControl::OnDrawAdvanced** denetim sınıfınızın sırayla çağıran `OnDraw` yöntemi. Bir `OnDraw` ATL Denetim Sihirbazı'yla denetiminizi oluşturduğunuzda yöntemi denetim sınıfınıza otomatik olarak eklenir. Sihirbazın varsayılan `OnDraw` "ATL 3.0" etiketli bir dikdörtgen çizer.  
  
 Bkz: [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) Windows SDK.  
  
##  <a name="freeze"></a>  IViewObjectExImpl::Freeze  
 Bir denetim çizilmiş gösterimini kadar değişmeyeceği şekilde donuyor bir `Unfreeze`. ATL uygulamasını döndürür **E_NOTIMPL**.  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728) Windows SDK.  
  
##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise  
 Varsa mevcut bir danışma havuz bağlantı denetimi alır.  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim sınıfı veri üyesi danışma havuz depolanan [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink).  
  
 Bkz: [IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772) Windows SDK.  
  
##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet  
 Çizim için denetim tarafından kullanılan mantıksal palet döndürür. ATL uygulamasını döndürür **E_NOTIMPL**.  
  
```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553) Windows SDK.  
  
##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent  
 Denetimin görüntüleme boyutu HIMETRIC birimler (birim başına 0,01 milimetre) denetim sınıfı veri üyesi alır [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) Windows SDK.  
  
##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent  
 Kullanıcı yeniden boyutlandırır olarak kullanılmak üzere nesnesinin kapsayıcısından boyutlandırma ipuçlarını sağlar.  
  
```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `dwAspect` olan `DVASPECT_CONTENT` ve *pExtentInfo -> dwExtentMode* olan **DVEXTENT_CONTENT**, ayarlar * `psizel` denetim sınıfın veri üyesi için [CComControlBase: : m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural). Aksi takdirde bir hata döndürür `HRESULT`.  
  
 Bkz: [IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718) Windows SDK.  
  
##  <a name="getrect"></a>  IViewObjectExImpl::GetRect  
 İstenen bir çizim yönü açıklayan bir dikdörtgen döndürür. ATL uygulamasını döndürür **E_NOTIMPL**.  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246) Windows SDK.  
  
##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus  
 Nesne ve hangi çizim yönlerini desteklenen opaklık hakkındaki bilgileri döndürür.  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, ATL ayarlar `pdwStatus` denetimi desteklediğini belirtmek için **VIEWSTATUS_OPAQUE** (olası değerler şunlardır: ın [VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201) numaralandırması).  
  
 Bkz: [IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371) Windows SDK.  
  
##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint  
 Belirtilen nokta belirtilen dikdörtgenin nedir ve döndürür denetler bir [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) değeri `pHitResult`.  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Değer, ya da olabilir **HITRESULT_HIT** veya **HITRESULT_OUTSIDE**.  
  
 Varsa `dwAspect` eşittir [DVASPECT_ICON](http://msdn.microsoft.com/library/windows/desktop/ms690318), yöntem `S_OK`. Aksi durumda, yöntem döndürür **E_FAIL**.  
  
 Bkz: [IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209) Windows SDK.  
  
##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect  
 Denetimin görüntüleme dikdörtgenini çakışıyor belirtilen konum dikdörtgenin içindeki herhangi bir noktasını döndürür olup olmadığını denetler ve bir [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) değeri `pHitResult`.  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Değer, ya da olabilir **HITRESULT_HIT** veya **HITRESULT_OUTSIDE**.  
  
 Varsa `dwAspect` eşittir [DVASPECT_ICON](http://msdn.microsoft.com/library/windows/desktop/ms690318), yöntem `S_OK`. Aksi durumda, yöntem döndürür **E_FAIL**.  
  
 Bkz: [IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797) Windows SDK.  
  
##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise  
 Havuz değişiklikleri denetimin görünüm hakkında bildirim almak için denetimi ve bir öneri havuz arasında bir bağlantı kurar.  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>Açıklamalar  

 İşaretçi [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) öneri havuz arabirimde denetim sınıfı veri üyesi depolanan [CComControlBase::m_spAdviseSink](ccomcontrolbase-class.md#m_spadvisesink).  

  
 Bkz: [IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950) Windows SDK.  
  
##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze  
 Denetim çizilmiş gösterimini canlandırır. ATL uygulamasını döndürür **E_NOTIMPL**.  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IViewObject::Unfreeze](http://msdn.microsoft.com/library/windows/desktop/ms686641) Windows SDK.  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 Bu nesneyle ilişkili tanıtıcı kapatmak için bu yöntemi uygulaması.  
  
```
HRESULT CloseHandle(HANDLE hHandle);
```  
  
### <a name="parameters"></a>Parametreler  
 *hHandle*  
 Kapatılması işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı veya başarısızlık HRESULT hata S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yönteme geçirilen tanıtıcı çağrısı ile bu nesne ile daha önce ilişkili [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod basit bir uyarlamasını gösterir `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 Bu nesneyle ilişkili tanıtıcı işaret hale zaman kod yürütmek için bu yöntemi uygulaması.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwParam`  
 Kullanıcı parametresi.  
  
 `hObject`  
 İşaret hale işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı veya başarısızlık HRESULT hata S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tanıtıcı ve DWORD/işaretçi bu yönteme geçirilen bir çağrı tarafından bu nesne ile daha önce ilişkili [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod basit bir uyarlamasını gösterir `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Arabirimleri ActiveX denetimleri](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Öğretici](../../atl/active-template-library-atl-tutorial.md)   
 [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
