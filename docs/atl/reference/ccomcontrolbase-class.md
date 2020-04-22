---
title: CcomControlBase Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
ms.openlocfilehash: 15cfa205337248181f02e6a1218d49e75bda58e6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748116"
---
# <a name="ccomcontrolbase-class"></a>CcomControlBase Sınıfı

Bu sınıf, ATL denetimleri oluşturmak ve yönetmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CcomControlBase::appearancetype](#appearancetype)|Stok özelliğiniz `m_nAppearance` **kısa**bir tür de değilse geçersiz kılın.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomControlBase::ccomcontrolbase](#ccomcontrolbase)|Oluşturucu.|
|[CcomControlBase::~CcomControlBase](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomControlBase::ControlQueryInterface](#controlqueryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|Kullanılan `IOleObjectImpl::DoVerb` *iVerb* parametresinin denetimin kullanıcı arabirimini etkinleştirdiğini *(iFiil* eşittir OLEIVERB_UIACTIVATE), kullanıcı denetimi çift tıklattığında *(iFiil* eşittir OLEIVERB_PRIMARY), denetimi *(iFiil* eşittir OLEIVERB_SHOW) veya denetimi etkinleştirdiğinde *(iFiil* eşittir OLEIVERB_INPLACEACTIVATE) eylemi tanımlar.|
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|Kullanılan `IOleObjectImpl::DoVerb` *iVerb* parametresinin denetimin kullanıcı arabiriminin etkinleştirilmesine neden olduğunu ve TRUE'yu döndürür.|
|[CComControlBase::DoVerbProperties](#doverbproperties)|Denetimin özellik sayfalarını görüntüler.|
|[CcomControlBase::FireViewChange](#fireviewchange)|Denetimi yeniden çizmesini konteynere bildirmek için bu yöntemi arayın veya kayıtlı tavsiye lavabolarına denetimin görünümünün değiştiğini bildirin.|
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|DISPID_AMBIENT_APPEARANCE alır, denetim için geçerli görünüm ayarı: düz için 0 ve 3D için 1.|
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|Kapsayıcının denetim görüntüleme alanının otomatik kırpmasını destekleyip desteklemediğini belirten bir bayrak olan DISPID_AMBIENT_AUTOCLIP alır.|
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|Kapsayıcı tarafından tanımlanan tüm denetimler için ortam arka plan rengi olan DISPID_AMBIENT_BACKCOLOR alır.|
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|Kapsayıcı tarafından tanımlanan tüm denetimler için ortam karakteri kümesi olan DISPID_AMBIENT_CHARSET alır.|
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|Kapsayıcı tarafından tanımlanan tüm denetimler için ortam karakteri kümesi olan DISPID_AMBIENT_CODEPAGE alır.|
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|Kapsayıcı bu sitedeki denetimi varsayılan düğme olarak işaretlediyse, doğru olan bir bayrak olan DISPID_AMBIENT_DISPLAYASDEFAULT alır ve bu nedenle bir düğme denetimi kendisini daha kalın bir çerçeveyle çizmelidir.|
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|kapsayıcının denetime verdiği ad olan DISPID_AMBIENT_DISPLAYNAME alır.|
|[CComControlBase::GetAmbientFont](#getambientfont)|Kapsayıcının ortam `IFont` arabirimine bir işaretçi alır.|
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|Kapsayıcının ortam `IFontDisp` gönderme arabirimine bir işaretçi alır.|
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|Kapsayıcı tarafından tanımlanan tüm denetimler için ortam ön plan rengi olan DISPID_AMBIENT_FORECOLOR alır.|
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|Kapsayıcı tarafından kullanılan dilin tanımlayıcısı olan DISPID_AMBIENT_LOCALEID alır.|
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|Kapsayıcının olay olarak pencere iletileri (WM_DRAWITEM gibi) almak isteyip istemediğini belirten bir bayrak olan DISPID_AMBIENT_MESSAGEREFLECT alır.|
|[CComControlBase::GetAmbientPalette](#getambientpalette)|Konteynerin HPALETTE'sine erişmek için kullanılan DISPID_AMBIENT_PALETTE alır.|
|[CComControlBase::GetAmbientProperty](#getambientproperty)|*Id*tarafından belirtilen kapsayıcı özelliğini alır.|
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|İçeriğin kapsayıcı tarafından görüntülendiği yön olan DISPID_AMBIENT_RIGHTTOLEFT alır.|
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|Ekranları etiketlemek için kabın ortam birimlerini (inç veya santimetre gibi) DISPID_AMBIENT_SCALEUNITS alır.|
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|Kapsayıcının etkin olduğunda tutamak tutamaçlarını kendisi için görüntülemesine izin verip vermediğine dair bir bayrak olan DISPID_AMBIENT_SHOWGRABHANDLES alır.|
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|DISPID_AMBIENT_SHOWHATCHING alır, kapsayıcının kullanıcı aracı etkin olduğunda denetimin kendisini yumurtadan çıkmış bir desenle görüntülemesine izin verip vermediğine dair bir bayrak.|
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Kapsayıcının klavye mnemonics'i destekleyip desteklemediğini belirten bir bayrak olan DISPID_AMBIENT_SUPPORTSMNEMONICS alır.|
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|kapsayıcı tarafından tercih edilen metin hizalaması DISPID_AMBIENT_TEXTALIGN alır: genel hizalama için 0 (sağ, metin sol), sol hizalama için 1, merkez hizalama için 2 ve sağ hizalama için 3.|
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|İçeriğin kapsayıcı tarafından görüntülendiği yön olan DISPID_AMBIENT_TOPTOBOTTOM alır.|
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|Kapsayıcının denetimin kullanıcı arabirimi eylemlerine yanıt vermek isteyip istemediğini belirten bir bayrak olan DISPID_AMBIENT_UIDEAD alır.|
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|DISPID_AMBIENT_USERMODE alır, kapsayıcının çalışma modunda olup olmadığını belirten bir bayrak (TRUE) veya tasarım modu (FALSE).|
|[CcomControlBase::GetDirty](#getdirty)|Veri üyesinin `m_bRequiresSave`değerini verir.|
|[CcomControlBase::Getzoominfo](#getzoominfo)|Yerinde düzenleme için etkinleştirilen bir denetim için yakınlaştırma faktörünün paydası ve paydasının x ve y değerlerini alır.|
|[CcomControlBase::InplaceActivate](#inplaceactivate)|Denetimin etkin olmayan durumdan *iVerb'deki* fiilin gösterdiği duruma geçişine neden olur.|
|[CcomControlBase::Internalgetsite](#internalgetsite)|Tanımlanan arabirimin işaretçisi için denetim sitesini sorgulamak için bu yöntemi arayın.|
|[CcomControlBase::OnDraw](#ondraw)|Denetiminizi çekmek için bu yöntemi geçersiz kılın.|
|[CcomControlBase::OndrawAdvanced](#ondrawadvanced)|Varsayılan, `OnDrawAdvanced` çizim için normalleştirilmiş bir aygıt bağlamı hazırlar `OnDraw` ve ardından denetim sınıfınızın yöntemini çağırır.|
|[CcomControlBase::OnKillFocus](#onkillfocus)|Denetimin yerinde etkin olup olmadığını ve geçerli bir denetim sitesi olup olmadığını denetler, ardından denetimin odak noktasını kaybettiğini kapsayıcıya bildirir.|
|[CcomControlBase::OnMouseActivate](#onmouseactivate)|Kullanıcı UI'nin kullanıcı modunda olup olmadığını denetler ve denetimi etkinleştirir.|
|[CcomControlBase::Onpaint](#onpaint)|Kapsayıcıyı boyama için hazırlar, denetimin istemci alanını alır, sonra `OnDraw` denetim sınıfının yöntemini arar.|
|[CcomControlBase::OnsetFocus](#onsetfocus)|Denetimin yerinde etkin olup olmadığını ve geçerli bir kontrol bölgesine sahip olup olmadığını denetler, ardından denetimin odaklandığı kapsayıcıyı bildirir.|
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|Kendi klavye hızlandırıcı işleyicilerinizi sağlamak için bu yöntemi geçersiz kılın.|
|[CcomControlBase::SendonClose](#sendonclose)|Tavsiye sahibine kayıtlı tüm danışmanlık lavabolarına denetimin kapatıldığını bildirin.|
|[CcomControlBase::SendonDataChange](#sendondatachange)|Tavsiye sahibine kayıtlı tüm danışma lavabolarını kontrol verilerinin değiştiğini bildirer.|
|[CComControlBase::SendOnRename](#sendonrename)|Tavsiye sahibine kayıtlı tüm danışmanlık lavabolarını, kontrolün yeni bir takma adı olduğunu bildirer.|
|[CcomControlBase::sendonsave](#sendonsave)|Tavsiye sahibine kayıtlı tüm danışmanlık lavabolarını, kontrolün kaydedildiğini bildirer.|
|[CcomControlBase::SendonViewChange](#sendonviewchange)|Tüm kayıtlı danışma lavabolarına denetimin görünümünün değiştiğini belirtir.|
|[CcomControlBase::SetControlFocus](#setcontrolfocus)|Klavye odağının denetime veya denetimden ayarlanır veya kaldırır.|
|[CcomControlBase::SetDirty](#setdirty)|Veri üyesini `m_bRequiresSave` *bDirty'deki*değere ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComControlBase::m_bAutoSize](#m_bautosize)|Denetimi gösteren bayrak başka bir boyut olamaz.|
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|Bunu `IDataObjectImpl::GetData` belirten bayrak `CComControlBase::GetZoomInfo` ve denetim boyutunu `m_sizeNatural` 'dan `m_sizeExtent`değil de.|
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|Çizim yaparken `IDataObjectImpl::GetData` piksel değil, HIMETRIC birimlerinin kullanılması gerektiğini belirten bayrak.|
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|Denetimin etkin olduğunu belirten bayrak.|
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|Kapsayıcıyı gösteren `IOleInPlaceSiteEx` bayrak, arabirimi ve penceresiz ve titreşmesiz denetimler gibi OCX96 denetim özelliklerini destekler.|
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|Denetimin OCX96 denetim özellikleri (titremesiz ve penceresiz denetimler gibi) desteği hakkında kapsayıcıyla görüşüp görüşmediğini ve denetimin pencereli veya penceresiz olup olmadığını belirten bayrak.|
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|Kapsayıcı denetimin ekran boyutunu değiştirdiğinde, denetimi gösteren bayrak sunusunu yeniden oluşturmak ister.|
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|Denetimin en son kaydedildiği günden beri değiştiğini belirten bayrak.|
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|Denetimin, kapsayıcı denetimin ekran boyutunu değiştirdiğinde doğal boyutunu (ölçeklendirilmemiş fiziksel boyutunu) yeniden boyutlandırmak istediğini belirten bayrak.|
|[CComControlBase::m_bUIActive](#m_buiactive)|Denetimin menüler ve araç çubukları gibi kullanıcı arabirimini belirten bayrak etkindir.|
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|Denetimi gösteren bayrak, konteyner tarafından sağlanan pencere bölgesini kullanıyor.|
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|Denetimi belirten bayrak penceresiz olmuştur, ancak şimdi penceresiz olabilir veya olmayabilir.|
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|Kapsayıcı penceresiz denetimleri desteklese bile denetimi gösteren bayrak pencereli olmalıdır.|
|[CComControlBase::m_bWndLess](#m_bwndless)|Denetimi gösteren bayrak penceresiz.|
|[CComControlBase::m_hWndCD](#m_hwndcd)|Denetimle ilişkili pencere tutamacına bir başvuru içerir.|
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|Kapsayıcının olayları kaç kez dondurduğunun sayısı (olayları kabul etmeyi reddeder) olayların çözülmesi (olayların kabulü) olmadan.|
|[CComControlBase::m_rcPos](#m_rcpos)|Denetimpikselkonum, kapsayıcının koordinatlarında ifade.|
|[CComControlBase::m_sizeExtent](#m_sizeextent)|Belirli bir ekran için HIMETRIC birimlerinde (her birim 0,01 milimetredir) kontrolün kapsamı.|
|[CComControlBase::m_sizeNatural](#m_sizenatural)|HIMETRIC birimlerinde kontrolün fiziksel boyutu (her birim 0,01 milimetredir).|
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|Kapsayıcı (kapsayıcının [IAdviseSink)](/windows/win32/api/objidl/nn-objidl-iadvisesink)üzerinde danışma bağlantısı için doğrudan bir işaretçi.|
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|Bir `CComDispatchDriver` işaretçi aracılığıyla kapsayıcının özelliklerini alıp ayarlamanızı sağlayan bir `IDispatch` nesne.|
|[CComControlBase::m_spClientSite](#m_spclientsite)|Denetimin istemci sitesine kapsayıcı içinde bir işaretçi.|
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|Veri nesneleri arasında danışma bağlantıları tutmak ve lavabolara tavsiyelerde bulunmak için standart bir araç sağlar.|
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|Konteynerin [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)bir işaretçi , [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex), veya [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arayüz işaretçisi.|
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|Danışma bağlantılarını tutmanın standart bir uygulamasını sağlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, ATL denetimleri oluşturmak ve yönetmek için yöntemler sağlar. [CComControl Sınıfı'](../../atl/reference/ccomcontrol-class.md) ndan `CComControlBase`türetilmiştir. ATL Denetim Sihirbazı'nı kullanarak bir Standart Denetim veya DHTML denetimi oluşturduğunuzda, sihirbaz sınıfınızı otomatik olarak .'den `CComControlBase`türetecektir.

Denetim oluşturma hakkında daha fazla bilgi için [ATL Tutorial'a](../../atl/active-template-library-atl-tutorial.md)bakın. ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ccomcontrolbaseappearancetype"></a><a name="appearancetype"></a>CcomControlBase::appearancetype

Stok özelliğiniz `m_nAppearance` **kısa**bir tür de değilse geçersiz kılın.

```
typedef short AppearanceType;
```

### <a name="remarks"></a>Açıklamalar

ATL Denetim Sihirbazı, kısa türdeki stok özelliğini ekler. `m_nAppearance` Farklı `AppearanceType` bir veri türü kullanıyorsanız geçersiz kılın.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="ccomcontrolbase"></a>CcomControlBase::ccomcontrolbase

Oluşturucu.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Denetimle ilişkili pencerenin tutamacı.

### <a name="remarks"></a>Açıklamalar

Kontrol boyutunu 5080X5080 HIMETRIC birimlerine (2"X2") başlatlar ve `CComControlBase` veri üye değerlerini NULL veya FALSE olarak aparat eder.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="dtor"></a>CcomControlBase::~CcomControlBase

Yıkıcı.

```
~CComControlBase();
```

### <a name="remarks"></a>Açıklamalar

Denetim pencereliyse, `~CComControlBase` [DestroyWindow'u](/windows/win32/api/winuser/nf-winuser-destroywindow)arayarak yok eder.

## <a name="ccomcontrolbasecontrolqueryinterface"></a><a name="controlqueryinterface"></a>CcomControlBase::ControlQueryInterface

İstenen arabirim için bir işaretçi alır.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
İstenmekte olan arabirimin GUID'i.

*Ppv*<br/>
Arabirim bulunamazsa *iid*veya NULL tarafından tanımlanan arabirim işaretçisine işaretçi.

### <a name="remarks"></a>Açıklamalar

Yalnızca COM harita tablosundaki arabirimleri işler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

## <a name="ccomcontrolbasedoesverbactivate"></a><a name="doesverbactivate"></a>CComControlBase::DoesVerbActivate

Kullanılan `IOleObjectImpl::DoVerb` *iVerb* parametresinin denetimin kullanıcı arabirimini etkinleştirdiğini *(iFiil* eşittir OLEIVERB_UIACTIVATE), kullanıcı denetimi çift tıklattığında *(iFiil* eşittir OLEIVERB_PRIMARY), denetimi *(iFiil* eşittir OLEIVERB_SHOW) veya denetimi etkinleştirdiğinde *(iFiil* eşittir OLEIVERB_INPLACEACTIVATE) eylemi tanımlar.

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*iFiil*<br/>
Tarafından gerçekleştirilecek eylemi gösteren `DoVerb`değer.

### <a name="return-value"></a>Dönüş Değeri

*iFiil* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW veya OLEIVERB_INPLACEACTIVATE eşitse DOĞRU döndürür; aksi takdirde, FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kendi etkinleştirme fiilinizi tanımlamak için bu yöntemi geçersiz kılabilirsiniz.

## <a name="ccomcontrolbasedoesverbuiactivate"></a><a name="doesverbuiactivate"></a>CComControlBase::DoesVerbUIActivate

Kullanılan `IOleObjectImpl::DoVerb` *iVerb* parametresinin denetimin kullanıcı arabiriminin etkinleştirilmesine neden olduğunu ve TRUE'yu döndürür.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*iFiil*<br/>
Tarafından gerçekleştirilecek eylemi gösteren `DoVerb`değer.

### <a name="return-value"></a>Dönüş Değeri

*iVerb* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW veya OLEIVERB_INPLACEACTIVATE eşitse DOĞRU döndürür. Aksi takdirde, yöntem FALSE döndürür.

## <a name="ccomcontrolbasedoverbproperties"></a><a name="doverbproperties"></a>CComControlBase::DoVerbProperties

Denetimin özellik sayfalarını görüntüler.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
Ayrılmış.

*hwndParent*<br/>
Denetimi içeren pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

## <a name="ccomcontrolbasefireviewchange"></a><a name="fireviewchange"></a>CcomControlBase::FireViewChange

Denetimi yeniden çizmesini konteynere bildirmek için bu yöntemi arayın veya kayıtlı tavsiye lavabolarına denetimin görünümünün değiştiğini bildirin.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetim etkinse (denetim sınıfı veri üyesi [CComControlBase::m_bInPlaceActive](#m_binplaceactive) TRUE's), tüm denetimi yeniden çizmek istediğiniz kapsayıcıyı belirtir. Denetim etkin değilse, denetimin kayıtlı tavsiye lavabolarını (denetim sınıfı veri üyesi [CComControlBase::m_spAdviseSink](#m_spadvisesink)aracılığıyla) denetimin görünümünün değiştiğini bildirin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

## <a name="ccomcontrolbasegetambientappearance"></a><a name="getambientappearance"></a>CComControlBase::GetAmbientAppearance

DISPID_AMBIENT_APPEARANCE alır, denetim için geçerli görünüm ayarı: düz için 0 ve 3D için 1.

```
HRESULT GetAmbientAppearance(short& nAppearance);
```

### <a name="parameters"></a>Parametreler

*nGörünüm*<br/>
Mülk DISPID_AMBIENT_APPEARANCE.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#22](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]

## <a name="ccomcontrolbasegetambientautoclip"></a><a name="getambientautoclip"></a>CComControlBase::GetAmbientAutoClip

Kapsayıcının denetim görüntüleme alanının otomatik kırpmasını destekleyip desteklemediğini belirten bir bayrak olan DISPID_AMBIENT_AUTOCLIP alır.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>Parametreler

*bAutoClip*<br/>
Tesis DISPID_AMBIENT_AUTOCLIP.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientbackcolor"></a><a name="getambientbackcolor"></a>CComControlBase::GetAmbientBackColor

Kapsayıcı tarafından tanımlanan tüm denetimler için ortam arka plan rengi olan DISPID_AMBIENT_BACKCOLOR alır.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>Parametreler

*Backcolor*<br/>
Mülk DISPID_AMBIENT_BACKCOLOR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientcharset"></a><a name="getambientcharset"></a>CComControlBase::GetAmbientCharSet

Kapsayıcı tarafından tanımlanan tüm denetimler için ortam karakteri kümesi olan DISPID_AMBIENT_CHARSET alır.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>Parametreler

*bstrCharSet*<br/>
Tesis DISPID_AMBIENT_CHARSET.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="ccomcontrolbasegetambientcodepage"></a><a name="getambientcodepage"></a>CComControlBase::GetAmbientCodePage

Kapsayıcı tarafından tanımlanan tüm denetimler için ortam kodu sayfası olan DISPID_AMBIENT_CODEPAGE alır.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>Parametreler

*ulCodePage*<br/>
Tesis DISPID_AMBIENT_CODEPAGE.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="ccomcontrolbasegetambientdisplayasdefault"></a><a name="getambientdisplayasdefault"></a>CComControlBase::GetAmbientDisplayAsDefault

Kapsayıcı bu sitedeki denetimi varsayılan düğme olarak işaretlediyse, doğru olan bir bayrak olan DISPID_AMBIENT_DISPLAYASDEFAULT alır ve bu nedenle bir düğme denetimi kendisini daha kalın bir çerçeveyle çizmelidir.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*bDisplayAsDefault*<br/>
Tesis DISPID_AMBIENT_DISPLAYASDEFAULT.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientdisplayname"></a><a name="getambientdisplayname"></a>CComControlBase::GetAmbientDisplayName

kapsayıcının denetime verdiği ad olan DISPID_AMBIENT_DISPLAYNAME alır.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>Parametreler

*bstrDisplayName*<br/>
Tesis DISPID_AMBIENT_DISPLAYNAME.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientfont"></a><a name="getambientfont"></a>CComControlBase::GetAmbientFont

Kapsayıcının ortam `IFont` arabirimine bir işaretçi alır.

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*<br/>
Kapsayıcının ortam [IFont](/windows/win32/api/ocidl/nn-ocidl-ifont) arabirimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Özellik NULL ise, işaretçi NULL'dur. İşaretçi NULL değilse, arayan işaretçiyi serbest bırakmalıdır.

## <a name="ccomcontrolbasegetambientfontdisp"></a><a name="getambientfontdisp"></a>CComControlBase::GetAmbientFontDisp

Kapsayıcının ortam `IFontDisp` gönderme arabirimine bir işaretçi alır.

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*<br/>
Kapsayıcının ortam [IFontDisp](/windows/win32/api/ocidl/nn-ocidl-ifontdisp) gönderme arabirimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Özellik NULL ise, işaretçi NULL'dur. İşaretçi NULL değilse, arayan işaretçiyi serbest bırakmalıdır.

## <a name="ccomcontrolbasegetambientforecolor"></a><a name="getambientforecolor"></a>CComControlBase::GetAmbientForeColor

Kapsayıcı tarafından tanımlanan tüm denetimler için ortam ön plan rengi olan DISPID_AMBIENT_FORECOLOR alır.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>Parametreler

*Forecolor*<br/>
Tesis DISPID_AMBIENT_FORECOLOR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientlocaleid"></a><a name="getambientlocaleid"></a>CComControlBase::GetAmbientLocaleID

Kapsayıcı tarafından kullanılan dilin tanımlayıcısı olan DISPID_AMBIENT_LOCALEID alır.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Tesis DISPID_AMBIENT_LOCALEID.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetim, kullanıcı arabirimini farklı dillere uyarlamak için bu tanımlayıcıyı kullanabilir.

## <a name="ccomcontrolbasegetambientmessagereflect"></a><a name="getambientmessagereflect"></a>CComControlBase::GetAmbientMessageReflect

Kapsayıcının olay olarak pencere iletileri (örneğin) `WM_DRAWITEM`almak isteyip istemediğini belirten bir bayrak olan DISPID_AMBIENT_MESSAGEREFLECT alır.

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>Parametreler

*bMessageReflect*<br/>
Tesis DISPID_AMBIENT_MESSAGEREFLECT.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientpalette"></a><a name="getambientpalette"></a>CComControlBase::GetAmbientPalette

Konteynerin HPALETTE'sine erişmek için kullanılan DISPID_AMBIENT_PALETTE alır.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>Parametreler

*hPalette*<br/>
Tesis DISPID_AMBIENT_PALETTE.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientproperty"></a><a name="getambientproperty"></a>CComControlBase::GetAmbientProperty

*Dispid*tarafından belirtilen kapsayıcı özelliğini alır.

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
Alınacak konteyner özelliğinin tanımlayıcısı.

*var*<br/>
Özelliği almak için değişken.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

ATL belirli özellikleri almak için yardımcı işlevleri bir dizi sağlamıştır, örneğin, [CComControlBase::GetAmbientBackColor](#getambientbackcolor). Uygun bir yöntem yoksa, `GetAmbientProperty`kullanın.

## <a name="ccomcontrolbasegetambientrighttoleft"></a><a name="getambientrighttoleft"></a>CComControlBase::GetAmbientRightToLeft

İçeriğin kapsayıcı tarafından görüntülendiği yön olan DISPID_AMBIENT_RIGHTTOLEFT alır.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>Parametreler

*bRightToLeft*<br/>
Mülk DISPID_AMBIENT_RIGHTTOLEFT. İçerik sağdan sola, false soldan sağa doğru görüntüleniyorsa DOĞRU olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="ccomcontrolbasegetambientscaleunits"></a><a name="getambientscaleunits"></a>CComControlBase::GetAmbientScaleUnits

Ekranları etiketlemek için kabın ortam birimlerini (inç veya santimetre gibi) DISPID_AMBIENT_SCALEUNITS alır.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>Parametreler

*bstrScaleUnits*<br/>
Tesis DISPID_AMBIENT_SCALEUNITS.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientshowgrabhandles"></a><a name="getambientshowgrabhandles"></a>CComControlBase::GetAmbientShowGrabHandles

Kapsayıcının etkin olduğunda tutamak tutamaçlarını kendisi için görüntülemesine izin verip vermediğine dair bir bayrak olan DISPID_AMBIENT_SHOWGRABHANDLES alır.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>Parametreler

*bShowGrabHandles*<br/>
Tesis DISPID_AMBIENT_SHOWGRABHANDLES.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientshowhatching"></a><a name="getambientshowhatching"></a>CComControlBase::GetAmbientShowHatching

DISPID_AMBIENT_SHOWHATCHING alır, kapsayıcının denetimin kullanıcı arabirimi etkin olduğunda kendini hatched desenle görüntülemesine izin verip vermediğine dair bir bayrak.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>Parametreler

*bShowHatching*<br/>
Tesis DISPID_AMBIENT_SHOWHATCHING.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientsupportsmnemonics"></a><a name="getambientsupportsmnemonics"></a>CComControlBase::GetAmbientSupportsMnemonics

Kapsayıcının klavye mnemonics'i destekleyip desteklemediğini belirten bir bayrak olan DISPID_AMBIENT_SUPPORTSMNEMONICS alır.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>Parametreler

*bSupportsMnemonics*<br/>
Tesis DISPID_AMBIENT_SUPPORTSMNEMONICS.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambienttextalign"></a><a name="getambienttextalign"></a>CComControlBase::GetAmbientTextAlign

kapsayıcı tarafından tercih edilen metin hizalaması DISPID_AMBIENT_TEXTALIGN alır: genel hizalama için 0 (sağ, metin sol), sol hizalama için 1, merkez hizalama için 2 ve sağ hizalama için 3.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>Parametreler

*nTextAlign*<br/>
Mülk DISPID_AMBIENT_TEXTALIGN.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambienttoptobottom"></a><a name="getambienttoptobottom"></a>CComControlBase::GetAmbientTopToBottom

İçeriğin kapsayıcı tarafından görüntülendiği yön olan DISPID_AMBIENT_TOPTOBOTTOM alır.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>Parametreler

*bTopToBottom*<br/>
Mülk DISPID_AMBIENT_TOPTOBOTTOM. Metin yukarıdan aşağıya doğru gösteriliyorsa TRUE, alttabakadan üste görüntüleniyorsa FALSE olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="ccomcontrolbasegetambientuidead"></a><a name="getambientuidead"></a>CComControlBase::GetAmbientUIDead

Kapsayıcının denetimin kullanıcı arabirimi eylemlerine yanıt vermek isteyip istemediğini belirten bir bayrak olan DISPID_AMBIENT_UIDEAD alır.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>Parametreler

*bUIDead*<br/>
Tesis DISPID_AMBIENT_UIDEAD.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

TRUE ise, denetim yanıt vermemelidir. Bu bayrak, DISPID_AMBIENT_USERMODE bayrağından bağımsız olarak geçerlidir. Bkz. [CComControlBase::GetAmbientUserMode](#getambientusermode).

## <a name="ccomcontrolbasegetambientusermode"></a><a name="getambientusermode"></a>CComControlBase::GetAmbientUserMode

DISPID_AMBIENT_USERMODE alır, kapsayıcının çalışma modunda olup olmadığını belirten bir bayrak (TRUE) veya tasarım modu (FALSE).

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>Parametreler

*bUserMode*<br/>
Tesis DISPID_AMBIENT_USERMODE.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetdirty"></a><a name="getdirty"></a>CcomControlBase::GetDirty

Veri üyesinin `m_bRequiresSave`değerini verir.

```
BOOL GetDirty();
```

### <a name="return-value"></a>Dönüş Değeri

Veri üyesi nin değerini [verir m_bRequiresSave.](#m_brequiressave)

### <a name="remarks"></a>Açıklamalar

Bu değer [CComControlBase::SetDirty](#setdirty)kullanılarak ayarlanır.

## <a name="ccomcontrolbasegetzoominfo"></a><a name="getzoominfo"></a>CcomControlBase::Getzoominfo

Yerinde düzenleme için etkinleştirilen bir denetim için yakınlaştırma faktörünün paydası ve paydasının x ve y değerlerini alır.

```cpp
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*Di*<br/>
Zum faktörünün sayıve paydasını tutacak yapı. Daha fazla bilgi için [ATL_DRAWINFO.](../../atl/reference/atl-drawinfo-structure.md)

### <a name="remarks"></a>Açıklamalar

Yakınlaştırma faktörü, denetimin doğal boyutunun geçerli boyutuna oranıdır.

## <a name="ccomcontrolbaseinplaceactivate"></a><a name="inplaceactivate"></a>CcomControlBase::InplaceActivate

Denetimin etkin olmayan durumdan *iVerb'deki* fiilin gösterdiği duruma geçişine neden olur.

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>Parametreler

*iFiil*<br/>
[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md#doverb)tarafından gerçekleştirilecek eylemi gösteren değer::DoVerb .

*prcPosRect*<br/>
Yerinde denetimin konumunu işaretet.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Etkinleştirmeden önce, bu yöntem denetimin bir istemci sitesi olup olmadığını denetler, denetimin ne kadarının görünür olduğunu denetler ve denetimin üst penceredeki konumunu alır. Denetim etkinleştirildikten sonra, bu yöntem denetimin kullanıcı arabirimini etkinleştirir ve denetimi görünür hale getirmesini kapsayıcıya söyler.

Bu yöntem ayrıca `IOleInPlaceSite`denetim `IOleInPlaceSiteEx`için `IOleInPlaceSiteWindowless` bir , veya arabirim işaretçisi alır ve denetim sınıfının veri üyesi [CComControlBase depolar::m_spInPlaceSite](#m_spinplacesite). Kontrol sınıfı veri üyeleri [CComControlBase::m_bInPlaceSiteEx,](#m_binplacesiteex) [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)ve [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) uygun olarak doğru ayarlanır.

## <a name="ccomcontrolbaseinternalgetsite"></a><a name="internalgetsite"></a>CcomControlBase::Internalgetsite

Tanımlanan arabirimin işaretçisi için denetim sitesini sorgulamak için bu yöntemi arayın.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
*ppUnkSite*döndürülmelidir arabirim işaretçisi IID .

*ppUnkSite*<br/>
*Riid'de*istenen arabirim işaretçisini alan işaretçi değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Site *riid*istenen arayüzü destekliyorsa, işaretçi *ppUnkSite*yoluyla döndürülür. Aksi takdirde, *ppUnkSite* NULL olarak ayarlanır.

## <a name="ccomcontrolbasem_bautosize"></a><a name="m_bautosize"></a>CComControlBase::m_bAutoSize

Denetimi gösteren bayrak başka bir boyut olamaz.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>Açıklamalar

Bu bayrak tarafından `IOleObjectImpl::SetExtent` denetlenir ve TRUE ise, işlevin E_FAIL dönmesine neden olur.

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

ATL Denetim Sihirbazı'nın [Stok Özellikleri](../../atl/reference/stock-properties-atl-control-wizard.md) sekmesine Otomatik **Boyut** seçeneğini eklerseniz, sihirbaz denetim sınıfınızda bu veri üyesini otomatik olarak oluşturur, özellik için put ve get yöntemleri oluşturur ve özellik değiştiğinde kapsayıcıyı otomatik olarak bildirmek için [IPropertyNotifySink'ü](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) destekler.

## <a name="ccomcontrolbasem_bdrawfromnatural"></a><a name="m_bdrawfromnatural"></a>CComControlBase::m_bDrawFromNatural

Bunu `IDataObjectImpl::GetData` belirten bayrak `CComControlBase::GetZoomInfo` ve denetim boyutunu `m_sizeNatural` 'dan `m_sizeExtent`değil de.

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_bdrawgetdatainhimetric"></a><a name="m_bdrawgetdatainhimetric"></a>CComControlBase::m_bDrawGetDataInHimetric

Çizim yaparken `IDataObjectImpl::GetData` piksel değil, HIMETRIC birimlerinin kullanılması gerektiğini belirten bayrak.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>Açıklamalar

Her mantıksal HIMETRIC birimi 0.01 milimetredir.

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_binplaceactive"></a><a name="m_binplaceactive"></a>CComControlBase::m_bInPlaceActive

Denetimin etkin olduğunu belirten bayrak.

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>Açıklamalar

Bu, denetimin görünür olduğu ve varsa penceresinin görünür olduğu, ancak menülerinin ve araç çubuklarının etkin olmadığı anlamına gelir. Bayrak, `m_bUIActive` denetimin menüler gibi kullanıcı arabiriminin de etkin olduğunu gösterir.

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_binplacesiteex"></a><a name="m_binplacesiteex"></a>CComControlBase::m_bInPlaceSiteEx

Kapsayıcıyı gösteren `IOleInPlaceSiteEx` bayrak, arabirimi ve penceresiz ve titreşmesiz denetimler gibi OCX96 denetim özelliklerini destekler.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

Veri üyesi `m_spInPlaceSite` bir [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)işaret , [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex), veya [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arayüzü, `m_bInPlaceSiteEx` ve bayrakların değerine `m_bWndLess` bağlı olarak. (İşaretçinin `m_bNegotiatedWnd` `m_spInPlaceSite` geçerli olabilmesi için veri üyesinin DOĞRU olması gerekir.)

FALSE `m_bWndLess` ise `m_bInPlaceSiteEx` ve TRUE `m_spInPlaceSite` ise, bir `IOleInPlaceSiteEx` arabirim işaretçisi. Bu üç veri üyesi arasındaki ilişkiyi gösteren bir tablo için [m_spInPlaceSite](#m_spinplacesite) bakın.

## <a name="ccomcontrolbasem_bnegotiatedwnd"></a><a name="m_bnegotiatedwnd"></a>CComControlBase::m_bNegotiatedWnd

Denetimin OCX96 denetim özellikleri (titremesiz ve penceresiz denetimler gibi) desteği hakkında kapsayıcıyla görüşüp görüşmediğini ve denetimin pencereli veya penceresiz olup olmadığını belirten bayrak.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

İşaretçinin `m_bNegotiatedWnd` geçerli olabilmesi için bayrağın `m_spInPlaceSite` DOĞRU olması gerekir.

## <a name="ccomcontrolbasem_brecomposeonresize"></a><a name="m_brecomposeonresize"></a>CComControlBase::m_bRecomposeOnResize

Kapsayıcı denetimin ekran boyutunu değiştirdiğinde, denetimi gösteren bayrak sunusunu yeniden oluşturmak ister.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

Bu bayrak [IOleObjectImpl tarafından denetlenir::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) ve `SetExtent` TRUE ise, görünüm değişiklikleri kapsayıcısını not. bu bayrak ayarlanırsa, [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) numaralandırmasındaki OLEMISC_RECOMPOSEONRESIZE biti de ayarlanmalıdır.

## <a name="ccomcontrolbasem_brequiressave"></a><a name="m_brequiressave"></a>CComControlBase::m_bRequiresSave

Denetimin en son kaydedildiği günden beri değiştiğini belirten bayrak.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>Açıklamalar

Değeri `m_bRequiresSave` [CComControlBase ile ayarlanabilir::SetDirty](#setdirty) ve [CComControlBase ile alınır::GetDirty](#getdirty).

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_bresizenatural"></a><a name="m_bresizenatural"></a>CComControlBase::m_bResizeNatural

Denetimin, kapsayıcı denetimin ekran boyutunu değiştirdiğinde doğal boyutunu (ölçeklendirilmemiş fiziksel boyutunu) yeniden boyutlandırmak istediğini belirten bayrak.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>Açıklamalar

Bu bayrak tarafından `IOleObjectImpl::SetExtent` denetlenir ve TRUE ise, `SetExtent` içine `m_sizeNatural`geçirilen boyut atanır.

Geçirilen `SetExtent` boyut, değeri `m_sizeExtent` `m_bResizeNatural`ne olursa olsun, her zaman .

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_buiactive"></a><a name="m_buiactive"></a>CComControlBase::m_bUIActive

Denetimin menüler ve araç çubukları gibi kullanıcı arabirimini belirten bayrak etkindir.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>Açıklamalar

Bayrak `m_bInPlaceActive` denetimin etkin olduğunu, ancak kullanıcı arabiriminin etkin olduğunu gösterir.

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_busingwindowrgn"></a><a name="m_busingwindowrgn"></a>CComControlBase::m_bUsingWindowRgn

Denetimi gösteren bayrak, konteyner tarafından sağlanan pencere bölgesini kullanıyor.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_bwasoncewindowless"></a><a name="m_bwasoncewindowless"></a>CComControlBase::m_bWasOnceWindowless

Denetimi belirten bayrak penceresiz olmuştur, ancak şimdi penceresiz olabilir veya olmayabilir.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_bwindowonly"></a><a name="m_bwindowonly"></a>CComControlBase::m_bWindowOnly

Kapsayıcı penceresiz denetimleri desteklese bile denetimi gösteren bayrak pencereli olmalıdır.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_bwndless"></a><a name="m_bwndless"></a>CComControlBase::m_bWndLess

Denetimi gösteren bayrak penceresiz.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

Veri üyesi `m_spInPlaceSite` bir [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)işaret , [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex), veya [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arayüzü, `m_bWndLess` ve [CComControlBase](#m_binplacesiteex) değerine bağlı olarak::m_bInPlaceSiteEx bayrakları. (Veri üyesi [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) [CComControlBase](#m_spinplacesite) için DOĞRU olmalıdır::m_spInPlaceSite işaretçi geçerli olmak.)

TRUE `m_bWndLess` ise, `m_spInPlaceSite` bir `IOleInPlaceSiteWindowless` arabirim işaretçisi. Bu veri üyeleri arasındaki tüm ilişkiyi gösteren bir tablo için [CComControlBase::m_spInPlaceSite'a](#m_spinplacesite) bakın.

## <a name="ccomcontrolbasem_hwndcd"></a><a name="m_hwndcd"></a>CComControlBase::m_hWndCD

Denetimle ilişkili pencere tutamacına bir başvuru içerir.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_nfreezeevents"></a><a name="m_nfreezeevents"></a>CComControlBase::m_nFreezeEvents

Kapsayıcının olayları kaç kez dondurduğunun sayısı (olayları kabul etmeyi reddeder) olayların çözülmesi (olayların kabulü) olmadan.

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_rcpos"></a><a name="m_rcpos"></a>CComControlBase::m_rcPos

Denetimpikselkonum, kapsayıcının koordinatlarında ifade.

```
RECT m_rcPos;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_sizeextent"></a><a name="m_sizeextent"></a>CComControlBase::m_sizeExtent

Belirli bir ekran için HIMETRIC birimlerinde (her birim 0,01 milimetredir) kontrolün kapsamı.

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

Bu boyut ekran tarafından ölçeklendirilir. Denetimin fiziksel boyutu veri üyesinde `m_sizeNatural` belirtilir ve sabitlenir.

[AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)işlevi ile boyutu piksellere dönüştürebilirsiniz.

## <a name="ccomcontrolbasem_sizenatural"></a><a name="m_sizenatural"></a>CComControlBase::m_sizeNatural

HIMETRIC birimlerinde kontrolün fiziksel boyutu (her birim 0,01 milimetredir).

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

Bu boyut sabitlenirken, `m_sizeExtent` boyutu ekran tarafından ölçeklendirilir.

[AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)işlevi ile boyutu piksellere dönüştürebilirsiniz.

## <a name="ccomcontrolbasem_spadvisesink"></a><a name="m_spadvisesink"></a>CComControlBase::m_spAdviseSink

Kapsayıcı (kapsayıcının [IAdviseSink)](/windows/win32/api/objidl/nn-objidl-iadvisesink)üzerinde danışma bağlantısı için doğrudan bir işaretçi.

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_spambientdispatch"></a><a name="m_spambientdispatch"></a>CComControlBase::m_spAmbientDispatch

Bir `CComDispatchDriver` işaretçi aracılığıyla nesnenin özelliklerini alıp ayarlamanızı sağlayan bir `IDispatch` nesne.

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_spclientsite"></a><a name="m_spclientsite"></a>CComControlBase::m_spClientSite

Denetimin istemci sitesine kapsayıcı içinde bir işaretçi.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

## <a name="ccomcontrolbasem_spdataadviseholder"></a><a name="m_spdataadviseholder"></a>CComControlBase::m_spDataAdviseHolder

Veri nesneleri arasında danışma bağlantıları tutmak ve lavabolara tavsiyelerde bulunmak için standart bir araç sağlar.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

Veri nesnesi, veri aktarımı yapabilecek ve yöntemleri verilerin biçimini ve aktarım ortamını belirten [IDataObject'i](/windows/win32/api/objidl/nn-objidl-idataobject)uygulayan bir denetimdir.

Arabirim, `m_spDataAdviseHolder` kapsayıcıya danışma bağlantıları kurmak ve silmek için [iDataObject::DAdvise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) ve [IDataObject::DUnadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) yöntemlerini uygular. Denetim [inkapsayıcıi IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) arabirimini destekleyerek bir tavsiye lavabosu uygulamalıdır.

## <a name="ccomcontrolbasem_spinplacesite"></a><a name="m_spinplacesite"></a>CComControlBase::m_spInPlaceSite

Konteynerin [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)bir işaretçi , [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex), veya [IOleInPlaceSiteWindowless](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arayüz işaretçisi.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

İşaretçi `m_spInPlaceSite` yalnızca [m_bNegotiatedWnd](#m_bnegotiatedwnd) bayrağı DOĞRUysa geçerlidir.

Aşağıdaki tablo, `m_spInPlaceSite` işaretçi türünün [m_bWndLess](#m_bwndless) ve [m_bInPlaceSiteEx](#m_binplacesiteex) veri üyesi bayraklarına nasıl bağlı olduğunu gösterir:

|m_spInPlaceSite Türü|m_bWndLess Değeri|m_bInPlaceSiteEx Değeri|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|TRUE|DOĞRU VEYA YANLIŞ|
|`IOleInPlaceSiteEx`|FALSE|TRUE|
|`IOleInPlaceSite`|FALSE|FALSE|

## <a name="ccomcontrolbasem_spoleadviseholder"></a><a name="m_spoleadviseholder"></a>CComControlBase::m_spOleAdviseHolder

Danışma bağlantılarını tutmanın standart bir uygulamasını sağlar.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınızda kullanmak için, denetim sınıfınızda bir veri üyesi olarak beyan etmeniz gerekir. Denetim sınıfınız, taban sınıfta bir birleşim içinde beyan edildiği için bu veri üyesini taban sınıftan devralmaz.

Arabirim `m_spOleAdviseHolder` [IOleObject uygular::Advise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) ve [IOleObject::Kapsayıcıya](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) danışma bağlantıları kurmak ve silmek için tavsiye edilmeyen yöntemler. Denetim [inkapsayıcıi IAdviseSink](/windows/win32/api/objidl/nn-objidl-iadvisesink) arabirimini destekleyerek bir tavsiye lavabosu uygulamalıdır.

## <a name="ccomcontrolbaseondraw"></a><a name="ondraw"></a>CcomControlBase::OnDraw

Denetiminizi çekmek için bu yöntemi geçersiz kılın.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*Di*<br/>
Çizim yönü, denetim sınırları ve çizimin optimize edilip edilmediği gibi çizim bilgilerini içeren [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) yapısına yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Varsayılan `OnDraw` aygıt bağlamını siler veya geri yükler veya CComControlBase'de ayarlanan bayraklara bağlı olarak hiçbir şey [yapmaz::OnDrawAdvanced](#ondrawadvanced).

ATL Denetim Sihirbazı ile denetiminizi oluşturduğunuzda bir `OnDraw` yöntem otomatik olarak denetim sınıfınıza eklenir. Sihirbazın varsayılanı `OnDraw` "ATL 8.0" etiketli bir dikdörtgen çizer.

### <a name="example"></a>Örnek

CComControlBase için örneğe [bakın:GetAmbientAppearance](#getambientappearance).

## <a name="ccomcontrolbaseondrawadvanced"></a><a name="ondrawadvanced"></a>CcomControlBase::OndrawAdvanced

Varsayılan, `OnDrawAdvanced` çizim için normalleştirilmiş bir aygıt bağlamı hazırlar `OnDraw` ve ardından denetim sınıfınızın yöntemini çağırır.

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*Di*<br/>
Çizim yönü, denetim sınırları ve çizimin optimize edilip edilmediği gibi çizim bilgilerini içeren [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) yapısına yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Normalleştirmeden kapsayıcı tarafından geçirilen aygıt bağlamını kabul etmek istiyorsanız bu yöntemi geçersiz kılın.

Bkz. [CComControlBase::Daha](#ondraw) fazla bilgi için OnDraw.

## <a name="ccomcontrolbaseonkillfocus"></a><a name="onkillfocus"></a>CcomControlBase::OnKillFocus

Denetimin yerinde etkin olup olmadığını ve geçerli bir denetim sitesi olup olmadığını denetler, ardından denetimin odak noktasını kaybettiğini kapsayıcıya bildirir.

```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
Ayrılmış.

*Wparam*<br/>
Ayrılmış.

*Lparam*<br/>
Ayrılmış.

*bHandled*<br/>
Pencere iletisinin başarıyla işlenip işlenmediğini belirten bayrak. Varsayılan FALSE'dır.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

## <a name="ccomcontrolbaseonmouseactivate"></a><a name="onmouseactivate"></a>CcomControlBase::OnMouseActivate

Kullanıcı UI'nin kullanıcı modunda olup olmadığını denetler ve denetimi etkinleştirir.

```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
Ayrılmış.

*Wparam*<br/>
Ayrılmış.

*Lparam*<br/>
Ayrılmış.

*bHandled*<br/>
Pencere iletisinin başarıyla işlenip işlenmediğini belirten bayrak. Varsayılan FALSE'dır.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

## <a name="ccomcontrolbaseonpaint"></a><a name="onpaint"></a>CcomControlBase::Onpaint

Kapsayıcıyı boyama için hazırlar, denetimin istemci alanını alır, sonra `OnDrawAdvanced` denetim sınıfının yöntemini arar.

```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
Ayrılmış.

*Wparam*<br/>
Varolan bir HDC.

*Lparam*<br/>
Ayrılmış.

*lResult*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Her zaman sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

*wParam* NULL değilse, `OnPaint` geçerli bir HDC içerdiğini varsayar ve [CComControlBase yerine kullanır::m_hWndCD](#m_hwndcd).

## <a name="ccomcontrolbaseonsetfocus"></a><a name="onsetfocus"></a>CcomControlBase::OnsetFocus

Denetimin yerinde etkin olup olmadığını ve geçerli bir kontrol bölgesine sahip olup olmadığını denetler, ardından denetimin odaklandığı kapsayıcıyı bildirir.

```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*nMsg*<br/>
Ayrılmış.

*Wparam*<br/>
Ayrılmış.

*Lparam*<br/>
Ayrılmış.

*bHandled*<br/>
Pencere iletisinin başarıyla işlenip işlenmediğini belirten bayrak. Varsayılan FALSE'dır.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin odaklandığı kapsayıcıya bir bildirim gönderir.

## <a name="ccomcontrolbasepretranslateaccelerator"></a><a name="pretranslateaccelerator"></a>CComControlBase::PreTranslateAccelerator

Kendi klavye hızlandırıcı işleyicilerinizi sağlamak için bu yöntemi geçersiz kılın.

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

Varsayılan olarak FALSE döndürür.

## <a name="ccomcontrolbasesendonclose"></a><a name="sendonclose"></a>CcomControlBase::SendonClose

Tavsiye sahibine kayıtlı tüm danışmanlık lavabolarına denetimin kapatıldığını bildirin.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Denetimin danışma lavabolarını kapattığına dair bir bildirim gönderir.

## <a name="ccomcontrolbasesendondatachange"></a><a name="sendondatachange"></a>CcomControlBase::SendonDataChange

Tavsiye sahibine kayıtlı tüm danışma lavabolarını kontrol verilerinin değiştiğini bildirer.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>Parametreler

*advf*<br/>
[IAdviseSink::OnDataChange'e](/windows/win32/api/objidl/nf-objidl-iadvisesink-ondatachange) yapılan çağrının nasıl yapıldığını belirten bayraklar tavsiye edin. Değerler [ADVF](/windows/win32/api/objidl/ne-objidl-advf) numaralandırmadan dır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="ccomcontrolbasesendonrename"></a><a name="sendonrename"></a>CComControlBase::SendOnRename

Tavsiye sahibine kayıtlı tüm danışmanlık lavabolarını, kontrolün yeni bir takma adı olduğunu bildirer.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>Parametreler

*Pmk*<br/>
Denetimin yeni lakabını işaretet.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Denetim için takma alabilen bir bildirim gönderir.

## <a name="ccomcontrolbasesendonsave"></a><a name="sendonsave"></a>CcomControlBase::sendonsave

Tavsiye sahibine kayıtlı tüm danışmanlık lavabolarını, kontrolün kaydedildiğini bildirer.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Denetimin verilerini kaydettiğine dair bir bildirim gönderir.

## <a name="ccomcontrolbasesendonviewchange"></a><a name="sendonviewchange"></a>CcomControlBase::SendonViewChange

Tüm kayıtlı danışma lavabolarına denetimin görünümünün değiştiğini belirtir.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>Parametreler

*dwAspect*<br/>
Denetimin yönü veya görünümü.

*Lindex*<br/>
Görünümün değişen bölümü. Sadece -1 geçerlidir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

`SendOnViewChange`[iAdviseSink çağırır::OnViewChange](/windows/win32/api/objidl/nf-objidl-iadvisesink-onviewchange). Şu anda desteklenen *lindex* tek değeri -1, tüm görünümü niçin ilgi olduğunu gösterir.

## <a name="ccomcontrolbasesetcontrolfocus"></a><a name="setcontrolfocus"></a>CcomControlBase::SetControlFocus

Klavye odağının denetime veya denetimden ayarlanır veya kaldırır.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>Parametreler

*bGrab*<br/>
TRUE ise, klavye odağı arama denetimine ayarlar. FALSE ise, odak noktası olması koşuluyla klavye odağı arama denetiminden kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarıyla odak alıyorsa TRUE döndürür; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Pencereli denetim için Windows API işlevi [SetFocus](/windows/win32/api/winuser/nf-winuser-setfocus) çağrılır. Penceresiz bir denetim için, [IOleInPlaceSiteWindowless::SetFocus](/windows/win32/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) denir. Bu arama sayesinde, penceresiz denetim klavye odağı elde eder ve pencere iletilerine yanıt verebilir.

## <a name="ccomcontrolbasesetdirty"></a><a name="setdirty"></a>CcomControlBase::SetDirty

Veri üyesini `m_bRequiresSave` *bDirty'deki*değere ayarlar.

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*bKirli*<br/>
Veri üyesi [CComControlBase değeri::m_bRequiresSave](#m_brequiressave).

### <a name="remarks"></a>Açıklamalar

`SetDirty(TRUE)`son kaydedildiğından beri denetimin değiştiğini işaretlemek için çağrılmalıdır. Değeri `m_bRequiresSave` [CComControlBase ile alınır::GetDirty](#getdirty).

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
