---
title: CComControlBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18666cc619796bc7ee0216eb9cdf020bd8d8a6f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035753"
---
# <a name="ccomcontrolbase-class"></a>CComControlBase sınıfı

Bu sınıf, oluşturmak ve ATL denetimleri yönetmek için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CComControlBase::AppearanceType](#appearancetype)|Geçersiz kılmak, `m_nAppearance` stok özellik türü olmayan **kısa**.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComControlBase::CComControlBase](#ccomcontrolbase)|Oluşturucu.|
|[CComControlBase:: ~ CComControlBase](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Denetleyen *iVerb* tarafından kullanılan parametre `IOleObjectImpl::DoVerb` denetimin kullanıcı arabirimini etkinleştirir ya da (*iVerb* OLEIVERB_UIACTIVATE eşittir), kullanıcı çift tıkladığında gerçekleştirilecek eylemi tanımlar Denetim (*iVerb* OLEIVERB_PRIMARY eşittir), denetim (*iVerb* OLEIVERB_SHOW eşittir), veya denetim etkinleştirir (*iVerb* OLEIVERB eşittir _INPLACEACTIVATE).|
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Denetleyen *iVerb* tarafından kullanılan parametre `IOleObjectImpl::DoVerb` etkinleştirmek kullanıcı arabirimi denetim neden olur ve true değer döndürür.|
|[CComControlBase::DoVerbProperties](#doverbproperties)|Denetimin özellik sayfalarını görüntüler.|
|[CComControlBase::FireViewChange](#fireviewchange)|Denetim yeniden çizmek için kapsayıcı bildirmek için bu yöntemi çağırın veya denetimin görünüm değiştirildi kayıtlı öneri havuzlarını bildirir.|
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|DISPID_AMBIENT_APPEARANCE, denetlemek için bu ayarı geçerli görünümünü alır: düz ve 3B 1 için 0.|
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|DISPID_AMBIENT_AUTOCLIP, kapsayıcı denetimi görüntüleme alanının otomatik kırpma destekleyip desteklemediğini belirten bir bayrak alır.|
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|DISPID_AMBIENT_BACKCOLOR, kapsayıcı tarafından tanımlanan tüm denetimler için ortam arka plan rengini alır.|
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|DISPID_AMBIENT_CHARSET, ortam karakter kapsayıcı tarafından tanımlanan tüm denetimler için kümesini alır.|
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|DISPID_AMBIENT_CODEPAGE, ortam karakter kapsayıcı tarafından tanımlanan tüm denetimler için kümesini alır.|
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|DISPID_AMBIENT_DISPLAYASDEFAULT, kapsayıcı denetimi bu sitedeki varsayılan düğme olarak işaretlenmiş ve bu nedenle bir düğme denetimi kendisini bir kalın kenarlığa sahip çizip TRUE ise bir bayrak alır.|
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|DISPID_AMBIENT_DISPLAYNAME, kapsayıcı denetimi tarafından sağlanan adını alır.|
|[CComControlBase::GetAmbientFont](#getambientfont)|Alır bir işaretçi kapsayıcıya ortam `IFont` arabirimi.|
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Alır bir işaretçi kapsayıcıya ortam `IFontDisp` gönderme arabirimi.|
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|DISPID_AMBIENT_FORECOLOR, kapsayıcı tarafından tanımlanan tüm denetimler için ortam ön plan rengini alır.|
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|DISPID_AMBIENT_LOCALEID, kapsayıcı tarafından kullanılan dil tanımlayıcısını alır.|
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|DISPID_AMBIENT_MESSAGEREFLECT, kapsayıcı olaylarla (örneğin, WM_DRAWITEM) pencere iletilerini almak isteyip istemediğini belirten bir bayrak alır.|
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Kapsayıcının HPALETTE erişmek için kullanılan DISPID_AMBIENT_PALETTE, alır.|
|[CComControlBase::GetAmbientProperty](#getambientproperty)|Belirtilen kapsayıcı özelliği alır *kimliği*.|
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|DISPID_AMBIENT_RIGHTTOLEFT, içeriği kapsayıcı tarafından görüntülenen yönünü alır.|
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|DISPID_AMBIENT_SCALEUNITS, görüntüler etiketleme kapsayıcının ortam birim (inç veya gibi inç) alır.|
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|DISPID_AMBIENT_SHOWGRABHANDLES, kapsayıcı tutamaçların kendisi için etkin olduğunda gösterilecek denetim izin verip vermediğini belirten bir bayrak alır.|
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|DISPID_AMBIENT_SHOWHATCHING, kapsayıcı denetim UI etkin olduğunda, kendisini taranmış bir desenle görüntülemek izin verip vermediğini belirten bir bayrak alır.|
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|DISPID_AMBIENT_SUPPORTSMNEMONICS, kapsayıcı klavye anımsatıcıları destekleyip desteklemediğini belirten bir bayrak alır.|
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|DISPID_AMBIENT_TEXTALIGN, kapsayıcı tarafından tercih edilen metin hizalamasını alır: Genel hizalama (sağ metin numaraları sol) için 0, sola hizalama için 1, 2 Ortala ve sağa hizalama için 3.|
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|DISPID_AMBIENT_TOPTOBOTTOM, içeriği kapsayıcı tarafından görüntülenen yönünü alır.|
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|DISPID_AMBIENT_UIDEAD, kapsayıcı eylemlerine kullanıcı arabirimi yanıt verme denetimi isteyip istemediğini gösteren bir bayrak alır.|
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|DISPID_AMBIENT_USERMODE, kapsayıcı çalıştırma modu (TRUE) veya tasarım modu (FALSE) olup olmadığını belirten bir bayrak alır.|
|[CComControlBase::GetDirty](#getdirty)|Veri üyesinin değerini döndürür `m_bRequiresSave`.|
|[CComControlBase::GetZoomInfo](#getzoominfo)|X ve y alır pay ve yakınlaştırma faktörünü, payda değerleri için bir denetimi etkinleştirilmiş için yerinde düzenleme.|
|[CComControlBase::InPlaceActivate](#inplaceactivate)|İnovasyonunuz ne olursa olsun fiil durum için devre dışı durumundan geçiş denetimi neden *iVerb* gösterir.|
|[CComControlBase::InternalGetSite](#internalgetsite)|Denetim site tanımlanan arabirim işaretçisi için sorgulamak için bu yöntemi çağırın.|
|[CComControlBase::OnDraw](#ondraw)|Denetiminizi çizmek için bu yöntemi yok sayın.|
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|Varsayılan `OnDrawAdvanced` normalleştirilmiş bir cihaz bağlamı çizim için hazırlar, ardından Denetim sınıfınızın çağırır `OnDraw` yöntemi.|
|[CComControlBase::OnKillFocus](#onkillfocus)|Denetim yerinde etkin ve geçerli denetim sitenin sonra kapsayıcı denetimi odağını kaybetmiş bildirir denetler.|
|[CComControlBase::OnMouseActivate](#onmouseactivate)|UI kullanıcı modunda ve ardından Denetim etkinleştirir denetler.|
|[CComControlBase::OnPaint](#onpaint)|Boyama için kapsayıcı hazırlar, denetimin istemci alanı alır ve ardından Denetim sınıfın çağırır `OnDraw` yöntemi.|
|[CComControlBase::OnSetFocus](#onsetfocus)|Denetim yerinde etkin ve geçerli denetim sitenin sonra kapsayıcı denetimi bildirir denetimleri odak kazanılan.|
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Kendi klavye Hızlandırıcı işleyicileri sağlamak için bu yöntemi yok sayın.|
|[CComControlBase::SendOnClose](#sendonclose)|Denetim kapatıldı öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirir.|
|[CComControlBase::SendOnDataChange](#sendondatachange)|Denetim verilerinin değişti öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirir.|
|[CComControlBase::SendOnRename](#sendonrename)|Denetim yeni bir ad olduğunu öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirir.|
|[CComControlBase::SendOnSave](#sendonsave)|Denetim kaydedildi öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirir.|
|[CComControlBase::SendOnViewChange](#sendonviewchange)|Denetimin görünüm değiştirildi danışmanlık havuzlarını tüm kayıtlı bildirir.|
|[CComControlBase::SetControlFocus](#setcontrolfocus)|Klavye odağı ya da denetiminden kaldırır veya ayarlar.|
|[CComControlBase::SetDirty](#setdirty)|Veri üyesi ayarlar `m_bRequiresSave` değerine *bDirty*.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComControlBase::m_bAutoSize](#m_bautosize)|Denetim, diğer herhangi bir boyutta olamaz belirten bayrak.|
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Olduğunu belirten bayrağı `IDataObjectImpl::GetData` ve `CComControlBase::GetZoomInfo` denetim boyutundan ayarlamalısınız `m_sizeNatural` yerine `m_sizeExtent`.|
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Olduğunu belirten bayrağı `IDataObjectImpl::GetData` HIMETRIC birimleri ve değil piksel çizerken kullanmanız gerekir.|
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Denetimin yerinde etkin olup olmadığını belirten bayrak.|
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Kapsayıcı destekler belirten bayrak `IOleInPlaceSiteEx` arabirimi ve OCX96 kontrol penceresiz ve titreşimsiz denetimleri gibi özellikleri.|
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Denetim (örneğin, titreşimsiz ve penceresiz denetimleri) OCX96 denetim özellikleri için desteği hakkında daha fazla kapsayıcı ile olup olmadığı anlaşılan ve denetim pencereli veya penceresiz olup olmadığını belirten bayrak.|
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Denetim kapsayıcı denetimin görüntüleme boyutu değiştiğinde, sunu yeniden oluşturmak istiyor belirten bayrak.|
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Denetimi son kez kaydedildiğinden beri değiştirildi belirten bayrak.|
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Denetim istediği doğal kapsamı (ölçeklendirilmemiş fiziksel boyutuna) yeniden boyutlandırmak belirten bayrak kapsayıcı denetimin görüntüleme boyutu değiştiğinde.|
|[CComControlBase::m_bUIActive](#m_buiactive)|Denetimin menüleri ve araç çubukları gibi kullanıcı arabirimi belirten bayrağı etkin değil.|
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Denetimin, kapsayıcı tarafından sağlanan pencere bölgesi kullanarak belirten bayrak.|
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Denetim penceresiz, alındı ancak olabilir veya artık penceresiz olmayabilir belirten bayrak.|
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|Kapsayıcı penceresiz denetimleri destekler olsa bile denetim pencereli, olmalıdır belirten bayrak.|
|[CComControlBase::m_bWndLess](#m_bwndless)|Denetimin penceresiz olup olmadığını belirten bayrak.|
|[CComControlBase::m_hWndCD](#m_hwndcd)|Denetimle ilişkili pencere tanıtıcısı başvuru içeriyor.|
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Kaç kez sayısını kapsayıcı (olayları kabul reddetti) olayları (olayları kabulü) olayların müdahalede bulunan bir çözme dondurulmuş.|
|[CComControlBase::m_rcPos](#m_rcpos)|Piksel cinsinden denetimin kapsayıcısının koordinatlarında belirtilen konumu.|
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Uzantı denetimin belirli bir ekran için HIMETRIC birimleri (her birim 0,01 milimetre'dir).|
|[CComControlBase::m_sizeNatural](#m_sizenatural)|(Her birim 0,01 milimetre'dir) HIMETRIC birimleri denetiminde fiziksel boyutu.|
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Kapsayıcı danışmanlık bağlantısında doğrudan bir işaretçiye (kapsayıcının [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink)).|
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|A `CComDispatchDriver` almak ve kapsayıcının özellikleri aracılığıyla ayarlamanıza olanak sağlayan bir nesne bir `IDispatch` işaretçi.|
|[CComControlBase::m_spClientSite](#m_spclientsite)|Denetimin istemci site kapsayıcı içindeki bir işaretçi.|
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Veri nesneleri arasında danışmanlık bağlantılar basılı tutun ve havuzlarını bildirmek için standart araçları sağlar.|
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Kapsayıcının işaretçisi [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), veya [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arabirim işaretçisi.|
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Standart bir danışmanlık bağlantılarını tutmak için bir yöntem uygulamasını sağlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, oluşturmak ve ATL denetimleri yönetmek için yöntemler sağlar. [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md) türetildiği `CComControlBase`. ATL Denetim Sihirbazı'nı kullanarak bir standart denetim veya DHTML denetimi oluşturduğunuzda, sihirbaz sizin sınıfınızdan otomatik olarak derleyeceği `CComControlBase`.

Bir denetim oluşturma hakkında daha fazla bilgi için bkz. [ATL öğretici](../../atl/active-template-library-atl-tutorial.md). ATL projesi Sihirbazı hakkında daha fazla bilgi için bkz [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="appearancetype"></a>  CComControlBase::AppearanceType

Geçersiz kılmak, `m_nAppearance` stok özellik türü olmayan **kısa**.

```
typedef short AppearanceType;
```

### <a name="remarks"></a>Açıklamalar

ATL Denetim Sihirbazı'nı ekler `m_nAppearance` stok özelliği kısa türü. Geçersiz kılma `AppearanceType` farklı bir veri türü kullanır.

##  <a name="ccomcontrolbase"></a>  CComControlBase::CComControlBase

Oluşturucu.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Denetimle ilişkili penceresine tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Denetim boyutunun 5080 X 5080 HIMETRIC birimleri başlatır (2 X"2") ve başlatır `CComControlBase` veri üyesi değerler NULL ya da FALSE.

##  <a name="dtor"></a>  CComControlBase:: ~ CComControlBase

Yıkıcı.

```
~CComControlBase();
```

### <a name="remarks"></a>Açıklamalar

Denetim pencereli, ise `~CComControlBase` çağırarak yok eder [DestroyWindow](/windows/desktop/api/winuser/nf-winuser-destroywindow).

##  <a name="controlqueryinterface"></a>  CComControlBase::ControlQueryInterface

İstenen arabirim için bir işaretçi alır.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
İstenen arabiriminin GUID'si.

*ppv*<br/>
Tarafından tanımlanan bir arabirim işaretçisi için bir işaretçi *IID*, veya arabirim bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

yalnızca COM eşleme tablosunda arabirimleri işler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

##  <a name="doesverbactivate"></a>  CComControlBase::DoesVerbActivate

Denetleyen *iVerb* tarafından kullanılan parametre `IOleObjectImpl::DoVerb` denetimin kullanıcı arabirimini etkinleştirir ya da (*iVerb* OLEIVERB_UIACTIVATE eşittir), kullanıcı çift tıkladığında gerçekleştirilecek eylemi tanımlar Denetim (*iVerb* OLEIVERB_PRIMARY eşittir), denetim (*iVerb* OLEIVERB_SHOW eşittir), veya denetim etkinleştirir (*iVerb* OLEIVERB eşittir _INPLACEACTIVATE).

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*iVerb*<br/>
Tarafından gerçekleştirilecek eylemi belirten değer `DoVerb`.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür *iVerb* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW veya OLEIVERB_INPLACEACTIVATE eşittir; Aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kendi etkinleştirme fiil tanımlamak için bu yöntemi geçersiz kılabilirsiniz.

##  <a name="doesverbuiactivate"></a>  CComControlBase::DoesVerbUIActivate

Denetleyen *iVerb* tarafından kullanılan parametre `IOleObjectImpl::DoVerb` etkinleştirmek kullanıcı arabirimi denetim neden olur ve true değer döndürür.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*iVerb*<br/>
Tarafından gerçekleştirilecek eylemi belirten değer `DoVerb`.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür *iVerb* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW veya OLEIVERB_INPLACEACTIVATE eşittir. Aksi takdirde yöntem FALSE döndürür.

##  <a name="doverbproperties"></a>  CComControlBase::DoVerbProperties

Denetimin özellik sayfalarını görüntüler.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
Ayrılmış.

*hwndParent*<br/>
Denetimi içeren pencere tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

##  <a name="fireviewchange"></a>  CComControlBase::FireViewChange

Denetim yeniden çizmek için kapsayıcı bildirmek için bu yöntemi çağırın veya denetimin görünüm değiştirildi kayıtlı öneri havuzlarını bildirir.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetim etkin olursa (denetim sınıfı veri üyesi [CComControlBase::m_bInPlaceActive](#m_binplaceactive) TRUE ise), tüm denetim yeniden çizmek istediğiniz kapsayıcı bildirir. Denetimin etkin değilse, denetimin kayıtlı bildirir havuzlarını bildirmek (denetim sınıfı veri üyesi aracılığıyla [CComControlBase::m_spAdviseSink](#m_spadvisesink)), denetimin görünüm değiştirildi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

##  <a name="getambientappearance"></a>  CComControlBase::GetAmbientAppearance

DISPID_AMBIENT_APPEARANCE, denetlemek için bu ayarı geçerli görünümünü alır: düz ve 3B 1 için 0.

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>Parametreler

*nAppearance*<br/>
Özellik DISPID_AMBIENT_APPEARANCE.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

##  <a name="getambientautoclip"></a>  CComControlBase::GetAmbientAutoClip

DISPID_AMBIENT_AUTOCLIP, kapsayıcı denetimi görüntüleme alanının otomatik kırpma destekleyip desteklemediğini belirten bir bayrak alır.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>Parametreler

*bAutoClip*<br/>
Özellik DISPID_AMBIENT_AUTOCLIP.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientbackcolor"></a>  CComControlBase::GetAmbientBackColor

DISPID_AMBIENT_BACKCOLOR, kapsayıcı tarafından tanımlanan tüm denetimler için ortam arka plan rengini alır.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>Parametreler

*Arka plan rengi*<br/>
Özellik DISPID_AMBIENT_BACKCOLOR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientcharset"></a>  CComControlBase::GetAmbientCharSet

DISPID_AMBIENT_CHARSET, ortam karakter kapsayıcı tarafından tanımlanan tüm denetimler için kümesini alır.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>Parametreler

*bstrCharSet*<br/>
Özellik DISPID_AMBIENT_CHARSET.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="getambientcodepage"></a>  CComControlBase::GetAmbientCodePage

DISPID_AMBIENT_CODEPAGE, kapsayıcı tarafından tanımlanan tüm denetimler için ortam kod sayfası alır.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>Parametreler

*ulCodePage*<br/>
Özellik DISPID_AMBIENT_CODEPAGE.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="getambientdisplayasdefault"></a>  CComControlBase::GetAmbientDisplayAsDefault

DISPID_AMBIENT_DISPLAYASDEFAULT, kapsayıcı denetimi bu sitedeki varsayılan düğme olarak işaretlenmiş ve bu nedenle bir düğme denetimi kendisini bir kalın kenarlığa sahip çizip TRUE ise bir bayrak alır.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*bDisplayAsDefault*<br/>
Özellik DISPID_AMBIENT_DISPLAYASDEFAULT.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientdisplayname"></a>  CComControlBase::GetAmbientDisplayName

DISPID_AMBIENT_DISPLAYNAME, kapsayıcı denetimi tarafından sağlanan adını alır.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>Parametreler

*bstrDisplayName*<br/>
Özellik DISPID_AMBIENT_DISPLAYNAME.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientfont"></a>  CComControlBase::GetAmbientFont

Alır bir işaretçi kapsayıcıya ortam `IFont` arabirimi.

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*<br/>
Kapsayıcı için bir işaretçi ortam [IFont](/windows/desktop/api/ocidl/nn-ocidl-ifont) arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Özellik NULL ise, işaretçi NULL olur. Çağıran, işaretçi NULL değilse, işaretçi serbest bırakmalısınız.

##  <a name="getambientfontdisp"></a>  CComControlBase::GetAmbientFontDisp

Alır bir işaretçi kapsayıcıya ortam `IFontDisp` gönderme arabirimi.

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*<br/>
Kapsayıcı için bir işaretçi ortam [IFontDisp](https://msdn.microsoft.com/library/windows/desktop/ms692695) gönderme arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Özellik NULL ise, işaretçi NULL olur. Çağıran, işaretçi NULL değilse, işaretçi serbest bırakmalısınız.

##  <a name="getambientforecolor"></a>  CComControlBase::GetAmbientForeColor

DISPID_AMBIENT_FORECOLOR, kapsayıcı tarafından tanımlanan tüm denetimler için ortam ön plan rengini alır.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>Parametreler

*ForeColor*<br/>
Özellik DISPID_AMBIENT_FORECOLOR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientlocaleid"></a>  CComControlBase::GetAmbientLocaleID

DISPID_AMBIENT_LOCALEID, kapsayıcı tarafından kullanılan dil tanımlayıcısını alır.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Özellik DISPID_AMBIENT_LOCALEID.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetim bu tanımlayıcı, farklı diller için kullanıcı arabirimi uyum sağlamak için kullanabilirsiniz.

##  <a name="getambientmessagereflect"></a>  CComControlBase::GetAmbientMessageReflect

DISPID_AMBIENT_MESSAGEREFLECT, kapsayıcı pencere iletilerini almak isteyip istemediğini belirten bir bayrak alır (gibi `WM_DRAWITEM`) olaylar olarak.

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>Parametreler

*bMessageReflect*<br/>
Özellik DISPID_AMBIENT_MESSAGEREFLECT.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientpalette"></a>  CComControlBase::GetAmbientPalette

Kapsayıcının HPALETTE erişmek için kullanılan DISPID_AMBIENT_PALETTE, alır.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>Parametreler

*hPalette*<br/>
Özellik DISPID_AMBIENT_PALETTE.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientproperty"></a>  CComControlBase::GetAmbientProperty

Belirtilen kapsayıcı özelliği alır *DISPID*.

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
Alınacak kapsayıcı özellik tanımlayıcısı.

*var*<br/>
Özelliği almak için değişken.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

ATL yardımcı işlevleri belirli özelliklerini almak için bir dizi sağlanan [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Kullanılabilir uygun yöntem ise kullanın `GetAmbientProperty`.

##  <a name="getambientrighttoleft"></a>  CComControlBase::GetAmbientRightToLeft

DISPID_AMBIENT_RIGHTTOLEFT, içeriği kapsayıcı tarafından görüntülenen yönünü alır.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>Parametreler

*bRightToLeft*<br/>
Özellik DISPID_AMBIENT_RIGHTTOLEFT. Sağdan sola görüntüleniyorsa, içerik sağdan sola FALSE görüntüleniyorsa TRUE olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="getambientscaleunits"></a>  CComControlBase::GetAmbientScaleUnits

DISPID_AMBIENT_SCALEUNITS, görüntüler etiketleme kapsayıcının ortam birim (inç veya gibi inç) alır.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>Parametreler

*bstrScaleUnits*<br/>
Özellik DISPID_AMBIENT_SCALEUNITS.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientshowgrabhandles"></a>  CComControlBase::GetAmbientShowGrabHandles

DISPID_AMBIENT_SHOWGRABHANDLES, kapsayıcı tutamaçların kendisi için etkin olduğunda gösterilecek denetim izin verip vermediğini belirten bir bayrak alır.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>Parametreler

*bShowGrabHandles*<br/>
Özellik DISPID_AMBIENT_SHOWGRABHANDLES.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientshowhatching"></a>  CComControlBase::GetAmbientShowHatching

DISPID_AMBIENT_SHOWHATCHING, kapsayıcı denetimin kullanıcı arabirimi etkin olduğunda, kendisini taranmış bir desenle görüntülemek üzere denetimi izin verip vermediğini belirten bir bayrak alır.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>Parametreler

*bShowHatching*<br/>
Özellik DISPID_AMBIENT_SHOWHATCHING.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambientsupportsmnemonics"></a>  CComControlBase::GetAmbientSupportsMnemonics

DISPID_AMBIENT_SUPPORTSMNEMONICS, kapsayıcı klavye anımsatıcıları destekleyip desteklemediğini belirten bir bayrak alır.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>Parametreler

*bSupportsMnemonics*<br/>
Özellik DISPID_AMBIENT_SUPPORTSMNEMONICS.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambienttextalign"></a>  CComControlBase::GetAmbientTextAlign

DISPID_AMBIENT_TEXTALIGN, kapsayıcı tarafından tercih edilen metin hizalamasını alır: Genel hizalama (sağ metin numaraları sol) için 0, sola hizalama için 1, 2 Ortala ve sağa hizalama için 3.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>Parametreler

*nTextAlign*<br/>
Özellik DISPID_AMBIENT_TEXTALIGN.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getambienttoptobottom"></a>  CComControlBase::GetAmbientTopToBottom

DISPID_AMBIENT_TOPTOBOTTOM, içeriği kapsayıcı tarafından görüntülenen yönünü alır.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>Parametreler

*bTopToBottom*<br/>
Özellik DISPID_AMBIENT_TOPTOBOTTOM. Metin görüntüleniyorsa TRUE olarak ayarlayın. yukarıdan aşağıya doğru bu ise FALSE alt dön görüntülenir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="getambientuidead"></a>  CComControlBase::GetAmbientUIDead

DISPID_AMBIENT_UIDEAD, kapsayıcı eylemlerine kullanıcı arabirimi yanıt verme denetimi isteyip istemediğini gösteren bir bayrak alır.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>Parametreler

*bUIDead*<br/>
Özellik DISPID_AMBIENT_UIDEAD.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

TRUE ise denetimi yanıt. Bu bayrak DISPID_AMBIENT_USERMODE bayrağı bağımsız olarak geçerlidir. Bkz: [CComControlBase::GetAmbientUserMode](#getambientusermode).

##  <a name="getambientusermode"></a>  CComControlBase::GetAmbientUserMode

DISPID_AMBIENT_USERMODE, kapsayıcı çalıştırma modu (TRUE) veya tasarım modu (FALSE) olup olmadığını belirten bir bayrak alır.

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>Parametreler

*bUserMode*<br/>
Özellik DISPID_AMBIENT_USERMODE.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

##  <a name="getdirty"></a>  CComControlBase::GetDirty

Veri üyesinin değerini döndürür `m_bRequiresSave`.

```
BOOL GetDirty();
```

### <a name="return-value"></a>Dönüş Değeri

Veri üyesinin değerini döndürür [m_bRequiresSave](#m_brequiressave).

### <a name="remarks"></a>Açıklamalar

Bu değer kullanılarak ayarlanan [CComControlBase::SetDirty](#setdirty).

##  <a name="getzoominfo"></a>  CComControlBase::GetZoomInfo

X ve y alır pay ve yakınlaştırma faktörünü, payda değerleri için bir denetimi etkinleştirilmiş için yerinde düzenleme.

```
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Yakınlaştırma faktörünü 's pay ve paydası barındıracak yapısı. Daha fazla bilgi için [atl_drawınfo](../../atl/reference/atl-drawinfo-structure.md).

### <a name="remarks"></a>Açıklamalar

Yakınlaştırma faktörünü denetimin doğal geçerli kapsamı boyutuna oranı ' dir.

##  <a name="inplaceactivate"></a>  CComControlBase::InPlaceActivate

İnovasyonunuz ne olursa olsun fiil durum için devre dışı durumundan geçiş denetimi neden *iVerb* gösterir.

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>Parametreler

*iVerb*<br/>
Tarafından gerçekleştirilecek eylemi belirten değer [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb).

*prcPosRect*<br/>
Yerinde denetimin konumunu işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Etkinleştirme tamamlanmadan önce bu yöntem, denetimin istemci bir siteye sahip, denetimin ne kadarının görünür olup olmadığını denetler ve ana penceresinde denetimin konumunu alır denetler. Denetimi etkinleştirildikten sonra bu yöntem denetimin kullanıcı arabirimini etkinleştirir ve denetimi görünür hale getirmek için kapsayıcı söyler.

Bu yöntem ayrıca alır bir `IOleInPlaceSite`, `IOleInPlaceSiteEx`, veya `IOleInPlaceSiteWindowless` denetimi için arabirim işaretçisi ve denetim sınıfın veri üyesi depolar [CComControlBase::m_spInPlaceSite](#m_spinplacesite). Denetim sınıf veri üyeleri [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)ve [ CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) true olarak uygun şekilde ayarlanır.

##  <a name="internalgetsite"></a>  CComControlBase::InternalGetSite

Denetim site tanımlanan arabirim işaretçisi için sorgulamak için bu yöntemi çağırın.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
İçinde döndürülmesi gereken arabirim işaretçisi Laboratuvardaki *ppUnkSite*.

*ppUnkSite*<br/>
İçinde istenen arabirim işaretçisi alır işaretçi değişkeninin adresi *riid*.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Site içinde istenen arabirimi destekliyorsa *riid*, yoluyla döndürülen işaretçiye *ppUnkSite*. Aksi takdirde, *ppUnkSite* NULL olarak ayarlandı.

##  <a name="m_bautosize"></a>  CComControlBase::m_bAutoSize

Denetim, diğer herhangi bir boyutta olamaz belirten bayrak.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>Açıklamalar

Bu bayrağı tarafından denetlenir `IOleObjectImpl::SetExtent` ve TRUE ise E_FAIL döndürmek işlev neden olur.

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

Eklerseniz **Otomatik Boyutlandır** seçeneğini [stok özellikleri](../../atl/reference/stock-properties-atl-control-wizard.md) sekmesi ATL denetimi Sihirbazı, sihirbaz otomatik olarak bu veri üyesi denetim sınıfınıza oluşturur, put oluşturur ve get yöntemleri bir özellik için ve destekleyen [Ipropertynotifysink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) kapsayıcı özelliği değiştiğinde otomatik olarak bilgilendirme.

##  <a name="m_bdrawfromnatural"></a>  CComControlBase::m_bDrawFromNatural

Olduğunu belirten bayrağı `IDataObjectImpl::GetData` ve `CComControlBase::GetZoomInfo` denetim boyutundan ayarlamalısınız `m_sizeNatural` yerine `m_sizeExtent`.

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_bdrawgetdatainhimetric"></a>  CComControlBase::m_bDrawGetDataInHimetric

Olduğunu belirten bayrağı `IDataObjectImpl::GetData` HIMETRIC birimleri ve değil piksel çizerken kullanmanız gerekir.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>Açıklamalar

Her mantıksal HIMETRIC Birim 0,01 milimetre ' dir.

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_binplaceactive"></a>  CComControlBase::m_bInPlaceActive

Denetimin yerinde etkin olup olmadığını belirten bayrak.

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>Açıklamalar

Başka bir deyişle, denetimin görünür olup ve varsa, pencerenin görünür, ancak kendi menüleri ve araç çubuklarını etkin olmayabilir. `m_bUIActive` Bayrağı gibi menüleri, denetim kullanıcı arabirimi etkin olup da gösterir.

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_binplacesiteex"></a>  CComControlBase::m_bInPlaceSiteEx

Kapsayıcı destekler belirten bayrak `IOleInPlaceSiteEx` arabirimi ve OCX96 kontrol penceresiz ve titreşimsiz denetimleri gibi özellikleri.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

Veri üyesi `m_spInPlaceSite` işaret eden bir [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), veya [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) değerine göre arabirimi `m_bWndLess` ve `m_bInPlaceSiteEx` bayrakları. (Veri üyesi `m_bNegotiatedWnd` TRUE olmalıdır için `m_spInPlaceSite` geçerli olması için işaretçi.)

Varsa `m_bWndLess` yanlış ve `m_bInPlaceSiteEx` TRUE ise `m_spInPlaceSite` olduğu bir `IOleInPlaceSiteEx` arabirim işaretçisi. Bkz: [m_spInPlaceSite](#m_spinplacesite) için bu üç veri üyeleri arasındaki ilişkiyi gösteren bir tablo.

##  <a name="m_bnegotiatedwnd"></a>  CComControlBase::m_bNegotiatedWnd

Denetim (örneğin, titreşimsiz ve penceresiz denetimleri) OCX96 denetim özellikleri için desteği hakkında daha fazla kapsayıcı ile olup olmadığı anlaşılan ve denetim pencereli veya penceresiz olup olmadığını belirten bayrak.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

`m_bNegotiatedWnd` Bayrağı TRUE olması için `m_spInPlaceSite` geçerli olması için işaretçi.

##  <a name="m_brecomposeonresize"></a>  CComControlBase::m_bRecomposeOnResize

Denetim kapsayıcı denetimin görüntüleme boyutu değiştiğinde, sunu yeniden oluşturmak istiyor belirten bayrak.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

Bu bayrağı tarafından denetlenir [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) ve TRUE ise `SetExtent` değişiklikleri görüntüleme kapsayıcı bildirir. Bu bayrağı ayarlarsanız, OLEMISC_RECOMPOSEONRESIZE bit [OLEMISC](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc) numaralandırma ayarlanmalıdır.

##  <a name="m_brequiressave"></a>  CComControlBase::m_bRequiresSave

Denetimi son kez kaydedildiğinden beri değiştirildi belirten bayrak.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>Açıklamalar

Değerini `m_bRequiresSave` ayarlanabilir [CComControlBase::SetDirty](#setdirty) ve ile alınan [CComControlBase::GetDirty](#getdirty).

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_bresizenatural"></a>  CComControlBase::m_bResizeNatural

Denetim istediği doğal kapsamı (ölçeklendirilmemiş fiziksel boyutuna) yeniden boyutlandırmak belirten bayrak kapsayıcı denetimin görüntüleme boyutu değiştiğinde.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>Açıklamalar

Bu bayrağı tarafından denetlenir `IOleObjectImpl::SetExtent` ve TRUE ise, boyutu yöntemlere geçirilen `SetExtent` atandığı `m_sizeNatural`.

Boyutu yöntemlere geçirilen `SetExtent` her zaman atanmış `m_sizeExtent`değerini bakılmaksızın `m_bResizeNatural`.

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_buiactive"></a>  CComControlBase::m_bUIActive

Denetimin menüleri ve araç çubukları gibi kullanıcı arabirimi belirten bayrağı etkin değil.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>Açıklamalar

`m_bInPlaceActive` Bayrağı denetim etkin, ancak değil, olduğunu gösterir, kullanıcı arabirimi etkindir.

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_busingwindowrgn"></a>  CComControlBase::m_bUsingWindowRgn

Denetimin, kapsayıcı tarafından sağlanan pencere bölgesi kullanarak belirten bayrak.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_bwasoncewindowless"></a>  CComControlBase::m_bWasOnceWindowless

Denetim penceresiz, alındı ancak olabilir veya artık penceresiz olmayabilir belirten bayrak.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_bwindowonly"></a>  CComControlBase::m_bWindowOnly

Kapsayıcı penceresiz denetimleri destekler olsa bile denetim pencereli, olmalıdır belirten bayrak.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_bwndless"></a>  CComControlBase::m_bWndLess

Denetimin penceresiz olup olmadığını belirten bayrak.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

Veri üyesi `m_spInPlaceSite` işaret eden bir [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), veya [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) değerine göre arabirimi `m_bWndLess` ve [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) bayrakları. (Veri üyesi [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) TRUE olmalıdır için [CComControlBase::m_spInPlaceSite](#m_spinplacesite) geçerli olması için işaretçi.)

Varsa `m_bWndLess` TRUE ise `m_spInPlaceSite` olduğu bir `IOleInPlaceSiteWindowless` arabirim işaretçisi. Bkz: [CComControlBase::m_spInPlaceSite](#m_spinplacesite) tam bu veri üyeleri arasındaki ilişkiyi gösteren bir tablo için.

##  <a name="m_hwndcd"></a>  CComControlBase::m_hWndCD

Denetimle ilişkili pencere tanıtıcısı başvuru içeriyor.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_nfreezeevents"></a>  CComControlBase::m_nFreezeEvents

Kaç kez sayısını kapsayıcı (olayları kabul reddetti) olayları (olayları kabulü) olayların müdahalede bulunan bir çözme dondurulmuş.

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_rcpos"></a>  CComControlBase::m_rcPos

Piksel cinsinden denetimin kapsayıcısının koordinatlarında belirtilen konumu.

```
RECT m_rcPos;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_sizeextent"></a>  CComControlBase::m_sizeExtent

Uzantı denetimin belirli bir ekran için HIMETRIC birimleri (her birim 0,01 milimetre'dir).

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

Bu boyut tarafından görüntülenmesini ölçeklendirilir. Fiziksel boyut denetimin belirtilen `m_sizeNatural` veri üyesi ve sabittir.

Genel işlev piksel boyutunu dönüştürebilirsiniz [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).

##  <a name="m_sizenatural"></a>  CComControlBase::m_sizeNatural

(Her birim 0,01 milimetre'dir) HIMETRIC birimleri denetiminde fiziksel boyutu.

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

Bu boyut boyutu hata düzeltilene `m_sizeExtent` görüntü ölçeklendirilir.

Genel işlev piksel boyutunu dönüştürebilirsiniz [AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel).

##  <a name="m_spadvisesink"></a>  CComControlBase::m_spAdviseSink

Kapsayıcı danışmanlık bağlantısında doğrudan bir işaretçiye (kapsayıcının [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink)).

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_spambientdispatch"></a>  CComControlBase::m_spAmbientDispatch

A `CComDispatchDriver` almak ve bir nesnenin özellikleri aracılığıyla ayarlamanıza olanak sağlayan bir nesne bir `IDispatch` işaretçi.

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_spclientsite"></a>  CComControlBase::m_spClientSite

Denetimin istemci site kapsayıcı içindeki bir işaretçi.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

##  <a name="m_spdataadviseholder"></a>  CComControlBase::m_spDataAdviseHolder

Veri nesneleri arasında danışmanlık bağlantılar basılı tutun ve havuzlarını bildirmek için standart araçları sağlar.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

Veri nesnesinde veri aktarabilir ve uygulayan bir denetimdir [IDataObject](/windows/desktop/api/objidl/nn-objidl-idataobject), verilerin biçimi ve aktarım Orta yöntemleri belirtin.

Arabirim `m_spDataAdviseHolder` uygulayan [IDataObject::DAdvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dadvise) ve [IDataObject::DUnadvise](/windows/desktop/api/objidl/nf-objidl-idataobject-dunadvise) oluşturmak ve kapsayıcıya danışmanlık bağlantıları silme yöntemleri. Denetimin kapsayıcı bir öneri havuz destekleyerek uygulamalıdır [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) arabirimi.

##  <a name="m_spinplacesite"></a>  CComControlBase::m_spInPlaceSite

Kapsayıcının işaretçisi [IOleInPlaceSite](/windows/desktop/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesiteex), veya [IOleInPlaceSiteWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arabirim işaretçisi.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

`m_spInPlaceSite` İşaretçi geçerli yalnızca [m_bNegotiatedWnd](#m_bnegotiatedwnd) bayrağı TRUE olduğu.

Aşağıdaki tabloda nasıl `m_spInPlaceSite` işaretçi türüne bağlı olarak [m_bWndLess](#m_bwndless) ve [m_bInPlaceSiteEx](#m_binplacesiteex) veri üyesi bayraklar:

|m_spInPlaceSite türü|m_bWndLess değeri|m_bInPlaceSiteEx değeri|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|TRUE|TRUE veya FALSE|
|`IOleInPlaceSiteEx`|FALSE|TRUE|
|`IOleInPlaceSite`|FALSE|FALSE|

##  <a name="m_spoleadviseholder"></a>  CComControlBase::m_spOleAdviseHolder

Standart bir danışmanlık bağlantılarını tutmak için bir yöntem uygulamasını sağlar.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu veri üyesi denetim sınıfınıza içinde kullanmak için bu veri üyesi olarak denetim sınıfınıza bildirmeniz gerekir. Denetim sınıfınıza temel sınıfta bir birleşim içinde bildirildiği için bu veri üyesi temel sınıftan devralmaz.

Arabirim `m_spOleAdviseHolder` uygulayan [IOleObject::Advise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-advise) ve [IOleObject::Unadvise](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-unadvise) oluşturmak ve kapsayıcıya danışmanlık bağlantıları silme yöntemleri. Denetimin kapsayıcı bir öneri havuz destekleyerek uygulamalıdır [IAdviseSink](/windows/desktop/api/objidl/nn-objidl-iadvisesink) arabirimi.

##  <a name="ondraw"></a>  CComControlBase::OnDraw

Denetiminizi çizmek için bu yöntemi yok sayın.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Bir başvuru [atl_drawınfo](../../atl/reference/atl-drawinfo-structure.md) denetim sınırları çizim en boy gibi çizim bilgileri içeren yapısı ve çizim veya optimize edilmiştir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Varsayılan `OnDraw` siler veya cihaz bağlamı geri yükler veya kümesinde bayrakları bağlı hiçbir şey yapmaz [CComControlBase::OnDrawAdvanced](#ondrawadvanced).

Bir `OnDraw` ATL denetimi Sihirbazı'yla denetiminizi oluşturduğunuzda yöntemi denetim sınıfınıza otomatik olarak eklenir. Sihirbazın varsayılan `OnDraw` "ATL 8.0" etiketli bir dikdörtgen çizer.

### <a name="example"></a>Örnek

Örneğin bakın [CComControlBase::GetAmbientAppearance](#getambientappearance).

##  <a name="ondrawadvanced"></a>  CComControlBase::OnDrawAdvanced

Varsayılan `OnDrawAdvanced` normalleştirilmiş bir cihaz bağlamı çizim için hazırlar, ardından Denetim sınıfınızın çağırır `OnDraw` yöntemi.

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Bir başvuru [atl_drawınfo](../../atl/reference/atl-drawinfo-structure.md) denetim sınırları çizim en boy gibi çizim bilgileri içeren yapısı ve çizim veya optimize edilmiştir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı tarafından geçirilen cihaz bağlamı kabul etmek istiyorsanız bu yöntemi yok sayın.

Bkz: [CComControlBase::OnDraw](#ondraw) daha fazla ayrıntı için.

##  <a name="onkillfocus"></a>  CComControlBase::OnKillFocus

Denetim yerinde etkin ve geçerli denetim sitenin sonra kapsayıcı denetimi odağını kaybetmiş bildirir denetler.

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
Ayrılmış.

*wParam*<br/>
Ayrılmış.

*lParam*<br/>
Ayrılmış.

*bHandled*<br/>
Pencere iletisi başarılı bir şekilde işleyip işlemediğini gösteren bayrak. Varsayılan değer false'tur.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

##  <a name="onmouseactivate"></a>  CComControlBase::OnMouseActivate

UI kullanıcı modunda ve ardından Denetim etkinleştirir denetler.

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
Ayrılmış.

*wParam*<br/>
Ayrılmış.

*lParam*<br/>
Ayrılmış.

*bHandled*<br/>
Pencere iletisi başarılı bir şekilde işleyip işlemediğini gösteren bayrak. Varsayılan değer false'tur.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

##  <a name="onpaint"></a>  CComControlBase::OnPaint

Boyama için kapsayıcı hazırlar, denetimin istemci alanı alır ve ardından Denetim sınıfın çağırır `OnDrawAdvanced` yöntemi.

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
Ayrılmış.

*wParam*<br/>
Mevcut bir HDC.

*lParam*<br/>
Ayrılmış.

*lResult*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Her zaman sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

Varsa *wParam* NULL değil `OnPaint` geçerli HDC içerir ve yerine kullandığı varsayılır [CComControlBase::m_hWndCD](#m_hwndcd).

##  <a name="onsetfocus"></a>  CComControlBase::OnSetFocus

Denetim yerinde etkin ve geçerli denetim sitenin sonra kapsayıcı denetimi bildirir denetimleri odak kazanılan.

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
Ayrılmış.

*wParam*<br/>
Ayrılmış.

*lParam*<br/>
Ayrılmış.

*bHandled*<br/>
Pencere iletisi başarılı bir şekilde işleyip işlemediğini gösteren bayrak. Varsayılan değer false'tur.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim odağı aldı, kapsayıcıya bir bildirim gönderir.

##  <a name="pretranslateaccelerator"></a>  CComControlBase::PreTranslateAccelerator

Kendi klavye Hızlandırıcı işleyicileri sağlamak için bu yöntemi yok sayın.

```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
Ayrılmış.

*hRet*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak false değerini döndürür.

##  <a name="sendonclose"></a>  CComControlBase::SendOnClose

Denetim kapatıldı öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirir.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim, danışmanlık havuzlarını kapattı bir bildirim gönderir.

##  <a name="sendondatachange"></a>  CComControlBase::SendOnDataChange

Denetim verilerinin değişti öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirir.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>Parametreler

*advf*<br/>
Öneri belirten bayrakları nasıl çağrısı [IAdviseSink::OnDataChange](/windows/desktop/api/objidl/nf-objidl-iadvisesink-ondatachange) yapılır. Değerler: gelen [ADVF](/windows/desktop/api/objidl/ne-objidl-tagadvf) sabit listesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="sendonrename"></a>  CComControlBase::SendOnRename

Denetim yeni bir ad olduğunu öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirir.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>Parametreler

*PMK*<br/>
Yeni takma denetim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim için bilinen ad değişen bir bildirim gönderir.

##  <a name="sendonsave"></a>  CComControlBase::SendOnSave

Denetim kaydedildi öneri sahibi ile kayıtlı tüm danışmanlık havuzlarını bildirir.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Denetim verilerini yeni kaydettiğiniz bir bildirim gönderir.

##  <a name="sendonviewchange"></a>  CComControlBase::SendOnViewChange

Denetimin görünüm değiştirildi danışmanlık havuzlarını tüm kayıtlı bildirir.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>Parametreler

*dwAspect*<br/>
En boy veya denetimin görünümü.

*Dizin*<br/>
Görünümünün değişmiş. Yalnızca -1, geçerli değil.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

`SendOnViewChange` çağrıları [IAdviseSink::OnViewChange](/windows/desktop/api/objidl/nf-objidl-iadvisesink-onviewchange). Yalnızca değerini *dizin* ilgi tüm görünüm gösterir -1 olan şu anda desteklenmiyor.

##  <a name="setcontrolfocus"></a>  CComControlBase::SetControlFocus

Klavye odağı ya da denetiminden kaldırır veya ayarlar.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>Parametreler

*bGrab*<br/>
TRUE ise, klavye odağı arama denetimi için ayarlar. Odaklanmış sağlanan yanlışsa, klavye odağı arama denetiminden kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Odak denetimi başarıyla aldığında, TRUE döndürür; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Pencereli denetimin, Windows API işlevi için [SetFocus](https://msdn.microsoft.com/library/windows/desktop/ms646312) çağrılır. Penceresiz denetime için [IOleInPlaceSiteWindowless::SetFocus](/windows/desktop/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) çağrılır. Bu çağrı aracılığıyla penceresiz denetime klavye odağa gelir ve pencere iletilere yanıt verebilir.

##  <a name="setdirty"></a>  CComControlBase::SetDirty

Veri üyesi ayarlar `m_bRequiresSave` değerine *bDirty*.

```
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*bDirty*<br/>
Veri üyesinin değerini [CComControlBase::m_bRequiresSave](#m_brequiressave).

### <a name="remarks"></a>Açıklamalar

`SetDirty(TRUE)` denetimi son kez kaydedildiğinden beri değiştirildi bayrağı için çağrılmalıdır. Değerini `m_bRequiresSave` alınan [CComControlBase::GetDirty](#getdirty).

## <a name="see-also"></a>Ayrıca Bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
