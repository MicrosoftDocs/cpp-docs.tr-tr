---
title: "CComControlBase sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
dev_langs: C++
helpviewer_keywords: CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8e7e3ab049a7fc7935b9027746fc4cdebb3428cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomcontrolbase-class"></a>CComControlBase sınıfı
Bu sınıf oluşturmak ve ATL denetimleri yönetmek için yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class ATL_NO_VTABLE CComControlBase
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComControlBase::AppearanceType](#appearancetype)|Geçersiz kılın, `m_nAppearance` stok özellik türü değil `short`.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComControlBase::CComControlBase](#ccomcontrolbase)|Oluşturucu.|  
|[CComControlBase:: ~ CComControlBase](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|İstenen arabirim için bir işaretçi alır.|  
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Denetleyen `iVerb` tarafından kullanılan parametre `IOleObjectImpl::DoVerb` ya da denetimin kullanıcı arabirimini etkinleştirir ( `iVerb` eşittir `OLEIVERB_UIACTIVATE`), kullanıcı denetimi tıklattığında gerçekleştirilecek eylemi tanımlar ( `iVerb` eşittir`OLEIVERB_PRIMARY`), Denetim görüntüler ( `iVerb` eşittir `OLEIVERB_SHOW`), ya da Denetim etkinleştirir ( `iVerb` eşittir **OLEIVERB_INPLACEACTIVATE**).|  
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Denetleyen `iVerb` tarafından kullanılan parametre `IOleObjectImpl::DoVerb` etkinleştirmek kullanıcı arabirimi denetim neden olur ve döndürür **doğru**.|  
|[CComControlBase::DoVerbProperties](#doverbproperties)|Denetimin özellik sayfaları görüntüler.|  
|[CComControlBase::FireViewChange](#fireviewchange)|Denetim yeniden boyutlandırmaya kapsayıcıya bildirmek için bu yöntemi çağırın veya denetimin görünüm değişti kayıtlı öneri havuzlarını bildirin.|  
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|Alır **DISPID_AMBIENT_APPEARANCE**, denetimi için ayarlama geçerli görünümü: düz ve 3B için 1'için 0.|  
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Alır **DISPID_AMBIENT_AUTOCLIP**, kapsayıcı denetimi görüntü alanının otomatik kırpma destekleyip desteklemediğini belirten bir bayrak.|  
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Alır **DISPID_AMBIENT_BACKCOLOR**, kapsayıcı tarafından tanımlanmış tüm denetimlerin ortam arka plan rengi.|  
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Alır **DISPID_AMBIENT_CHARSET**, ortam karakter kümesi kapsayıcı tarafından tanımlanan tüm denetimler için.|  
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Alır **DISPID_AMBIENT_CODEPAGE**, ortam karakter kümesi kapsayıcı tarafından tanımlanan tüm denetimler için.|  
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Alır **DISPID_AMBIENT_DISPLAYASDEFAULT**, olan bir bayrak **TRUE** kapsayıcı denetimi varsayılan düğme olarak bu site içinde işaretlenmiş ve bir düğme denetimi kendisiyle bu nedenle çizip bir Kalın çerçeve.|  
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|Alır **DISPID_AMBIENT_DISPLAYNAME**, kapsayıcı denetimi tarafından sağlanan adı.|  
|[CComControlBase::GetAmbientFont](#getambientfont)|Alır kapsayıcı için bir işaretçi ortam `IFont` arabirimi.|  
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Alır kapsayıcı için bir işaretçi ortam **IFontDisp** gönderme arabirimi.|  
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Alır **DISPID_AMBIENT_FORECOLOR**, kapsayıcı tarafından tanımlanan tüm denetimlerin ortam ön plan rengi.|  
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Alır **DISPID_AMBIENT_LOCALEID**, kapsayıcı tarafından kullanılan dil tanıtıcısı.|  
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|Alır **DISPID_AMBIENT_MESSAGEREFLECT**, kapsayıcı pencere iletileri almak istediği olup olmadığını belirten bir bayrak (gibi `WM_DRAWITEM`) olayları olarak.|  
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Alır **DISPID_AMBIENT_PALETTE**, kapsayıcının erişmek için kullanılan `HPALETTE`.|  
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Belirtilen kapsayıcı özelliği alır `id`.|  
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|Alır **DISPID_AMBIENT_RIGHTTOLEFT**, içerik kapsayıcı görüntülenir yönü.|  
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Alır **DISPID_AMBIENT_SCALEUNITS**, görüntüler etiketleme kapsayıcının ortam birim (inç veya gibi santimetreden).|  
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|Alır **DISPID_AMBIENT_SHOWGRABHANDLES**, kapsayıcı Al tanıtıcıları kendisi için etkin olduğunda görüntülemek üzere denetimi izin verip vermediğini belirten bir bayrak.|  
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|Alır **DISPID_AMBIENT_SHOWHATCHING**, kapsayıcı UI etkin olduğunda kendisini taranmış bir desenle görüntülemek üzere denetimi izin verip vermediğini belirten bir bayrak.|  
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Alır **DISPID_AMBIENT_SUPPORTSMNEMONICS**, kapsayıcı klavye anımsatıcıları destekleyip desteklemediğini belirten bir bayrak.|  
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|Alır **DISPID_AMBIENT_TEXTALIGN**, kapsayıcı tarafından tercih edilen metin hizalamasını: Genel hizalama (numaraları sağdaki metni sola) için 0, 1 sol hizalaması için Ortala için 2 ve 3 sağa hizalama için.|  
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|Alır **DISPID_AMBIENT_TOPTOBOTTOM**, içerik kapsayıcı görüntülenir yönü.|  
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Alır **DISPID_AMBIENT_UIDEAD**, kapsayıcı denetimi için kullanıcı arabirimi eylemlerini yanıtlamasını isteyip istemediğini gösteren bir bayrak.|  
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|Alır **DISPID_AMBIENT_USERMODE**, kapsayıcı çalışma modunda olup olmadığını belirten bir bayrak ( **TRUE**) veya Tasarım modunda ( **FALSE**).|  
|[CComControlBase::GetDirty](#getdirty)|Veri üyesi değerini döndürür `m_bRequiresSave`.|  
|[CComControlBase::GetZoomInfo](#getzoominfo)|X ve y alır pay ve yakınlaştırma faktörünü payda değerleri bir denetimi için etkinleştirilmiş için yerinde düzenleme.|  
|[CComControlBase::InPlaceActivate](#inplaceactivate)|Ne olursa olsun fiil durum devre dışı durumuna geçiş denetimi neden `iVerb` gösterir.|  
|[CComControlBase::InternalGetSite](#internalgetsite)|Denetim site için tanımlanan arayüzü için bir işaretçi sorgulamak için bu yöntemi çağırın.|  
|[CComControlBase::OnDraw](#ondraw)|Denetim çizmek için bu yöntemi geçersiz kılın.|  
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|Varsayılan **OnDrawAdvanced** normalleştirilmiş cihaz bağlamı çizim için hazırlar ve ardından Denetim sınıfınızın çağırır `OnDraw` yöntemi.|  
|[CComControlBase::OnKillFocus](#onkillfocus)|Denetim yerinde etkin ve geçerli denetim sitesinde ardından kapsayıcı denetimi odağını kaybetmiş bildirir denetler.|  
|[CComControlBase::OnMouseActivate](#onmouseactivate)|Kullanıcı Arabirimi kullanıcı modunda sonra denetimi etkinleştirir denetler.|  
|[CComControlBase::OnPaint](#onpaint)|Boyama için kapsayıcı hazırlar, denetimin istemci alanını alır ve ardından Denetim sınıfının çağırır `OnDraw` yöntemi.|  
|[CComControlBase::OnSetFocus](#onsetfocus)|Denetim yerinde etkin ve geçerli denetim sitesinde ardından kapsayıcı denetimi bildirir denetimleri odak kazanılan.|  
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Kendi klavye kısayol işleyicileri sağlamak için bu yöntemi geçersiz kılın.|  
|[CComControlBase::SendOnClose](#sendonclose)|Denetim kapatıldı öneri sahibi ile kayıtlı tüm danışma havuzlarını bildirir.|  
|[CComControlBase::SendOnDataChange](#sendondatachange)|Denetim verileri değişti öneri sahibi ile kayıtlı tüm danışma havuzlarını bildirir.|  
|[CComControlBase::SendOnRename](#sendonrename)|Denetimi yeni bir bilinen ad sahip öneri sahibi ile kayıtlı tüm danışma havuzlarını bildirir.|  
|[CComControlBase::SendOnSave](#sendonsave)|Denetim kaydedilmiş öneri sahibi ile kayıtlı tüm danışma havuzlarını bildirir.|  
|[CComControlBase::SendOnViewChange](#sendonviewchange)|Denetimin görünüm değişti danışma havuzlarını tüm kayıtlı bildirir.|  
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Klavye odağı ya da denetiminden kaldırır veya ayarlar.|  
|[CComControlBase::SetDirty](#setdirty)|Veri üyesi ayarlar `m_bRequiresSave` değerine `bDirty`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComControlBase::m_bAutoSize](#m_bautosize)|Denetim herhangi bir boyutta olamaz belirten bayrak.|  
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Gösteren bayrağı `IDataObjectImpl::GetData` ve `CComControlBase::GetZoomInfo` denetim boyutundan ayarlamalısınız `m_sizeNatural` yerine `m_sizeExtent`.|  
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Gösteren bayrağı `IDataObjectImpl::GetData` HIMETRIC birimleri ve değil piksel çizerken kullanmanız gerekir.|  
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Denetim yerinde etkin olduğunu gösteren bayrak.|  
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Bayrak kapsayıcı destekler belirten **IOleInPlaceSiteEx** arabirimi ve OCX96 kontrol penceresiz ve titreşimsiz denetimleri gibi özellikleri.|  
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|OCX96 denetim özellikleri (örneğin, titreşimsiz ve penceresiz denetimleri) desteği hakkında kapsayıcısı ile denetimi desteklemediğini anlaşılan ve denetimi pencereli veya penceresiz olup olmadığını belirten bayrak.|  
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Kapsayıcı denetimin görüntüleme boyutu değiştiğinde kendi sunu yeniden oluşturmak denetimi istediği belirten bayrak.|  
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Son kaydedilişinden denetimi değiştiğini gösteren bayrak.|  
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Denetim istediği kendi doğal ölçüde (ölçeklendirilmemiş fiziksel boyutuna) yeniden boyutlandırmak belirten bayrak denetimin görüntüleme boyutu değiştiğinde kapsayıcı.|  
|[CComControlBase::m_bUIActive](#m_buiactive)|Menüleri ve araç çubukları gibi denetimin kullanıcı arabirimi belirten bayrak etkindir.|  
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Kapsayıcı tarafından sağlanan penceresi bölge denetimi kullanarak belirten bayrak.|  
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Denetim penceresiz, ancak olabilir veya artık penceresiz olmayabilir belirten bayrak.|  
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|Penceresiz denetimlerini kapsayıcı destekleyen olsa bile denetimi pencereli, belirten bayrak.|  
|[CComControlBase::m_bWndLess](#m_bwndless)|Denetim penceresiz belirten bayrak.|  
|[CComControlBase::m_hWndCD](#m_hwndcd)|Denetimle ilişkili bir pencere tanıtıcının başvuru içeriyor.|  
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Kaç kez sayısını kapsayıcı olayları (olayları kabulü) bir araya giren çözme (olayları kabul etmeyi reddetti) olayları dondurulmuş.|  
|[CComControlBase::m_rcPos](#m_rcpos)|Kapsayıcı koordinatlarında ifade denetimin konumunu piksel cinsinden.|  
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Belirli bir ekran HIMETRIC birimlerini (her 0,01 milimetre birimdir) denetiminde uzantı.|  
|[CComControlBase::m_sizeNatural](#m_sizenatural)|(Her 0,01 milimetre birimdir) HIMETRIC birimleri denetiminde fiziksel boyutu.|  
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Kapsayıcı danışma bağlantısı için doğrudan bir işaretçi (kapsayıcının [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).|  
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|A `CComDispatchDriver` almak ve aracılığıyla kapsayıcının özelliklerini ayarlamanıza olanak sağlayan nesne bir `IDispatch` işaretçi.|  
|[CComControlBase::m_spClientSite](#m_spclientsite)|Kapsayıcı içinde denetimin istemci site için bir işaretçi.|  
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Veri nesneleri arasındaki danışma bağlantıları basılı tutun ve havuzlarını bildirmek için bir standart araçları sağlar.|  
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Kapsayıcının gösteren bir işaretçi [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), veya [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) arabirim işaretçisi.|  
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Standart uygulaması danışma bağlantıları tutmak için bir yol sağlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf oluşturmak ve ATL denetimleri yönetmek için yöntemler sağlar. [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md) türetilen `CComControlBase`. ATL Denetim Sihirbazı'nı kullanarak bir standart denetim veya DHTML denetimi oluşturduğunuzda, sihirbaz otomatik olarak, sınıfından türetilen `CComControlBase`.  
  
 Bir denetim oluşturma hakkında daha fazla bilgi için bkz: [ATL öğretici](../../atl/active-template-library-atl-tutorial.md). ATL Proje Sihirbazı hakkında daha fazla bilgi için bkz: [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="appearancetype"></a>CComControlBase::AppearanceType  
 Geçersiz kılın, **m_nAppearance** stok özellik türü değil **kısa**.  
  
```
typedef short AppearanceType;
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL Denetim Sihirbazı'nı ekler **m_nAppearance** stok özellik türü kısa. Geçersiz kılma `AppearanceType` farklı bir veri türüne kullanıyorsanız.  
  
##  <a name="ccomcontrolbase"></a>CComControlBase::CComControlBase  
 Oluşturucu.  
  
```
CComControlBase(HWND& h);
```  
  
### <a name="parameters"></a>Parametreler  
 `h`  
 Denetimle ilişkili penceresine işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 5080 X 5080 HIMETRIC birimleri denetim boyutuna başlatır (2 "X 2") ve başlatır `CComControlBase` veri üyesi değerleri için **NULL** veya **FALSE**.  
  
##  <a name="dtor"></a>CComControlBase:: ~ CComControlBase  
 Yok Edicisi.  
  
```
~CComControlBase();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim pencereli, ise `~CComControlBase` çağırarak bozar [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682).  
  
##  <a name="controlqueryinterface"></a>CComControlBase::ControlQueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 İstenen arabirimi GUID.  
  
 `ppv`  
 Arabirim işaretçisi ile tanımlanan bir işaretçi `iid`, veya **NULL** arabirimi bulunmazsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca COM eşleme tablosu arabirimlerde işler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]  
  
##  <a name="doesverbactivate"></a>CComControlBase::DoesVerbActivate  
 Denetleyen `iVerb` tarafından kullanılan parametre `IOleObjectImpl::DoVerb` ya da denetimin kullanıcı arabirimini etkinleştirir ( `iVerb` eşittir `OLEIVERB_UIACTIVATE`), kullanıcı denetimi tıklattığında gerçekleştirilecek eylemi tanımlar ( `iVerb` eşittir`OLEIVERB_PRIMARY`), Denetim görüntüler ( `iVerb` eşittir `OLEIVERB_SHOW`), ya da Denetim etkinleştirir ( `iVerb` eşittir **OLEIVERB_INPLACEACTIVATE**).  
  
```
BOOL DoesVerbActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Parametreler  
 `iVerb`  
 Tarafından gerçekleştirilecek eylemi belirten değer `DoVerb`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** varsa `iVerb` eşittir `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, veya **OLEIVERB_INPLACEACTIVATE**; Aksi halde döndürür **yanlış**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kendi etkinleştirme fiili tanımlamak için bu yöntemin üzerine yazabilir.  
  
##  <a name="doesverbuiactivate"></a>CComControlBase::DoesVerbUIActivate  
 Denetleyen `iVerb` tarafından kullanılan parametre `IOleObjectImpl::DoVerb` etkinleştirmek kullanıcı arabirimi denetim neden olur ve döndürür **doğru**.  
  
```
BOOL DoesVerbUIActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>Parametreler  
 `iVerb`  
 Tarafından gerçekleştirilecek eylemi belirten değer `DoVerb`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** varsa `iVerb` eşittir `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, veya **OLEIVERB_INPLACEACTIVATE**. Aksi durumda, yöntem döndürür **FALSE**.  
  
##  <a name="doverbproperties"></a>CComControlBase::DoVerbProperties  
 Denetimin özellik sayfaları görüntüler.  
  
```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```  
  
### <a name="parameters"></a>Parametreler  
 `prcPosRec`  
 Ayrılmış.  
  
 *hwndParent*  
 Denetimi içeren pencere işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]  
  
 [!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]  
  
##  <a name="fireviewchange"></a>CComControlBase::FireViewChange  
 Denetim yeniden boyutlandırmaya kapsayıcıya bildirmek için bu yöntemi çağırın veya denetimin görünüm değişti kayıtlı öneri havuzlarını bildirin.  
  
```
HRESULT FireViewChange();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimi etkinse (denetim sınıfı veri üyesi [CComControlBase::m_bInPlaceActive](#m_binplaceactive) olan **TRUE**), tüm denetim yeniden boyutlandırmaya istediğiniz kapsayıcı bildirir. Denetim etkin değilse, Denetim kayıtlı bildirir havuzlarını bildirmek (denetim sınıfı veri üyesi aracılığıyla [CComControlBase::m_spAdviseSink](#m_spadvisesink)), denetimin görünümünü değişti.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]  
  
##  <a name="getambientappearance"></a>CComControlBase::GetAmbientAppearance  
 Alır **DISPID_AMBIENT_APPEARANCE**, denetimi için ayarlama geçerli görünümü: düz ve 3B için 1'için 0.  
  
```
HRESULT GetAmbientAppearance(short& nAppearance);
```  
  
### <a name="parameters"></a>Parametreler  
 `nAppearance`  
 Özellik **DISPID_AMBIENT_APPEARANCE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]  
  
##  <a name="getambientautoclip"></a>CComControlBase::GetAmbientAutoClip  
 Alır **DISPID_AMBIENT_AUTOCLIP**, kapsayıcı denetimi görüntü alanının otomatik kırpma destekleyip desteklemediğini belirten bir bayrak.  
  
```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```  
  
### <a name="parameters"></a>Parametreler  
 *bAutoClip*  
 Özellik **DISPID_AMBIENT_AUTOCLIP**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientbackcolor"></a>CComControlBase::GetAmbientBackColor  
 Alır **DISPID_AMBIENT_BACKCOLOR**, kapsayıcı tarafından tanımlanmış tüm denetimlerin ortam arka plan rengi.  
  
```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```  
  
### <a name="parameters"></a>Parametreler  
 *Arka plan rengi*  
 Özellik **DISPID_AMBIENT_BACKCOLOR**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientcharset"></a>CComControlBase::GetAmbientCharSet  
 Alır **DISPID_AMBIENT_CHARSET**, ortam karakter kümesi kapsayıcı tarafından tanımlanan tüm denetimler için.  
  
```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```  
  
### <a name="parameters"></a>Parametreler  
 *bstrCharSet*  
 Özellik **DISPID_AMBIENT_CHARSET**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="getambientcodepage"></a>CComControlBase::GetAmbientCodePage  
 Alır **DISPID_AMBIENT_CODEPAGE**, kapsayıcı tarafından tanımlanan tüm denetimlerin ortam kod sayfası.  
  
```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```  
  
### <a name="parameters"></a>Parametreler  
 *ulCodePage*  
 Özellik **DISPID_AMBIENT_CODEPAGE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="getambientdisplayasdefault"></a>CComControlBase::GetAmbientDisplayAsDefault  
 Alır **DISPID_AMBIENT_DISPLAYASDEFAULT**, olan bir bayrak **TRUE** kapsayıcı denetimi varsayılan düğme olarak bu site içinde işaretlenmiş ve bir düğme denetimi kendisiyle bu nedenle çizip bir Kalın çerçeve.  
  
```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```  
  
### <a name="parameters"></a>Parametreler  
 `bDisplayAsDefault`  
 Özellik **DISPID_AMBIENT_DISPLAYASDEFAULT**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientdisplayname"></a>CComControlBase::GetAmbientDisplayName  
 Alır **DISPID_AMBIENT_DISPLAYNAME**, kapsayıcı denetimi tarafından sağlanan adı.  
  
```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```  
  
### <a name="parameters"></a>Parametreler  
 *bstrDisplayName*  
 Özellik **DISPID_AMBIENT_DISPLAYNAME**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientfont"></a>CComControlBase::GetAmbientFont  
 Alır kapsayıcı için bir işaretçi ortam `IFont` arabirimi.  
  
```
HRESULT GetAmbientFont(IFont** ppFont);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppFont`  
 Kapsayıcı için bir işaretçi ortam [IFont](http://msdn.microsoft.com/library/windows/desktop/ms680673) arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik ise **NULL**, işaretçi **NULL**. İşaretçinin değilse **NULL**, çağıran işaretçinin serbest bırakmanız gerekir.  
  
##  <a name="getambientfontdisp"></a>CComControlBase::GetAmbientFontDisp  
 Alır kapsayıcı için bir işaretçi ortam **IFontDisp** gönderme arabirimi.  
  
```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppFont`  
 Kapsayıcı için bir işaretçi ortam [IFontDisp](http://msdn.microsoft.com/library/windows/desktop/ms692695) gönderme arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik ise **NULL**, işaretçi **NULL**. İşaretçinin değilse **NULL**, çağıran işaretçinin serbest bırakmanız gerekir.  
  
##  <a name="getambientforecolor"></a>CComControlBase::GetAmbientForeColor  
 Alır **DISPID_AMBIENT_FORECOLOR**, kapsayıcı tarafından tanımlanan tüm denetimlerin ortam ön plan rengi.  
  
```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```  
  
### <a name="parameters"></a>Parametreler  
 *ForeColor*  
 Özellik **DISPID_AMBIENT_FORECOLOR**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientlocaleid"></a>CComControlBase::GetAmbientLocaleID  
 Alır **DISPID_AMBIENT_LOCALEID**, kapsayıcı tarafından kullanılan dil tanıtıcısı.  
  
```
HRESULT GetAmbientLocaleID(LCID& lcid);
```  
  
### <a name="parameters"></a>Parametreler  
 `lcid`  
 Özellik **DISPID_AMBIENT_LOCALEID**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim bu tanımlayıcı, farklı diller için kullanıcı arabirimi uyarlamak için kullanabilirsiniz.  
  
##  <a name="getambientmessagereflect"></a>CComControlBase::GetAmbientMessageReflect  
 Alır **DISPID_AMBIENT_MESSAGEREFLECT**, kapsayıcı pencere iletileri almak istediği olup olmadığını belirten bir bayrak (gibi `WM_DRAWITEM`) olayları olarak.  
  
```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```  
  
### <a name="parameters"></a>Parametreler  
 `bMessageReflect`  
 Özellik **DISPID_AMBIENT_MESSAGEREFLECT**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientpalette"></a>CComControlBase::GetAmbientPalette  
 Alır **DISPID_AMBIENT_PALETTE**, kapsayıcının erişmek için kullanılan `HPALETTE`.  
  
```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```  
  
### <a name="parameters"></a>Parametreler  
 `hPalette`  
 Özellik **DISPID_AMBIENT_PALETTE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientproperty"></a>CComControlBase::GetAmbientProperty  
 Belirtilen kapsayıcı özelliği alır `dispid`.  
  
```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```  
  
### <a name="parameters"></a>Parametreler  
 `dispid`  
 Alınacak kapsayıcı özellik tanımlayıcısı.  
  
 `var`  
 Özellik almak için değişkeni.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL yardımcı işlevleri belirli özelliklerini almak için bir dizi sağlanan [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Kullanılabilir uygun bir yöntem ise `GetAmbientProperty`.  
  
##  <a name="getambientrighttoleft"></a>CComControlBase::GetAmbientRightToLeft  
 Alır **DISPID_AMBIENT_RIGHTTOLEFT**, içerik kapsayıcı görüntülenir yönü.  
  
```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```  
  
### <a name="parameters"></a>Parametreler  
 *bRightToLeft*  
 Özellik **DISPID_AMBIENT_RIGHTTOLEFT**. Kümesine **TRUE** içerik sağdan sola görüntüleniyorsa, **FALSE** sağdan sola görüntüleniyorsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="getambientscaleunits"></a>CComControlBase::GetAmbientScaleUnits  
 Alır **DISPID_AMBIENT_SCALEUNITS**, görüntüler etiketleme kapsayıcının ortam birim (inç veya gibi santimetreden).  
  
```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```  
  
### <a name="parameters"></a>Parametreler  
 *bstrScaleUnits*  
 Özellik **DISPID_AMBIENT_SCALEUNITS**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientshowgrabhandles"></a>CComControlBase::GetAmbientShowGrabHandles  
 Alır **DISPID_AMBIENT_SHOWGRABHANDLES**, kapsayıcı Al tanıtıcıları kendisi için etkin olduğunda görüntülemek üzere denetimi izin verip vermediğini belirten bir bayrak.  
  
```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```  
  
### <a name="parameters"></a>Parametreler  
 *bShowGrabHandles*  
 Özellik **DISPID_AMBIENT_SHOWGRABHANDLES**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientshowhatching"></a>CComControlBase::GetAmbientShowHatching  
 Alır **DISPID_AMBIENT_SHOWHATCHING**, kapsayıcı denetimin kullanıcı arabirimi etkin olduğunda kendisini taranmış bir desenle görüntülemek üzere denetimi izin verip vermediğini belirten bir bayrak.  
  
```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```  
  
### <a name="parameters"></a>Parametreler  
 *bShowHatching*  
 Özellik **DISPID_AMBIENT_SHOWHATCHING**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambientsupportsmnemonics"></a>CComControlBase::GetAmbientSupportsMnemonics  
 Alır **DISPID_AMBIENT_SUPPORTSMNEMONICS**, kapsayıcı klavye anımsatıcıları destekleyip desteklemediğini belirten bir bayrak.  
  
```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```  
  
### <a name="parameters"></a>Parametreler  
 *bSupportsMnemonics*  
 Özellik **DISPID_AMBIENT_SUPPORTSMNEMONICS**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambienttextalign"></a>CComControlBase::GetAmbientTextAlign  
 Alır **DISPID_AMBIENT_TEXTALIGN**, kapsayıcı tarafından tercih edilen metin hizalamasını: Genel hizalama (numaraları sağdaki metni sola) için 0, 1 sol hizalaması için Ortala için 2 ve 3 sağa hizalama için.  
  
```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```  
  
### <a name="parameters"></a>Parametreler  
 *nTextAlign*  
 Özellik **DISPID_AMBIENT_TEXTALIGN**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getambienttoptobottom"></a>CComControlBase::GetAmbientTopToBottom  
 Alır **DISPID_AMBIENT_TOPTOBOTTOM**, içerik kapsayıcı görüntülenir yönü.  
  
```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```  
  
### <a name="parameters"></a>Parametreler  
 *bTopToBottom*  
 Özellik **DISPID_AMBIENT_TOPTOBOTTOM**. Kümesine **TRUE** metin görüntüleniyorsa yukarıdan aşağıya doğru **FALSE** görüntüleniyorsa, aşağıdan yukarıya.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="getambientuidead"></a>CComControlBase::GetAmbientUIDead  
 Alır **DISPID_AMBIENT_UIDEAD**, kapsayıcı denetimi için kullanıcı arabirimi eylemlerini yanıtlamasını isteyip istemediğini gösteren bir bayrak.  
  
```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```  
  
### <a name="parameters"></a>Parametreler  
 *bUIDead*  
 Özellik **DISPID_AMBIENT_UIDEAD**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa **doğru**, denetimi yanıt. Bağımsız olarak, bu bayrağı uygulanır **DISPID_AMBIENT_USERMODE** bayrağı. Bkz: [CComControlBase::GetAmbientUserMode](#getambientusermode).  
  
##  <a name="getambientusermode"></a>CComControlBase::GetAmbientUserMode  
 Alır **DISPID_AMBIENT_USERMODE**, kapsayıcı çalışma modunda olup olmadığını belirten bir bayrak ( **TRUE**) veya Tasarım modunda ( **FALSE**).  
  
```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `bUserMode`  
 Özellik **DISPID_AMBIENT_USERMODE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
##  <a name="getdirty"></a>CComControlBase::GetDirty  
 Veri üyesi değerini döndürür `m_bRequiresSave`.  
  
```
BOOL GetDirty();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veri üyesi değerini döndürür [m_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer kullanılarak ayarlanan [CComControlBase::SetDirty](#setdirty).  
  
##  <a name="getzoominfo"></a>CComControlBase::GetZoomInfo  
 X ve y alır pay ve yakınlaştırma faktörünü payda değerleri bir denetimi için etkinleştirilmiş için yerinde düzenleme.  
  
```
void GetZoomInfo(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parametreler  
 `di`  
 Yakınlaştırma faktörünü 's pay ve payda barındıracak yapısı. Daha fazla bilgi için bkz: [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Yakınlaştırma faktörünü denetimin doğal boyutu, geçerli ölçüde oranını ' dir.  
  
##  <a name="inplaceactivate"></a>CComControlBase::InPlaceActivate  
 Ne olursa olsun fiil durum devre dışı durumuna geçiş denetimi neden `iVerb` gösterir.  
  
```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `iVerb`  
 Tarafından gerçekleştirilecek eylemi belirten değer [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).  
  
 *prcPosRect*  
 Yerinde denetimin konumunu işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkinleştirme önce bu yöntem denetler denetimi bir istemci siteye sahip, denetimin ne kadarının görünür olduğunu denetler ve ana penceresinde denetimin konumunu alır. Denetim etkinleştirildikten sonra bu yöntem denetimin kullanıcı arabirimini etkinleştirir ve denetimi görünür hale getirmek için kapsayıcı söyler.  
  
 Bu yöntem aynı zamanda alır bir `IOleInPlaceSite`, **IOleInPlaceSiteEx**, veya **IOleInPlaceSiteWindowless** denetimi için arabirim işaretçisi ve denetim sınıfın veri üyesi depolar[CComControlBase::m_spInPlaceSite](#m_spinplacesite). Denetim sınıfı veri üyeleri [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)ve [ CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) true olarak uygun şekilde ayarlanır.  
  
##  <a name="internalgetsite"></a>CComControlBase::InternalGetSite  
 Denetim site için tanımlanan arayüzü için bir işaretçi sorgulamak için bu yöntemi çağırın.  
  
```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```  
  
### <a name="parameters"></a>Parametreler  
 `riid`  
 İçinde döndürülmelidir arabirim işaretçisi IID `ppUnkSite`.  
  
 `ppUnkSite`  
 İçinde istenen arabirim işaretçisi alan işaretçi değişkeninin adresi `riid`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Site içinde istenen arabirimi destekliyorsa `riid`, işaretçi yoluyla döndürülen `ppUnkSite`. Aksi takdirde, `ppUnkSite` NULL olarak ayarlandı.  
  
##  <a name="m_bautosize"></a>CComControlBase::m_bAutoSize  
 Denetim herhangi bir boyutta olamaz belirten bayrak.  
  
```
unsigned m_bAutoSize:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak tarafından denetlenir `IOleObjectImpl::SetExtent` ve **TRUE**, işlevinin döndürmesine neden olan **E_FAIL**.  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 Eklerseniz **otomatik boyutu** seçeneği [hisse senedi özellikleri](../../atl/reference/stock-properties-atl-control-wizard.md) ATL Denetim Sihirbazı, sihirbazın sekmesinde otomatik olarak bu veri üyesi denetim sınıfınızda oluşturur, put oluşturur ve yöntemleri özelliği için alma ve destekleyen [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) özelliği değiştiğinde kapsayıcı otomatik olarak bildirir.  
  
##  <a name="m_bdrawfromnatural"></a>CComControlBase::m_bDrawFromNatural  
 Gösteren bayrağı `IDataObjectImpl::GetData` ve `CComControlBase::GetZoomInfo` denetim boyutundan ayarlamalısınız `m_sizeNatural` yerine `m_sizeExtent`.  
  
```
unsigned m_bDrawFromNatural:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_bdrawgetdatainhimetric"></a>CComControlBase::m_bDrawGetDataInHimetric  
 Gösteren bayrağı `IDataObjectImpl::GetData` HIMETRIC birimleri ve değil piksel çizerken kullanmanız gerekir.  
  
```
unsigned m_bDrawGetDataInHimetric:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her mantıksal HIMETRIC 0,01 milimetre birimdir.  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_binplaceactive"></a>CComControlBase::m_bInPlaceActive  
 Denetim yerinde etkin olduğunu gösteren bayrak.  
  
```
unsigned m_bInPlaceActive:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu denetim görülebilir ve varsa, onun penceresi görünür, ancak kendi menüleri ve araç çubuklarını etkin olmayabilir anlamına gelir. `m_bUIActive` Bayrağı gösterir menüleri gibi denetimin kullanıcı arabirimi etkin olduğu aynı zamanda.  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_binplacesiteex"></a>CComControlBase::m_bInPlaceSiteEx  
 Bayrak kapsayıcı destekler belirten **IOleInPlaceSiteEx** arabirimi ve OCX96 kontrol penceresiz ve titreşimsiz denetimleri gibi özellikleri.  
  
```
unsigned m_bInPlaceSiteEx:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 Veri üyesi `m_spInPlaceSite` işaret eden bir [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), veya [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) değerine bağlı olarak arabirimi `m_bWndLess` ve `m_bInPlaceSiteEx` bayrakları. (Veri üyesi `m_bNegotiatedWnd` olmalıdır **TRUE** için `m_spInPlaceSite` geçerli olması için işaretçi.)  
  
 Varsa `m_bWndLess` olan **FALSE** ve `m_bInPlaceSiteEx` olan **TRUE**, `m_spInPlaceSite` olan bir **IOleInPlaceSiteEx** arabirim işaretçisi. Bkz: [m_spInPlaceSite](#m_spinplacesite) bu üç veri üyeleri arasındaki ilişkiyi gösteren bir tablo için.  
  
##  <a name="m_bnegotiatedwnd"></a>CComControlBase::m_bNegotiatedWnd  
 OCX96 denetim özellikleri (örneğin, titreşimsiz ve penceresiz denetimleri) desteği hakkında kapsayıcısı ile denetimi desteklemediğini anlaşılan ve denetimi pencereli veya penceresiz olup olmadığını belirten bayrak.  
  
```
unsigned m_bNegotiatedWnd:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 `m_bNegotiatedWnd` Bayrağı olmalıdır **TRUE** için `m_spInPlaceSite` geçerli olması için işaretçi.  
  
##  <a name="m_brecomposeonresize"></a>CComControlBase::m_bRecomposeOnResize  
 Kapsayıcı denetimin görüntüleme boyutu değiştiğinde kendi sunu yeniden oluşturmak denetimi istediği belirten bayrak.  
  
```
unsigned m_bRecomposeOnResize:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 Bu bayrak tarafından denetlenir [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) ve **TRUE**, `SetExtent` değişiklikleri görüntüleme kapsayıcı bildirir. Bu bayrağı ayarlarsanız **OLEMISC_RECOMPOSEONRESIZE** içinde bit [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) numaralandırma de ayarlanmalıdır.  
  
##  <a name="m_brequiressave"></a>CComControlBase::m_bRequiresSave  
 Son kaydedilişinden denetimi değiştiğini gösteren bayrak.  
  
```
unsigned m_bRequiresSave:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Değeri `m_bRequiresSave` ile ayarlayabilirsiniz [CComControlBase::SetDirty](#setdirty) ve ile alınan [CComControlBase::GetDirty](#getdirty).  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_bresizenatural"></a>CComControlBase::m_bResizeNatural  
 Denetim istediği kendi doğal ölçüde (ölçeklendirilmemiş fiziksel boyutuna) yeniden boyutlandırmak belirten bayrak denetimin görüntüleme boyutu değiştiğinde kapsayıcı.  
  
```
unsigned m_bResizeNatural:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bayrak tarafından denetlenir `IOleObjectImpl::SetExtent` ve **TRUE**, içine boyutu geçti `SetExtent` atandığı `m_sizeNatural`.  
  
 İçine boyutu geçti `SetExtent` her zaman atanan `m_sizeExtent`değerinin ne olursa olsun `m_bResizeNatural`.  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_buiactive"></a>CComControlBase::m_bUIActive  
 Menüleri ve araç çubukları gibi denetimin kullanıcı arabirimi belirten bayrak etkindir.  
  
```
unsigned m_bUIActive:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_bInPlaceActive` Bayrağı denetimi etkin, ancak değil, olduğunu gösterir, kullanıcı arabirimi etkindir.  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_busingwindowrgn"></a>CComControlBase::m_bUsingWindowRgn  
 Kapsayıcı tarafından sağlanan penceresi bölge denetimi kullanarak belirten bayrak.  
  
```
unsigned m_bUsingWindowRgn:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_bwasoncewindowless"></a>CComControlBase::m_bWasOnceWindowless  
 Denetim penceresiz, ancak olabilir veya artık penceresiz olmayabilir belirten bayrak.  
  
```
unsigned m_bWasOnceWindowless:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_bwindowonly"></a>CComControlBase::m_bWindowOnly  
 Penceresiz denetimlerini kapsayıcı destekleyen olsa bile denetimi pencereli, belirten bayrak.  
  
```
unsigned m_bWindowOnly:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_bwndless"></a>CComControlBase::m_bWndLess  
 Denetim penceresiz belirten bayrak.  
  
```
unsigned m_bWndLess:1;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 Veri üyesi `m_spInPlaceSite` işaret eden bir [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), veya [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) değerine bağlı olarak arabirimi `m_bWndLess` ve [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) bayrakları. (Veri üyesi [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) olmalıdır **TRUE** için [CComControlBase::m_spInPlaceSite](#m_spinplacesite) geçerli olması için işaretçi.)  
  
 Varsa `m_bWndLess` olan **TRUE**, `m_spInPlaceSite` olan bir **IOleInPlaceSiteWindowless** arabirim işaretçisi. Bkz: [CComControlBase::m_spInPlaceSite](#m_spinplacesite) bu veri üyeleri arasında tam ilişki gösteren bir tablo için.  
  
##  <a name="m_hwndcd"></a>CComControlBase::m_hWndCD  
 Denetimle ilişkili bir pencere tanıtıcının başvuru içeriyor.  
  
```
HWND& m_hWndCD;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_nfreezeevents"></a>CComControlBase::m_nFreezeEvents  
 Kaç kez sayısını kapsayıcı olayları (olayları kabulü) bir araya giren çözme (olayları kabul etmeyi reddetti) olayları dondurulmuş.  
  
```
short m_nFreezeEvents;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_rcpos"></a>CComControlBase::m_rcPos  
 Kapsayıcı koordinatlarında ifade denetimin konumunu piksel cinsinden.  
  
```
RECT m_rcPos;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_sizeextent"></a>CComControlBase::m_sizeExtent  
 Belirli bir ekran HIMETRIC birimlerini (her 0,01 milimetre birimdir) denetiminde uzantı.  
  
```
SIZE m_sizeExtent;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 Bu boyut tarafından gösterilecek ölçeklendirilir. Denetimin fiziksel boyutu belirtilen `m_sizeNatural` veri üyesi ve sabittir.  
  
 Genel işlevi ile piksel boyutu dönüştürebilir [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).  
  
##  <a name="m_sizenatural"></a>CComControlBase::m_sizeNatural  
 (Her 0,01 milimetre birimdir) HIMETRIC birimleri denetiminde fiziksel boyutu.  
  
```
SIZE m_sizeNatural;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 Bu boyut boyutu sırasında sabittir `m_sizeExtent` tarafından gösterilecek ölçeklendirilir.  
  
 Genel işlevi ile piksel boyutu dönüştürebilir [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).  
  
##  <a name="m_spadvisesink"></a>CComControlBase::m_spAdviseSink  
 Kapsayıcı danışma bağlantısı için doğrudan bir işaretçi (kapsayıcının [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).  
  
```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```     
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_spambientdispatch"></a>CComControlBase::m_spAmbientDispatch  
 A `CComDispatchDriver` almak ve aracılığıyla bir nesnenin özelliklerini ayarlamanıza olanak sağlayan nesne bir `IDispatch` işaretçi.  
  
```
CComDispatchDriver m_spAmbientDispatch;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_spclientsite"></a>CComControlBase::m_spClientSite  
 Kapsayıcı içinde denetimin istemci site için bir işaretçi.  
  
```
CComPtr<IOleClientSite>
    m_spClientSite;
```     
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
##  <a name="m_spdataadviseholder"></a>CComControlBase::m_spDataAdviseHolder  
 Veri nesneleri arasındaki danışma bağlantıları basılı tutun ve havuzlarını bildirmek için bir standart araçları sağlar.  
  
```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```     
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 Bir veri nesnesi verilerin aktarılabileceği ve uygulayan bir denetimi olan [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), veri biçimi ve aktarım Orta olan yöntemleri belirtin.  
  
 Arabirim `m_spDataAdviseHolder` uygulayan [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) ve [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) kurmak ve kapsayıcısı danışma bağlantıları silme yöntemleri. Denetimin kapsayıcı bir öneri havuz destekleyerek uygulamalıdır [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) arabirimi.  
  
##  <a name="m_spinplacesite"></a>CComControlBase::m_spInPlaceSite  
 Kapsayıcının gösteren bir işaretçi [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), veya [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) arabirim işaretçisi.  
  
```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```     
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 `m_spInPlaceSite` İşaretçidir geçerli yalnızca [m_bNegotiatedWnd](#m_bnegotiatedwnd) bayrağı **doğru**.  
  
 Aşağıdaki tabloda nasıl `m_spInPlaceSite` işaretçi türü bağımlı [m_bWndLess](#m_bwndless) ve [m_bInPlaceSiteEx](#m_binplacesiteex) veri üyesi bayrakları:  
  
|m_spInPlaceSite türü|m_bWndLess değeri|m_bInPlaceSiteEx değeri|  
|---------------------------|-----------------------|-----------------------------|  
|**IOleInPlaceSiteWindowless**|**TRUE**|**DOĞRU** veya **FALSE**|  
|**IOleInPlaceSiteEx**|**FALSE**|**TRUE**|  
|`IOleInPlaceSite`|**FALSE**|**FALSE**|  
  
##  <a name="m_spoleadviseholder"></a>CComControlBase::m_spOleAdviseHolder  
 Standart uygulaması danışma bağlantıları tutmak için bir yol sağlar.  
  
```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```     
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için onu bir veri üyesi olarak denetim sınıfınızda bildirmeniz gerekir. Bir birleşim taban sınıf içinde içinde bildirildiğinden denetim sınıfınıza bu veri üyesi temel sınıfından devralmaz.  
  
 Arabirim `m_spOleAdviseHolder` uygulayan [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) ve [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) kurmak ve kapsayıcısı danışma bağlantıları silme yöntemleri. Denetimin kapsayıcı bir öneri havuz destekleyerek uygulamalıdır [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) arabirimi.  
  
##  <a name="ondraw"></a>CComControlBase::OnDraw  
 Denetim çizmek için bu yöntemi geçersiz kılın.  
  
```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parametreler  
 `di`  
 Bir başvuru [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) denetim sınırları çizim en boy gibi çizim bilgileri içeren yapısı ve çizim optimize edilmiştir değil.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan `OnDraw` siler veya cihaz bağlamı geri yükler veya kümesinde bayrakları bağlı hiçbir şey yapmaz [CComControlBase::OnDrawAdvanced](#ondrawadvanced).  
  
 Bir `OnDraw` ATL Denetim Sihirbazı'yla denetiminizi oluşturduğunuzda yöntemi denetim sınıfınıza otomatik olarak eklenir. Sihirbazın varsayılan `OnDraw` "ATL 8.0" etiketli bir dikdörtgen çizer.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CComControlBase::GetAmbientAppearance](#getambientappearance).  
  
##  <a name="ondrawadvanced"></a>CComControlBase::OnDrawAdvanced  
 Varsayılan `OnDrawAdvanced` normalleştirilmiş cihaz bağlamı çizim için hazırlar ve ardından Denetim sınıfınızın çağırır `OnDraw` yöntemi.  
  
```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>Parametreler  
 `di`  
 Bir başvuru [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) denetim sınırları çizim en boy gibi çizim bilgileri içeren yapısı ve çizim optimize edilmiştir değil.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Normalleştirme olmadan kapsayıcı tarafından geçirilen cihaz bağlamı kabul etmek istiyorsanız bu yöntemi geçersiz kılın.  
  
 Bkz: [CComControlBase::OnDraw](#ondraw) daha fazla ayrıntı için.  
  
##  <a name="onkillfocus"></a>CComControlBase::OnKillFocus  
 Denetim yerinde etkin ve geçerli denetim sitesinde ardından kapsayıcı denetimi odağını kaybetmiş bildirir denetler.  
  
```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMsg`  
 Ayrılmış.  
  
 `wParam`  
 Ayrılmış.  
  
 `lParam`  
 Ayrılmış.  
  
 `bHandled`  
 Pencere iletisi başarılı bir şekilde yürütüldü olup olmadığını belirten bayrak. Varsayılan, `FALSE` değeridir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
##  <a name="onmouseactivate"></a>CComControlBase::OnMouseActivate  
 Kullanıcı Arabirimi kullanıcı modunda sonra denetimi etkinleştirir denetler.  
  
```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMsg`  
 Ayrılmış.  
  
 `wParam`  
 Ayrılmış.  
  
 `lParam`  
 Ayrılmış.  
  
 `bHandled`  
 Pencere iletisi başarılı bir şekilde yürütüldü olup olmadığını belirten bayrak. Varsayılan, `FALSE` değeridir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
##  <a name="onpaint"></a>CComControlBase::OnPaint  
 Boyama için kapsayıcı hazırlar, denetimin istemci alanını alır ve ardından Denetim sınıfının çağırır `OnDrawAdvanced` yöntemi.  
  
```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMsg`  
 Ayrılmış.  
  
 `wParam`  
 Varolan bir HDC.  
  
 `lParam`  
 Ayrılmış.  
  
 `lResult`  
 Ayrılmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman sıfır verir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `wParam` NULL değil `OnPaint` geçerli HDC içerir ve bunun yerine kullanır varsayar [CComControlBase::m_hWndCD](#m_hwndcd).  
  
##  <a name="onsetfocus"></a>CComControlBase::OnSetFocus  
 Denetim yerinde etkin ve geçerli denetim sitesinde ardından kapsayıcı denetimi bildirir denetimleri odak kazanılan.  
  
```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMsg`  
 Ayrılmış.  
  
 `wParam`  
 Ayrılmış.  
  
 `lParam`  
 Ayrılmış.  
  
 `bHandled`  
 Pencere iletisi başarılı bir şekilde yürütüldü olup olmadığını belirten bayrak. Varsayılan, `FALSE` değeridir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman 1 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim odağı aldı kapsayıcı bildirim gönderir.  
  
##  <a name="pretranslateaccelerator"></a>CComControlBase::PreTranslateAccelerator  
 Kendi klavye kısayol işleyicileri sağlamak için bu yöntemi geçersiz kılın.  
  
```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```  
  
### <a name="parameters"></a>Parametreler  
 `pMsg`  
 Ayrılmış.  
  
 *hRet*  
 Ayrılmış.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan olarak döndürür **FALSE**.  
  
##  <a name="sendonclose"></a>CComControlBase::SendOnClose  
 Denetim kapatıldı öneri sahibi ile kayıtlı tüm danışma havuzlarını bildirir.  
  
```
HRESULT SendOnClose();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim danışma havuzlarını kapattı bir bildirim gönderir.  
  
##  <a name="sendondatachange"></a>CComControlBase::SendOnDataChange  
 Denetim verileri değişti öneri sahibi ile kayıtlı tüm danışma havuzlarını bildirir.  
  
```
HRESULT SendOnDataChange(DWORD advf = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *advf*  
 Belirttiğiniz bayrakları bildirmek nasıl çağrısı [IAdviseSink::OnDataChange](http://msdn.microsoft.com/library/windows/desktop/ms687283) yapılır. Değerler: [ADVF](http://msdn.microsoft.com/library/windows/desktop/ms693742) numaralandırması.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
##  <a name="sendonrename"></a>CComControlBase::SendOnRename  
 Denetimi yeni bir bilinen ad sahip öneri sahibi ile kayıtlı tüm danışma havuzlarını bildirir.  
  
```
HRESULT SendOnRename(IMoniker* pmk);
```  
  
### <a name="parameters"></a>Parametreler  
 *PMK*  
 Yeni ad denetiminin işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Ad denetimi için değişen bir bildirim gönderir.  
  
##  <a name="sendonsave"></a>CComControlBase::SendOnSave  
 Denetim kaydedilmiş öneri sahibi ile kayıtlı tüm danışma havuzlarını bildirir.  
  
```
HRESULT SendOnSave();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim verileri yalnızca kaydetti bir bildirim gönderir.  
  
##  <a name="sendonviewchange"></a>CComControlBase::SendOnViewChange  
 Denetimin görünüm değişti danışma havuzlarını tüm kayıtlı bildirir.  
  
```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwAspect`  
 En boy veya denetimin görünüm.  
  
 *Dizin*  
 Görünümünün değişen. Yalnızca -1, geçerli değil.  
  
### <a name="return-value"></a>Dönüş Değeri  
 S_OK başarı veya başarısızlık HRESULT hata döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `SendOnViewChange`çağrıları [IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337). Yalnızca değeri *dizin* ilgi tüm görünüm gösterir -1 olan şu anda desteklenmiyor.  
  
##  <a name="setcontrolfocus"></a>CComControlBase::SetControlFocus  
 Klavye odağı ya da denetiminden kaldırır veya ayarlar.  
  
```
BOOL SetControlFocus(BOOL bGrab);
```  
  
### <a name="parameters"></a>Parametreler  
 *bGrab*  
 Varsa **doğru**, klavye odağı arama denetimi için ayarlar. Varsa **yanlış**, odağa sahip sağlanan arama denetiminden klavye odağını kaldırır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** denetimi odağı; başarıyla alırsa, aksi takdirde, **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows API işlevi pencereli bir denetim için [SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312) olarak adlandırılır. Penceresiz bir denetim için [IOleInPlaceSiteWindowless::SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms679745) olarak adlandırılır. Bu çağrı aracılığıyla penceresiz bir denetim klavye odağını alır ve pencere iletileri yanıt verebilir.  
  
##  <a name="setdirty"></a>CComControlBase::SetDirty  
 Veri üyesi ayarlar `m_bRequiresSave` değerine `bDirty`.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Parametreler  
 `bDirty`  
 Veri üyesi değerini [CComControlBase::m_bRequiresSave](#m_brequiressave).  
  
### <a name="remarks"></a>Açıklamalar  
 **SetDirty(TRUE)** son kaydedilişinden denetimi değiştiğini bayrak için çağrılmalıdır. Değeri `m_bRequiresSave` ile alınan [CComControlBase::GetDirty](#getdirty).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
