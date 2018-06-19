---
title: IOleObjectImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl
- ATLCTL/ATL::IOleObjectImpl::Advise
- ATLCTL/ATL::IOleObjectImpl::Close
- ATLCTL/ATL::IOleObjectImpl::DoVerb
- ATLCTL/ATL::IOleObjectImpl::DoVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::DoVerbHide
- ATLCTL/ATL::IOleObjectImpl::DoVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::DoVerbOpen
- ATLCTL/ATL::IOleObjectImpl::DoVerbPrimary
- ATLCTL/ATL::IOleObjectImpl::DoVerbShow
- ATLCTL/ATL::IOleObjectImpl::DoVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::EnumAdvise
- ATLCTL/ATL::IOleObjectImpl::EnumVerbs
- ATLCTL/ATL::IOleObjectImpl::GetClientSite
- ATLCTL/ATL::IOleObjectImpl::GetClipboardData
- ATLCTL/ATL::IOleObjectImpl::GetExtent
- ATLCTL/ATL::IOleObjectImpl::GetMiscStatus
- ATLCTL/ATL::IOleObjectImpl::GetMoniker
- ATLCTL/ATL::IOleObjectImpl::GetUserClassID
- ATLCTL/ATL::IOleObjectImpl::GetUserType
- ATLCTL/ATL::IOleObjectImpl::InitFromData
- ATLCTL/ATL::IOleObjectImpl::IsUpToDate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPostVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbDiscardUndo
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbHide
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbInPlaceActivate
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbOpen
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbShow
- ATLCTL/ATL::IOleObjectImpl::OnPreVerbUIActivate
- ATLCTL/ATL::IOleObjectImpl::SetClientSite
- ATLCTL/ATL::IOleObjectImpl::SetColorScheme
- ATLCTL/ATL::IOleObjectImpl::SetExtent
- ATLCTL/ATL::IOleObjectImpl::SetHostNames
- ATLCTL/ATL::IOleObjectImpl::SetMoniker
- ATLCTL/ATL::IOleObjectImpl::Unadvise
- ATLCTL/ATL::IOleObjectImpl::Update
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], communication between container and control
- IOleObject, ATL implementation
- IOleObjectImpl class
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a98d3e0ad75d2eaa0325699369bfe4473182049
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366201"
---
# <a name="ioleobjectimpl-class"></a>IOleObjectImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve üzerinden bir kapsayıcı iletişim kurduğu bir denetimle asıl arabirimdir.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class ATL_NO_VTABLE IOleObjectImpl : public IOleObject
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IOleObjectImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](#advise)|Denetimi ile danışma bir bağlantı kurar.|  
|[IOleObjectImpl::Close](#close)|Denetim durumu için yüklenen çalışmasını değiştirir.|  
|[IOleObjectImpl::DoVerb](#doverb)|Numaralandırılmış eylemlerden birini gerçekleştirin denetimi söyler.|  
|[IOleObjectImpl::DoVerbDiscardUndo](#doverbdiscardundo)|Bu koruma herhangi bir geri alma durumu atmak için Denetim söyler.|  
|[IOleObjectImpl::DoVerbHide](#doverbhide)|Kullanıcı arabirimi görünümden kaldırmak için Denetim söyler.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](#doverbinplaceactivate)|Denetimi çalıştırır ve onun penceresi yükler, ancak denetimin kullanıcı arabirimi yüklenmez.|  
|[IOleObjectImpl::DoVerbOpen](#doverbopen)|Ayrı bir pencerede aç düzenlenebilir denetim neden olur.|  
|[IOleObjectImpl::DoVerbPrimary](#doverbprimary)|Kullanıcı denetimi tıklattığında belirtilen eylemi gerçekleştirir. Denetim genellikle yerinde denetimi etkinleştirmek için eylem tanımlar.|  
|[IOleObjectImpl::DoVerbShow](#doverbshow)|Yeni eklenen bir denetim kullanıcıya gösterilir.|  
|[IOleObjectImpl::DoVerbUIActivate](#doverbuiactivate)|Yerinde denetimini etkinleştirir ve menüleri ve araç çubukları gibi denetimin kullanıcı arabirimi gösterir.|  
|[IOleObjectImpl::EnumAdvise](#enumadvise)|Denetimin danışma bağlantıları numaralandırır.|  
|[IOleObjectImpl::EnumVerbs](#enumverbs)|Denetim eylemleri numaralandırır.|  
|[IOleObjectImpl::GetClientSite](#getclientsite)|Denetimin istemci site alır.|  
|[IOleObjectImpl::GetClipboardData](#getclipboarddata)|Panodan verileri alır. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleObjectImpl::GetExtent](#getextent)|Denetimin görüntüleme alanı kapsamını alır.|  
|[IOleObjectImpl::GetMiscStatus](#getmiscstatus)|Denetim durumunu alır.|  
|[IOleObjectImpl::GetMoniker](#getmoniker)|Denetimin bilinen adını alır. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleObjectImpl::GetUserClassID](#getuserclassid)|Denetimin sınıf tanımlayıcısı alır.|  
|[IOleObjectImpl::GetUserType](#getusertype)|Denetimin kullanıcı türü adını alır.|  
|[IOleObjectImpl::InitFromData](#initfromdata)|Seçili veri denetiminden başlatır. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleObjectImpl::IsUpToDate](#isuptodate)|Denetim güncel olup olmadığını denetler. ATL uygulamasını döndürür `S_OK`.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](#onpostverbdiscardundo)|Tarafından çağrılır [DoVerbDiscardUndo](#doverbdiscardundo) sonra geri alma durum atılır.|  
|[IOleObjectImpl::OnPostVerbHide](#onpostverbhide)|Tarafından çağrılır [DoVerbHide](#doverbhide) denetimi gizli sonra.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](#onpostverbinplaceactivate)|Tarafından çağrılır [DoVerbInPlaceActivate](#doverbinplaceactivate) denetimi yerinde etkinleştirildikten sonra.|  
|[IOleObjectImpl::OnPostVerbOpen](#onpostverbopen)|Tarafından çağrılır [DoVerbOpen](#doverbopen) denetimi ayrı bir pencerede düzenlenmek üzere açıldıktan sonra.|  
|[IOleObjectImpl::OnPostVerbShow](#onpostverbshow)|Tarafından çağrılır [DoVerbShow](#doverbshow) denetimi görünür kurulduktan sonra.|  
|[IOleObjectImpl::OnPostVerbUIActivate](#onpostverbuiactivate)|Tarafından çağrılır [DoVerbUIActivate](#doverbuiactivate) denetimin kullanıcı arabirimi etkinleştirildikten sonra.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](#onpreverbdiscardundo)|Tarafından çağrılır [DoVerbDiscardUndo](#doverbdiscardundo) önce geri durum atılır.|  
|[IOleObjectImpl::OnPreVerbHide](#onpreverbhide)|Tarafından çağrılır [DoVerbHide](#doverbhide) denetimi gizli önce.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](#onpreverbinplaceactivate)|Tarafından çağrılır [DoVerbInPlaceActivate](#doverbinplaceactivate) denetimi yerinde etkinleştirilmeden önce.|  
|[IOleObjectImpl::OnPreVerbOpen](#onpreverbopen)|Tarafından çağrılır [DoVerbOpen](#doverbopen) denetimi ayrı bir pencerede düzenlenmek üzere açıldıktan önce.|  
|[IOleObjectImpl::OnPreVerbShow](#onpreverbshow)|Tarafından çağrılır [DoVerbShow](#doverbshow) önce denetimi görünür duruma getirildi.|  
|[IOleObjectImpl::OnPreVerbUIActivate](#onpreverbuiactivate)|Tarafından çağrılır [DoVerbUIActivate](#doverbuiactivate) önce denetimin kullanıcı arabirimi etkinleştirildi.|  
|[IOleObjectImpl::SetClientSite](#setclientsite)|Kendi istemci sitesi kapsayıcısında hakkında denetimi söyler.|  
|[IOleObjectImpl::SetColorScheme](#setcolorscheme)|Bir renk şeması denetimin uygulamaya varsa önerir. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleObjectImpl::SetExtent](#setextent)|Denetimin görüntüleme alanı kapsamını ayarlar.|  
|[IOleObjectImpl::SetHostNames](#sethostnames)|Denetim kapsayıcısı uygulamasına ve kapsayıcı belge adlarını bildirir.|  
|[IOleObjectImpl::SetMoniker](#setmoniker)|Denetim ne takma adı olduğunu söyler. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleObjectImpl::Unadvise](#unadvise)|Denetim danışma bir bağlantıyla siler.|  
|[IOleObjectImpl::Update](#update)|Denetim güncelleştirir. ATL uygulamasını döndürür `S_OK`.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IOLE nesnesini](http://msdn.microsoft.com/library/windows/desktop/dd542709) üzerinden bir kapsayıcı iletişim kuran bir denetimle asıl arabirimi bir arabirimdir. Sınıf `IOleObjectImpl` bu arabirimin varsayılan uygulamasını sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="advise"></a>  IOleObjectImpl::Advise  
 Denetimi ile danışma bir bağlantı kurar.  
  
```
STDMETHOD(Advise)(
    IAdviseSink* pAdvSink,
    DWORD* pdwConnection);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) Windows SDK.  
  
##  <a name="close"></a>  IOleObjectImpl::Close  
 Denetim durumu için yüklenen çalışmasını değiştirir.  
  
```
STDMETHOD(Close)(DWORD dwSaveOption);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim devre dışı bırakır ve varsa denetimi penceresi yok eder. Denetimin veri üyesi sınıftan olursa [CComControlBase::m_bRequiresSave](../../atl/reference/ccomcontrolbase-class.md#m_brequiressave) olan **TRUE** ve `dwSaveOption` parametresi `OLECLOSE_SAVEIFDIRTY` veya `OLECLOSE_PROMPTSAVE`, denetim özellikleri kaydedilir kapatmadan önce.  
  
 İşaretçileri tutulan denetim sınıf veri üyeleri [CComControlBase::m_spInPlaceSite](../../atl/reference/ccomcontrolbase-class.md#m_spinplacesite) ve [CComControlBase::m_spAdviseSink](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink) serbest bırakılır ve veri üyeleri [CComControlBase:: m_bNegotiatedWnd](../../atl/reference/ccomcontrolbase-class.md#m_bnegotiatedwnd), [CComControlBase::m_bWndless](../../atl/reference/ccomcontrolbase-class.md#m_bwndless), ve [CComControlBase::m_bInPlaceSiteEx](../../atl/reference/ccomcontrolbase-class.md#m_binplacesiteex) ayarlanır **FALSE**.  
  
 Bkz: [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922) Windows SDK.  
  
##  <a name="doverb"></a>  IOleObjectImpl::DoVerb  
 Numaralandırılmış eylemlerden birini gerçekleştirin denetimi söyler.  
  
```
STDMETHOD(DoVerb)(
    LONG iVerb,
    LPMSG /* pMsg */,
    IOleClientSite* pActiveSite,
    LONG /* lindex */,
    HWND hwndParent,
    LPCRECT lprcPosRect);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Değerine bağlı olarak `iVerb`, ATL birini `DoVerb` yardımcı işlevleri gibi çağrılır:  
  
|*iVerb* değeri|Adlı DoVerb yardımcı işlevi|  
|-------------------|-----------------------------------|  
|**OLEIVERB_DISCARDUNDOSTATE**|[DoVerbDiscardUndo](#doverbdiscardundo)|  
|`OLEIVERB_HIDE`|[DoVerbHide](#doverbhide)|  
|**OLEIVERB_INPLACEACTIVATE**|[DoVerbInPlaceActivate](#doverbinplaceactivate)|  
|`OLEIVERB_OPEN`|[DoVerbOpen](#doverbopen)|  
|`OLEIVERB_PRIMARY`|[DoVerbPrimary](#doverbprimary)|  
|**OLEIVERB_PROPERTIES**|[CComControlBase::DoVerbProperties](../../atl/reference/ccomcontrolbase-class.md#doverbproperties)|  
|`OLEIVERB_SHOW`|[DoVerbShow](#doverbshow)|  
|`OLEIVERB_UIACTIVATE`|[DoVerbUIActivate](#doverbuiactivate)|  
  
 Bkz: [Rpc_e_serverfault](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows SDK.  
  
##  <a name="doverbdiscardundo"></a>  IOleObjectImpl::DoVerbDiscardUndo  
 Bu koruma herhangi bir geri alma durumu atmak için Denetim söyler.  
  
```
HRESULT DoVerbDiscardUndo(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parametreler  
 `prcPosRec`  
 [in] Kapsayıcı dikdörtgen işaretçisine içine çizmek için denetimi istiyor.  
  
 *hwndParent*  
 [in] Denetimi içeren pencere işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
##  <a name="doverbhide"></a>  IOleObjectImpl::DoVerbHide  
 Devre dışı bırakır ve denetimin kullanıcı arabirimi kaldırır ve denetimini gizler.  
  
```
HRESULT DoVerbHide(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parametreler  
 `prcPosRec`  
 [in] Kapsayıcı dikdörtgen işaretçisine içine çizmek için denetimi istiyor.  
  
 *hwndParent*  
 [in] Denetimi içeren pencere işleci. ATL uygulamasında kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
##  <a name="doverbinplaceactivate"></a>  IOleObjectImpl::DoVerbInPlaceActivate  
 Denetimi çalıştırır ve onun penceresi yükler, ancak denetimin kullanıcı arabirimi yüklenmez.  
  
```
HRESULT DoVerbInPlaceActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parametreler  
 `prcPosRec`  
 [in] Kapsayıcı dikdörtgen işaretçisine içine çizmek için denetimi istiyor.  
  
 *hwndParent*  
 [in] Denetimi içeren pencere işleci. ATL uygulamasında kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerinde denetim çağırarak etkinleştirir [CComControlBase::InPlaceActivate](../../atl/reference/ccomcontrolbase-class.md#inplaceactivate). Sürece denetim sınıfın veri üyesi `m_bWindowOnly` olan **TRUE**, `DoVerbInPlaceActivate` önce çalışır denetimi penceresiz bir denetim olarak etkinleştirmek (yalnızca kapsayıcı destekliyorsa olası [IOleInPlaceSiteWindowless ](http://msdn.microsoft.com/library/windows/desktop/ms682300)). Başarısız olursa, işlevi genişletilmiş özellikler denetimiyle etkinleştirmeyi dener (yalnızca kapsayıcı destekliyorsa olası [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461)). Başarısız olursa, işlevi hiçbir genişletilmiş özellik denetimiyle etkinleştirmeyi dener (yalnızca kapsayıcı destekliyorsa olası [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586)). Etkinleştirme başarılı olursa, işlevi kapsayıcı denetimi etkinleştirilmiş bildirir.  
  
##  <a name="doverbopen"></a>  IOleObjectImpl::DoVerbOpen  
 Ayrı bir pencerede aç düzenlenebilir denetim neden olur.  
  
```
HRESULT DoVerbOpen(LPCRECT /* prcPosRect */, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parametreler  
 `prcPosRec`  
 [in] Kapsayıcı dikdörtgen işaretçisine içine çizmek için denetimi istiyor.  
  
 *hwndParent*  
 [in] Denetimi içeren pencere işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
##  <a name="doverbprimary"></a>  IOleObjectImpl::DoVerbPrimary  
 Kullanıcı denetimi tıklattığında gerçekleştirilecek eylemi tanımlar.  
  
```
HRESULT DoVerbPrimary(LPCRECT prcPosRect, HWND hwndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 `prcPosRec`  
 [in] Kapsayıcı dikdörtgen işaretçisine içine çizmek için denetimi istiyor.  
  
 *hwndParent*  
 [in] Denetimi içeren pencere işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfaları görüntülemek için varsayılan olarak ayarlayın. Bu, farklı bir davranış çift tıklatıldığında çağrılacak denetim sınıfınızda kılabilirsiniz; Örneğin, bir çalmasına veya yerinde etkin gidin.  
  
##  <a name="doverbshow"></a>  IOleObjectImpl::DoVerbShow  
 Denetimi görünür hale getirmek için kapsayıcı söyler.  
  
```
HRESULT DoVerbShow(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parametreler  
 `prcPosRec`  
 [in] Kapsayıcı dikdörtgen işaretçisine içine çizmek için denetimi istiyor.  
  
 *hwndParent*  
 [in] Denetimi içeren pencere işleci. ATL uygulamasında kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
##  <a name="doverbuiactivate"></a>  IOleObjectImpl::DoVerbUIActivate  
 Denetimin kullanıcı arabirimini etkinleştirir ve kapsayıcı menülerini bileşik menüleri değiştirilmektedir bildirir.  
  
```
HRESULT DoVerbUIActivate(LPCRECT prcPosRect, HWND /* hwndParent */);
```  
  
### <a name="parameters"></a>Parametreler  
 `prcPosRec`  
 [in] Kapsayıcı dikdörtgen işaretçisine içine çizmek için denetimi istiyor.  
  
 *hwndParent*  
 [in] Denetimi içeren pencere işleci. ATL uygulamasında kullanılmaz.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
##  <a name="enumadvise"></a>  IOleObjectImpl::EnumAdvise  
 Bu denetim için kayıtlı danışma bağlantıları numaralandırması sağlar.  
  
```
STDMETHOD(EnumAdvise)(IEnumSTATDATA** ppenumAdvise);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::EnumAdvise](http://msdn.microsoft.com/library/windows/desktop/ms682355) Windows SDK.  
  
##  <a name="enumverbs"></a>  IOleObjectImpl::EnumVerbs  
 Kayıtlı eylemleri (fiiller) numaralandırması çağırarak bu denetim için sağladığı **OleRegEnumVerbs**.  
  
```
STDMETHOD(EnumVerbs)(IEnumOLEVERB** ppEnumOleVerb);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Fiiller projenizin .rgs dosyasına ekleyebilirsiniz. Örneğin, CIRCCTL bakın. İçinde RGS [DAİ](../../visual-cpp-samples.md) örnek.  
  
 Bkz: [IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781) Windows SDK.  
  
##  <a name="getclientsite"></a>  IOleObjectImpl::GetClientSite  
 Denetim sınıfı veri üyesi işaretçinin koyar [CComControlBase::m_spClientSite](../../atl/reference/ccomcontrolbase-class.md#m_spclientsite) içine *ppClientSite* ve işaretçi başvuru sayısına artırır.  
  
```
STDMETHOD(GetClientSite)(IOleClientSite** ppClientSite);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::GetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms692603) Windows SDK.  
  
##  <a name="getclipboarddata"></a>  IOleObjectImpl::GetClipboardData  
 Panodan verileri alır.  
  
```
STDMETHOD(GetClipboardData)(    
    DWORD /* dwReserved */,
    IDataObject** /* ppDataObject */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::GetClipboardData](http://msdn.microsoft.com/library/windows/desktop/ms682288) Windows SDK.  
  
##  <a name="getextent"></a>  IOleObjectImpl::GetExtent  
 Çalışan bir denetimin görüntüleme boyutu HIMETRIC birimler (birim başına 0,01 milimetre) alır.  
  
```
STDMETHOD(GetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim sınıfı veri üyesi boyutu depolanan [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent).  
  
 Bkz: [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325) Windows SDK.  
  
##  <a name="getmiscstatus"></a>  IOleObjectImpl::GetMiscStatus  
 Çağırarak denetimi için kayıtlı durum bilgisi için bir işaretçi döndürür **OleRegGetMiscStatus**.  
  
```
STDMETHOD(GetMiscStatus)(
    DWORD dwAspect,
    DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Durum bilgileri denetim ve sunu verileri tarafından desteklenen davranışları içerir. Durum bilgisi projenizin .rgs dosyasına ekleyebilirsiniz.  
  
 Bkz: [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) Windows SDK.  
  
##  <a name="getmoniker"></a>  IOleObjectImpl::GetMoniker  
 Denetimin bilinen adını alır.  
  
```
STDMETHOD(GetMoniker)(
    DWORD /* dwAssign */,
    DWORD /* dwWhichMoniker */,
    IMoniker** /* ppmk */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::GetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms686576) Windows SDK.  
  
##  <a name="getuserclassid"></a>  IOleObjectImpl::GetUserClassID  
 Denetimin sınıf tanımlayıcısı döndürür.  
  
```
STDMETHOD(GetUserClassID)(CLSID* pClsid);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::GetUserClassID](http://msdn.microsoft.com/library/windows/desktop/ms682313) Windows SDK.  
  
##  <a name="getusertype"></a>  IOleObjectImpl::GetUserType  
 Denetimin kullanıcı türü adı çağırarak döndürür **OleRegGetUserType**.  
  
```
STDMETHOD(GetUserType)(
    DWORD dwFormOfType,
    LPOLESTR* pszUserType);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Menüler ve iletişim kutuları gibi kullanıcı arabirimi öğeleri görüntülemek için kullanılan kullanıcı türü adı. Projenizin .rgs dosyasındaki kullanıcı türü adını değiştirebilirsiniz.  
  
 Bkz: [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643) Windows SDK.  
  
##  <a name="initfromdata"></a>  IOleObjectImpl::InitFromData  
 Seçili veri denetiminden başlatır.  
  
```
STDMETHOD(InitFromData)(
    IDataObject* /* pDataObject */,
    BOOL /* fCreation */,
    DWORD /* dwReserved */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510) Windows SDK.  
  
##  <a name="isuptodate"></a>  IOleObjectImpl::IsUpToDate  
 Denetim güncel olup olmadığını denetler.  
  
```
STDMETHOD(IsUpToDate)(void);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::IsUpToDate](http://msdn.microsoft.com/library/windows/desktop/ms686624) Windows SDK.  
  
##  <a name="onpostverbdiscardundo"></a>  IOleObjectImpl::OnPostVerbDiscardUndo  
 Tarafından çağrılır [DoVerbDiscardUndo](#doverbdiscardundo) sonra geri alma durum atılır.  
  
```
HRESULT OnPostVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Geri alma durum atılır sonra yürütülen istediğiniz koduyla bu yöntemi geçersiz kılın.  
  
##  <a name="onpostverbhide"></a>  IOleObjectImpl::OnPostVerbHide  
 Tarafından çağrılır [DoVerbHide](#doverbhide) denetimi gizli sonra.  
  
```
HRESULT OnPostVerbHide();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanmak istediğiniz kod denetimi gizli sonra yürütülen ile bu yöntemi geçersiz kılın.  
  
##  <a name="onpostverbinplaceactivate"></a>  IOleObjectImpl::OnPostVerbInPlaceActivate  
 Tarafından çağrılır [DoVerbInPlaceActivate](#doverbinplaceactivate) denetimi yerinde etkinleştirildikten sonra.  
  
```
HRESULT OnPostVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanmak istediğiniz kod denetimi yerinde etkinleştirildikten sonra yürütülen ile bu yöntemi geçersiz kılın.  
  
##  <a name="onpostverbopen"></a>  IOleObjectImpl::OnPostVerbOpen  
 Tarafından çağrılır [DoVerbOpen](#doverbopen) denetimi ayrı bir pencerede düzenlenmek üzere açıldıktan sonra.  
  
```
HRESULT OnPostVerbOpen();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim ayrı bir pencerede düzenlenmek üzere açıldıktan sonra yürütülen istediğiniz kod ile bu yöntemi geçersiz kılın.  
  
##  <a name="onpostverbshow"></a>  IOleObjectImpl::OnPostVerbShow  
 Tarafından çağrılır [DoVerbShow](#doverbshow) denetimi görünür kurulduktan sonra.  
  
```
HRESULT OnPostVerbShow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim görünür kurulduktan sonra yürütülen istediğiniz kod ile bu yöntemi geçersiz kılın.  
  
##  <a name="onpostverbuiactivate"></a>  IOleObjectImpl::OnPostVerbUIActivate  
 Tarafından çağrılır [DoVerbUIActivate](#doverbuiactivate) denetimin kullanıcı arabirimi etkinleştirildikten sonra.  
  
```
HRESULT OnPostVerbUIActivate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimin kullanıcı arabirimi etkinleştirildikten sonra yürütülen istediğiniz kod ile bu yöntemi geçersiz kılın.  
  
##  <a name="onpreverbdiscardundo"></a>  IOleObjectImpl::OnPreVerbDiscardUndo  
 Tarafından çağrılır [DoVerbDiscardUndo](#doverbdiscardundo) önce geri durum atılır.  
  
```
HRESULT OnPreVerbDiscardUndo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Atılan gelen geri alma durumu önlemek için HRESULT hata döndürmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onpreverbhide"></a>  IOleObjectImpl::OnPreVerbHide  
 Tarafından çağrılır [DoVerbHide](#doverbhide) denetimi gizli önce.  
  
```
HRESULT OnPreVerbHide();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Gizli gelen denetimi önlemek için HRESULT hata döndürmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onpreverbinplaceactivate"></a>  IOleObjectImpl::OnPreVerbInPlaceActivate  
 Tarafından çağrılır [DoVerbInPlaceActivate](#doverbinplaceactivate) denetimi yerinde etkinleştirilmeden önce.  
  
```
HRESULT OnPreVerbInPlaceActivate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yerinde etkinleştirilmiş denetim önlemek için HRESULT hata döndürmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onpreverbopen"></a>  IOleObjectImpl::OnPreVerbOpen  
 Tarafından çağrılır [DoVerbOpen](#doverbopen) denetimi ayrı bir pencerede düzenlenmek üzere açıldıktan önce.  
  
```
HRESULT OnPreVerbOpen();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrı bir pencerede düzenleme için açılmasını denetimi önlemek için HRESULT hata döndürmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onpreverbshow"></a>  IOleObjectImpl::OnPreVerbShow  
 Tarafından çağrılır [DoVerbShow](#doverbshow) önce denetimi görünür duruma getirildi.  
  
```
HRESULT OnPreVerbShow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimi görünür hale önlemek için HRESULT hata döndürmek için bu yöntemi geçersiz kılın.  
  
##  <a name="onpreverbuiactivate"></a>  IOleObjectImpl::OnPreVerbUIActivate  
 Tarafından çağrılır [DoVerbUIActivate](#doverbuiactivate) önce denetimin kullanıcı arabirimi etkinleştirildi.  
  
```
HRESULT OnPreVerbUIActivate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirilmekte olan denetimin kullanıcı arabirimi önlemek için HRESULT hata döndürmek için bu yöntemi geçersiz kılın.  
  
##  <a name="setclientsite"></a>  IOleObjectImpl::SetClientSite  
 Kendi istemci sitesi kapsayıcısında hakkında denetimi söyler.  
  
```
STDMETHOD(SetClientSite)(IOleClientSite* pClientSite);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ardından yöntem `S_OK`.  
  
 Bkz: [IOleObject::SetClientSite](http://msdn.microsoft.com/library/windows/desktop/ms684013) Windows SDK.  
  
##  <a name="setcolorscheme"></a>  IOleObjectImpl::SetColorScheme  
 Bir renk şeması denetimin uygulamaya varsa önerir.  
  
```
STDMETHOD(SetColorScheme)(LOGPALETTE* /* pLogPal */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971) Windows SDK.  
  
##  <a name="setextent"></a>  IOleObjectImpl::SetExtent  
 Denetimin görüntüleme alanı kapsamını ayarlar.  
  
```
STDMETHOD(SetExtent)(
    DWORD dwDrawAspect,
    SIZEL* psizel);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aksi takdirde, `SetExtent` gösterdiği değerini depolar `psizel` denetim sınıfı veri üyesi olarak [CComControlBase::m_sizeExtent](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent). Bu değer HIMETRIC birimler (birim başına 0,01 milimetre) olur.  
  
 Denetim sınıfı veri üyesi değilse [CComControlBase::m_bResizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_bresizenatural) olan **TRUE**, `SetExtent` de gösterdiği değerini depolar `psizel` denetim sınıfı veri üyesi içinde[CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural).  
  
 Denetimin veri üyesi sınıftan olursa [CComControlBase::m_bRecomposeOnResize](../../atl/reference/ccomcontrolbase-class.md#m_brecomposeonresize) olan **TRUE**, `SetExtent` çağrıları `SendOnDataChange` ve `SendOnViewChange` kayıtlı tüm danışma havuzlarını bildirmek için Denetim boyutunun değiştiğini sahibi öneriyoruz.  
  
 Bkz: [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330) Windows SDK.  
  
##  <a name="sethostnames"></a>  IOleObjectImpl::SetHostNames  
 Denetim kapsayıcısı uygulamasına ve kapsayıcı belge adlarını bildirir.  
  
```
STDMETHOD(SetHostNames)(LPCOLESTR /* szContainerApp */, LPCOLESTR /* szContainerObj */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642) Windows SDK.  
  
##  <a name="setmoniker"></a>  IOleObjectImpl::SetMoniker  
 Denetim ne takma adı olduğunu söyler.  
  
```
STDMETHOD(SetMoniker)(
    DWORD /* dwWhichMoniker */,
    IMoniker** /* pmk */);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::SetMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679671) Windows SDK.  
  
##  <a name="unadvise"></a>  IOleObjectImpl::Unadvise  
 Denetim sınıfının depolanan danışma bağlantısını siler `m_spOleAdviseHolder` veri üyesi.  
  
```
STDMETHOD(Unadvise)(DWORD dwConnection);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) Windows SDK.  
  
##  <a name="update"></a>  IOleObjectImpl::Update  
 Denetim güncelleştirir.  
  
```
STDMETHOD(Update)(void);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleObject::Update](http://msdn.microsoft.com/library/windows/desktop/ms679699) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Arabirimleri ActiveX denetimleri](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
