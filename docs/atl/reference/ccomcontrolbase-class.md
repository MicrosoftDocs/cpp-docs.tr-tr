---
description: 'Daha fazla bilgi edinin: CComControlBase sınıfı'
title: CComControlBase sınıfı
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
ms.openlocfilehash: 5ea232ac84ede33f7faa2a04e75b1ef65073ae9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152171"
---
# <a name="ccomcontrolbase-class"></a>CComControlBase sınıfı

Bu sınıf, ATL denetimleri oluşturmak ve yönetmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class ATL_NO_VTABLE CComControlBase
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CComControlBase:: AppearanceType](#appearancetype)|`m_nAppearance`Hisse senedi özelliği türünde değilse, bunu geçersiz kılın **`short`** .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComControlBase:: CComControlBase](#ccomcontrolbase)|Oluşturucu.|
|[CComControlBase:: ~ CComControlBase](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComControlBase:: Controlqueryınterface](#controlqueryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComControlBase::D Oesverbacuter](#doesverbactivate)|Tarafından kullanılan *ıverb* parametresinin, `IOleObjectImpl::DoVerb` denetimin kullanıcı arabirimini (*ıverb* eşittir OLEIVERB_UIACTIVATE) etkinleştirdiğini denetler, Kullanıcı denetimi çift tıkladığında (*ıverb* eşittir OLEIVERB_PRIMARY), denetimi (*ıverb* eşittir OLEIVERB_SHOW) gösterir veya denetimi etkinleştirir (*ifiil* eşittir OLEIVERB_INPLACEACTIVATE).|
|[CComControlBase::D Oesverbuıactivate](#doesverbuiactivate)|Tarafından kullanılan *ıverb* parametresinin, `IOleObjectImpl::DoVerb` denetimin kullanıcı ARABIRIMININ etkin ve true değerini döndürür olduğunu denetler.|
|[CComControlBase::D fazla Bproperties](#doverbproperties)|Denetimin özellik sayfalarını görüntüler.|
|[CComControlBase:: FireViewChange](#fireviewchange)|Kapsayıcının denetimi yeniden çizmesini söylemek veya denetim görünümünün değiştiği kayıtlı öneri havuzlarını bilgilendirmek için bu yöntemi çağırın.|
|[CComControlBase:: Getambentappearance](#getambientappearance)|DISPID_AMBIENT_APPEARANCE, denetimin geçerli görünüm ayarını (düz için 0) ve 3B için 1 alır.|
|[CComControlBase:: Getambentautoclip](#getambientautoclip)|Kapsayıcının denetim görüntüleme alanının otomatik kırpmasını destekleyip desteklemediğini belirten bir bayrak alır DISPID_AMBIENT_AUTOCLIP.|
|[CComControlBase:: Getambentbackcolor](#getambientbackcolor)|Kapsayıcı tarafından tanımlanan tüm denetimler için çevresel arka plan rengi DISPID_AMBIENT_BACKCOLOR alır.|
|[CComControlBase:: Getambentcharset](#getambientcharset)|Kapsayıcı tarafından tanımlanan tüm denetimler için çevresel karakter kümesini DISPID_AMBIENT_CHARSET alır.|
|[CComControlBase:: Getambentcodepage](#getambientcodepage)|Kapsayıcı tarafından tanımlanan tüm denetimler için çevresel karakter kümesini DISPID_AMBIENT_CODEPAGE alır.|
|[CComControlBase:: Getambentdisplayasdefault](#getambientdisplayasdefault)|Kapsayıcı, bu sitedeki denetimi varsayılan bir düğme olacak şekilde işaretlenmişse TRUE olan bir bayrak DISPID_AMBIENT_DISPLAYASDEFAULT alır ve bu nedenle bir düğme denetimi kendisini daha kalın bir kareyle çizmelidir.|
|[CComControlBase:: Getambentdisplayname](#getambientdisplayname)|Kapsayıcının denetime sağladığı adı DISPID_AMBIENT_DISPLAYNAME alır.|
|[CComControlBase:: GetAmbientFont](#getambientfont)|Kapsayıcının çevresel arabirimine bir işaretçi alır `IFont` .|
|[CComControlBase:: GetAmbientFontDisp](#getambientfontdisp)|Kapsayıcının çevresel dağıtım arabirimine bir işaretçi alır `IFontDisp` .|
|[CComControlBase:: Getambentforecolor](#getambientforecolor)|Kapsayıcı tarafından tanımlanan tüm denetimler için çevresel ön plan rengini DISPID_AMBIENT_FORECOLOR alır.|
|[CComControlBase:: Getambentlocaleıd](#getambientlocaleid)|Kapsayıcı tarafından kullanılan dilin tanımlayıcısını DISPID_AMBIENT_LOCALEID alır.|
|[CComControlBase:: Getambentmessagerefseç](#getambientmessagereflect)|Kapsayıcının olay olarak pencere iletileri (WM_DRAWITEM gibi) almak isteyip istemediğini belirten bir bayrak alır DISPID_AMBIENT_MESSAGEREFLECT.|
|[CComControlBase:: Getambentpalette](#getambientpalette)|Kapsayıcının HPALETTE erişmek için kullanılan DISPID_AMBIENT_PALETTE alır.|
|[CComControlBase:: Getambentproperty](#getambientproperty)|*ID* tarafından belirtilen kapsayıcı özelliğini alır.|
|[CComControlBase:: GetAmbientRightToLeft](#getambientrighttoleft)|İçeriğin kapsayıcı tarafından gösterileceği yönü DISPID_AMBIENT_RIGHTTOLEFT alır.|
|[CComControlBase:: Getambentscaleunits](#getambientscaleunits)|Etiketleme görüntüleri için kapsayıcının çevresel birimlerinin (inç veya santimetre gibi) DISPID_AMBIENT_SCALEUNITS alır.|
|[CComControlBase:: Getambentshowgrabhandles](#getambientshowgrabhandles)|Kapsayıcının, denetimin etkin olduğunda kendi kendine yönelik tutamaçları görüntülemesine izin verip içermediğini belirten bir bayrak alır DISPID_AMBIENT_SHOWGRABHANDLES.|
|[CComControlBase:: Getambentshowhadikiş](#getambientshowhatching)|Kapsayıcının, Kullanıcı arabirimi etkinken denetimin kendisini bir hagesle görüntülemesine izin verip içermediğini belirten bir bayrak alır DISPID_AMBIENT_SHOWHATCHING alır.|
|[CComControlBase:: GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|Kapsayıcının klavye anımsatıcılarını destekleyip desteklemediğini gösteren bir bayrak DISPID_AMBIENT_SUPPORTSMNEMONICS alır.|
|[CComControlBase:: Getambenttextalign](#getambienttextalign)|Kapsayıcının tercih ettiği metin hizalamasını DISPID_AMBIENT_TEXTALIGN alır: Genel hizalama için 0 (rakamlar sağ, metin sola), sol hizalama için 1, orta hizalama için 2 ve sağ hizalama için 3.|
|[CComControlBase:: Getambenttoptobottom](#getambienttoptobottom)|İçeriğin kapsayıcı tarafından gösterileceği yönü DISPID_AMBIENT_TOPTOBOTTOM alır.|
|[CComControlBase:: Getambentuıdead](#getambientuidead)|Kapsayıcının denetimin kullanıcı arabirimi eylemlerine yanıt vermesini isteyip istemediğini belirten bir bayrak olan DISPID_AMBIENT_UIDEAD alır.|
|[CComControlBase:: Getambentkullanıcı modu](#getambientusermode)|Kapsayıcının çalışma modunda (TRUE) veya tasarım modunda (FALSE) olup olmadığını belirten bir bayrak DISPID_AMBIENT_USERMODE alır.|
|[CComControlBase:: GetDirty](#getdirty)|Veri üyesinin değerini döndürür `m_bRequiresSave` .|
|[CComControlBase:: GetZoomInfo](#getzoominfo)|Yerinde düzenlenmek üzere etkinleştirilen bir denetim için yakınlaştırma faktörünün pay ve paydasın x ve y değerlerini alır.|
|[CComControlBase:: InPlaceActivate](#inplaceactivate)|Denetimin etkin olmayan durumdan, *ıverb* 'teki fiilin gösterdiği herhangi bir duruma geçişine neden olur.|
|[CComControlBase:: ınternalgetsite](#internalgetsite)|Tanımlanan arabirime yönelik bir işaretçinin denetim sitesini sorgulamak için bu yöntemi çağırın.|
|[CComControlBase:: OnDraw](#ondraw)|Denetiminizi çizmek için bu yöntemi geçersiz kılın.|
|[CComControlBase:: OnDrawAdvanced](#ondrawadvanced)|Varsayılan değer, `OnDrawAdvanced` Çizim için Normalleştirilmemiş bir cihaz bağlamı hazırlar, sonra denetim sınıfınızın `OnDraw` yöntemini çağırır.|
|[CComControlBase:: OnKillFocus](#onkillfocus)|Denetimin yerinde etkin olduğunu ve geçerli bir denetim sitesine sahip olduğunu denetler, sonra kapsayıcıya denetimin odağa sahip olduğunu bildirir.|
|[CComControlBase:: OnMouseActivate](#onmouseactivate)|Kullanıcı ARABIRIMININ Kullanıcı modunda olduğunu denetler, sonra denetimi etkinleştirir.|
|[CComControlBase:: OnPaint](#onpaint)|Kapsayıcıyı boyama için hazırlar, denetimin istemci alanını alır, sonra Denetim sınıfının `OnDraw` yöntemini çağırır.|
|[CComControlBase:: OnSetFocus](#onsetfocus)|Denetimin yerinde etkin olduğunu ve geçerli bir denetim sitesine sahip olduğunu denetler ve sonra denetimin odağa sahip olduğu kapsayıcıyı bilgilendirir.|
|[CComControlBase::P reTranslateAccelerator](#pretranslateaccelerator)|Kendi klavye Hızlandırıcısı işleyicilerinizi sağlamak için bu yöntemi geçersiz kılın.|
|[CComControlBase:: SendOnClose](#sendonclose)|Denetim kapatılmış olan öneri sahibine kayıtlı tüm danışmanlık havuzlarını bilgilendirir.|
|[CComControlBase:: SendOnDataChange](#sendondatachange)|Denetim verilerinin değiştiği öneri sahibine kayıtlı tüm danışmanlık havuzlarını bilgilendirir.|
|[CComControlBase:: SendOnRename](#sendonrename)|Tüm danışmanlık havuzlarını, denetimin yeni bir adı olan öneri sahibine kayıtlı olduğunu bildirir.|
|[CComControlBase:: SendOnSave](#sendonsave)|Tüm danışmanlık havuzları ' nın, denetimin kaydedildiği öneri sahibine kayıtlı olduğunu bildirir.|
|[CComControlBase:: SendOnViewChange](#sendonviewchange)|Tüm kayıtlı danışmanlık havuzlarını denetim görünümü ' nin değiştiğini bildirir.|
|[CComControlBase:: SetControlFocus](#setcontrolfocus)|Klavye odağını denetimden veya denetiminden kaldırır.|
|[CComControlBase:: SetDirty](#setdirty)|Veri üyesini `m_bRequiresSave` *bDirty* içindeki değere ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComControlBase:: m_bAutoSize](#m_bautosize)|Denetimin başka bir boyut olmadığını belirten bayrak.|
|[CComControlBase:: m_bDrawFromNatural](#m_bdrawfromnatural)|`IDataObjectImpl::GetData`' In ' ı belirten ve `CComControlBase::GetZoomInfo` denetim boyutunu from yerine olarak ayarlaması gerektiğini belirten bayrak `m_sizeNatural` `m_sizeExtent` .|
|[CComControlBase:: m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|`IDataObjectImpl::GetData`Çizim sırasında piksel değil, HIMETRIK birimleri kullanması gerektiğini belirten bayrak.|
|[CComControlBase:: m_bInPlaceActive](#m_binplaceactive)|Denetimin yerinde etkin olduğunu belirten bayrak.|
|[CComControlBase:: m_bInPlaceSiteEx](#m_binplacesiteex)|Kapsayıcının, `IOleInPlaceSiteEx` penceresiz ve titreşimsiz denetimler gibi arabirim ve OCX96 denetim özelliklerini desteklediğini belirten bayrak.|
|[CComControlBase:: m_bNegotiatedWnd](#m_bnegotiatedwnd)|Denetimin, OCX96 denetim özellikleri (titreşimsiz ve Penceresiz denetimler gibi) için destek hakkında kapsayıcınıza ve denetimin pencereli mi yoksa penceresiz mi olduğunu belirten bayrak.|
|[CComControlBase:: m_bRecomposeOnResize](#m_brecomposeonresize)|Kapsayıcı denetimin görüntüleme boyutunu değiştirdiğinde denetimin sunumunu yeniden oluşturmak istediğini belirten bayrak.|
|[CComControlBase:: m_bRequiresSave](#m_brequiressave)|Denetimin son kaydedduğundan bu yana değiştiğini belirten bayrak.|
|[CComControlBase:: m_bResizeNatural](#m_bresizenatural)|Kapsayıcı denetimin görüntüleme boyutunu değiştirdiğinde denetimin doğal kapsamını (ölçeklendirilmemiş fiziksel boyut) yeniden boyutlandırmak istediğini belirten bayrak.|
|[CComControlBase:: m_bUIActive](#m_buiactive)|Denetimin, menüler ve araç çubukları gibi kullanıcı arabirimini belirten bayrak etkin.|
|[CComControlBase:: m_bUsingWindowRgn](#m_busingwindowrgn)|Denetimin kapsayıcı tarafından sağlanan pencere bölgesini kullandığını belirten bayrak.|
|[CComControlBase:: m_bWasOnceWindowless](#m_bwasoncewindowless)|Denetimin penceresiz olduğunu belirten bayrak, ancak şu anda penceresiz olabilir veya görünmeyebilir.|
|[CComControlBase:: m_bWindowOnly](#m_bwindowonly)|Kapsayıcı penceresiz denetimleri desteklese bile denetimin pencereli olması gerektiğini belirten bayrak.|
|[CComControlBase:: m_bWndLess](#m_bwndless)|Denetimin penceresiz olduğunu belirten bayrak.|
|[CComControlBase:: m_hWndCD](#m_hwndcd)|Denetimle ilişkili pencere tanıtıcısına bir başvuru içerir.|
|[CComControlBase:: m_nFreezeEvents](#m_nfreezeevents)|Bir olay çözme (olayların kabulü) olmadan, kapsayıcının dondurulmuş olaylara (olayları kabul etmek için reddedildi) sahip olduğu sayıda sayı.|
|[CComControlBase:: m_rcPos](#m_rcpos)|Denetimin piksel cinsinden konumu, kapsayıcının koordinatları cinsinden ifade edilir.|
|[CComControlBase:: m_sizeExtent](#m_sizeextent)|Belirli bir görüntü için HIMETRIK birimlerde (her birim 0,01 milimetre) denetimin kapsamı.|
|[CComControlBase:: m_sizeNatural](#m_sizenatural)|Denetimin HIMETRIK birimlerde fiziksel boyutu (her birim 0,01 milimetre 'dir).|
|[CComControlBase:: m_spAdviseSink](#m_spadvisesink)|Kapsayıcıda doğrudan danışmanlık bağlantısına yönelik bir işaretçi (kapsayıcının [ıvısesink](/windows/win32/api/objidl/nn-objidl-iadvisesink)).|
|[CComControlBase:: m_spAmbientDispatch](#m_spambientdispatch)|`CComDispatchDriver`Kapsayıcının özelliklerini bir işaretçi aracılığıyla almanıza ve ayarlamanıza imkan tanıyan bir nesne `IDispatch` .|
|[CComControlBase:: m_spClientSite](#m_spclientsite)|Kapsayıcının içindeki denetimin istemci sitesine yönelik bir işaretçi.|
|[CComControlBase:: m_spDataAdviseHolder](#m_spdataadviseholder)|Veri nesneleri ve öneri havuzları arasında danışmanlık bağlantılarını tutmak için standart bir yol sağlar.|
|[CComControlBase:: m_spInPlaceSite](#m_spinplacesite)|Kapsayıcının [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)veya [ıoleınplacesitepenceresiz](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arabirim işaretçisine yönelik bir işaretçi.|
|[CComControlBase:: m_spOleAdviseHolder](#m_spoleadviseholder)|Danışmanlık bağlantılarını tutan bir yol için standart bir uygulama sağlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, ATL denetimleri oluşturmak ve yönetmek için yöntemler sağlar. [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md) öğesinden türetilir `CComControlBase` . ATL Denetim Sihirbazı 'nı kullanarak standart bir denetim veya DHTML denetimi oluşturduğunuzda, sihirbaz sınıfınızı otomatik olarak türetecektir `CComControlBase` .

Denetim oluşturma hakkında daha fazla bilgi için bkz. [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md). ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="ccomcontrolbaseappearancetype"></a><a name="appearancetype"></a> CComControlBase:: AppearanceType

`m_nAppearance`Hisse senedi özelliği türünde değilse, bunu geçersiz kılın **`short`** .

```
typedef short AppearanceType;
```

### <a name="remarks"></a>Açıklamalar

ATL Denetim Sihirbazı `m_nAppearance` Short türünde hisse senedi özelliği ekler. `AppearanceType`Farklı bir veri türü kullanıyorsanız geçersiz kılın.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="ccomcontrolbase"></a> CComControlBase:: CComControlBase

Oluşturucu.

```
CComControlBase(HWND& h);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Denetimle ilişkilendirilen pencerenin tutamacı.

### <a name="remarks"></a>Açıklamalar

Denetim boyutunu 5080X5080 HIMETRIK birimlerine (2 "X2") başlatır ve `CComControlBase` veri üyesi DEğERLERINI null ya da yanlış olarak başlatır.

## <a name="ccomcontrolbaseccomcontrolbase"></a><a name="dtor"></a> CComControlBase:: ~ CComControlBase

Yok edicisi.

```
~CComControlBase();
```

### <a name="remarks"></a>Açıklamalar

Denetim pencereli ise, `~CComControlBase` [Destroyıwindow](/windows/win32/api/winuser/nf-winuser-destroywindow)'u çağırarak onu yok eder.

## <a name="ccomcontrolbasecontrolqueryinterface"></a><a name="controlqueryinterface"></a> CComControlBase:: Controlqueryınterface

İstenen arabirim için bir işaretçi alır.

```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
İstenen arabirimin GUID 'SI.

*PPV*<br/>
Arabirim bulunmazsa, *IID* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi veya ARABIRIM bulunamazsa null.

### <a name="remarks"></a>Açıklamalar

Yalnızca COM Map tablosundaki arabirimleri işler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]

## <a name="ccomcontrolbasedoesverbactivate"></a><a name="doesverbactivate"></a> CComControlBase::D Oesverbacuter

Tarafından kullanılan *ıverb* parametresinin, `IOleObjectImpl::DoVerb` denetimin kullanıcı arabirimini (*ıverb* eşittir OLEIVERB_UIACTIVATE) etkinleştirdiğini denetler, Kullanıcı denetimi çift tıkladığında (*ıverb* eşittir OLEIVERB_PRIMARY), denetimi (*ıverb* eşittir OLEIVERB_SHOW) gösterir veya denetimi etkinleştirir (*ifiil* eşittir OLEIVERB_INPLACEACTIVATE).

```
BOOL DoesVerbActivate(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*ıverb*<br/>
Tarafından gerçekleştirilecek eylemi gösteren değer `DoVerb` .

### <a name="return-value"></a>Dönüş Değeri

*Iverb* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW veya OLEIVERB_INPLACEACTIVATE eşitse true değerini döndürür; Aksi takdirde, FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kendi etkinleştirme fiilini tanımlamak için bu yöntemi geçersiz kılabilirsiniz.

## <a name="ccomcontrolbasedoesverbuiactivate"></a><a name="doesverbuiactivate"></a> CComControlBase::D Oesverbuıactivate

Tarafından kullanılan *ıverb* parametresinin, `IOleObjectImpl::DoVerb` denetimin kullanıcı ARABIRIMININ etkin ve true değerini döndürür olduğunu denetler.

```
BOOL DoesVerbUIActivate(LONG iVerb);
```

### <a name="parameters"></a>Parametreler

*ıverb*<br/>
Tarafından gerçekleştirilecek eylemi gösteren değer `DoVerb` .

### <a name="return-value"></a>Dönüş Değeri

*Iverb* OLEIVERB_UIACTIVATE, OLEIVERB_PRIMARY, OLEIVERB_SHOW veya OLEIVERB_INPLACEACTIVATE eşitse true değerini döndürür. Aksi takdirde, yöntem FALSE döndürür.

## <a name="ccomcontrolbasedoverbproperties"></a><a name="doverbproperties"></a> CComControlBase::D fazla Bproperties

Denetimin özellik sayfalarını görüntüler.

```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```

### <a name="parameters"></a>Parametreler

*prcPosRec*<br/>
Ayrılmış.

*hwndParent*<br/>
Denetimi içeren pencerenin tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#19](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]

[!code-cpp[NVC_ATL_COM#20](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]

## <a name="ccomcontrolbasefireviewchange"></a><a name="fireviewchange"></a> CComControlBase:: FireViewChange

Kapsayıcının denetimi yeniden çizmesini söylemek veya denetim görünümünün değiştiği kayıtlı öneri havuzlarını bilgilendirmek için bu yöntemi çağırın.

```
HRESULT FireViewChange();
```

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetim etkinse (denetim sınıfı veri üyesi [CComControlBase:: M_BINPLACEACTIVE](#m_binplaceactive) true ise), kapsayıcıyı tüm denetimi yeniden çizmek istediğinizi bildirir. Denetim devre dışı ise, denetimin görünüm değiştiği, denetimin kayıtlı öneri havuzlarını ( [CComControlBase:: m_spAdviseSink](#m_spadvisesink)' denetim sınıfı aracılığıyla) bilgilendirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#21](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]

## <a name="ccomcontrolbasegetambientappearance"></a><a name="getambientappearance"></a> CComControlBase:: Getambentappearance

DISPID_AMBIENT_APPEARANCE, denetimin geçerli görünüm ayarını (düz için 0) ve 3B için 1 alır.

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

## <a name="ccomcontrolbasegetambientautoclip"></a><a name="getambientautoclip"></a> CComControlBase:: Getambentautoclip

Kapsayıcının denetim görüntüleme alanının otomatik kırpmasını destekleyip desteklemediğini belirten bir bayrak alır DISPID_AMBIENT_AUTOCLIP.

```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```

### <a name="parameters"></a>Parametreler

*bAutoClip*<br/>
Özellik DISPID_AMBIENT_AUTOCLIP.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientbackcolor"></a><a name="getambientbackcolor"></a> CComControlBase:: Getambentbackcolor

Kapsayıcı tarafından tanımlanan tüm denetimler için çevresel arka plan rengi DISPID_AMBIENT_BACKCOLOR alır.

```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```

### <a name="parameters"></a>Parametreler

*Rengi*<br/>
Özellik DISPID_AMBIENT_BACKCOLOR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientcharset"></a><a name="getambientcharset"></a> CComControlBase:: Getambentcharset

Kapsayıcı tarafından tanımlanan tüm denetimler için çevresel karakter kümesini DISPID_AMBIENT_CHARSET alır.

```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```

### <a name="parameters"></a>Parametreler

*bstrCharSet*<br/>
Özellik DISPID_AMBIENT_CHARSET.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="ccomcontrolbasegetambientcodepage"></a><a name="getambientcodepage"></a> CComControlBase:: Getambentcodepage

Kapsayıcı tarafından tanımlanan tüm denetimlerin çevresel kod sayfasını DISPID_AMBIENT_CODEPAGE alır.

```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```

### <a name="parameters"></a>Parametreler

*ulCodePage*<br/>
Özellik DISPID_AMBIENT_CODEPAGE.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="ccomcontrolbasegetambientdisplayasdefault"></a><a name="getambientdisplayasdefault"></a> CComControlBase:: Getambentdisplayasdefault

Kapsayıcı, bu sitedeki denetimi varsayılan bir düğme olacak şekilde işaretlenmişse TRUE olan bir bayrak DISPID_AMBIENT_DISPLAYASDEFAULT alır ve bu nedenle bir düğme denetimi kendisini daha kalın bir kareyle çizmelidir.

```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```

### <a name="parameters"></a>Parametreler

*bDisplayAsDefault*<br/>
Özellik DISPID_AMBIENT_DISPLAYASDEFAULT.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientdisplayname"></a><a name="getambientdisplayname"></a> CComControlBase:: Getambentdisplayname

Kapsayıcının denetime sağladığı adı DISPID_AMBIENT_DISPLAYNAME alır.

```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```

### <a name="parameters"></a>Parametreler

*bstrDisplayName*<br/>
Özellik DISPID_AMBIENT_DISPLAYNAME.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientfont"></a><a name="getambientfont"></a> CComControlBase:: GetAmbientFont

Kapsayıcının çevresel arabirimine bir işaretçi alır `IFont` .

```
HRESULT GetAmbientFont(IFont** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*<br/>
Kapsayıcının çevresel [Ifazı](/windows/win32/api/ocidl/nn-ocidl-ifont) arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Özellik NULL ise, işaretçi NULL olur. İşaretçi NULL değilse, çağıran işaretçiyi serbest bırakmalıdır.

## <a name="ccomcontrolbasegetambientfontdisp"></a><a name="getambientfontdisp"></a> CComControlBase:: GetAmbientFontDisp

Kapsayıcının çevresel dağıtım arabirimine bir işaretçi alır `IFontDisp` .

```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parametreler

*ppFont*<br/>
Kapsayıcının çevresel [IFontDisp](/windows/win32/api/ocidl/nn-ocidl-ifontdisp) Dispatch arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Özellik NULL ise, işaretçi NULL olur. İşaretçi NULL değilse, çağıran işaretçiyi serbest bırakmalıdır.

## <a name="ccomcontrolbasegetambientforecolor"></a><a name="getambientforecolor"></a> CComControlBase:: Getambentforecolor

Kapsayıcı tarafından tanımlanan tüm denetimler için çevresel ön plan rengini DISPID_AMBIENT_FORECOLOR alır.

```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```

### <a name="parameters"></a>Parametreler

*ForeColor*<br/>
Özellik DISPID_AMBIENT_FORECOLOR.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientlocaleid"></a><a name="getambientlocaleid"></a> CComControlBase:: Getambentlocaleıd

Kapsayıcı tarafından kullanılan dilin tanımlayıcısını DISPID_AMBIENT_LOCALEID alır.

```
HRESULT GetAmbientLocaleID(LCID& lcid);
```

### <a name="parameters"></a>Parametreler

*lcid*<br/>
Özellik DISPID_AMBIENT_LOCALEID.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetim bu tanımlayıcıyı kullanarak Kullanıcı arabirimini farklı dillere uyarlayabilir.

## <a name="ccomcontrolbasegetambientmessagereflect"></a><a name="getambientmessagereflect"></a> CComControlBase:: Getambentmessagerefseç

Kapsayıcının pencere iletilerini (gibi) olay olarak almak isteyip istemediğini belirten bir bayrak alır DISPID_AMBIENT_MESSAGEREFLECT `WM_DRAWITEM` .

```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```

### <a name="parameters"></a>Parametreler

*Bmessagerefseç*<br/>
Özellik DISPID_AMBIENT_MESSAGEREFLECT.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientpalette"></a><a name="getambientpalette"></a> CComControlBase:: Getambentpalette

Kapsayıcının HPALETTE erişmek için kullanılan DISPID_AMBIENT_PALETTE alır.

```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```

### <a name="parameters"></a>Parametreler

*hPalette*<br/>
Özellik DISPID_AMBIENT_PALETTE.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientproperty"></a><a name="getambientproperty"></a> CComControlBase:: Getambentproperty

*DISPID* tarafından belirtilen kapsayıcı özelliğini alır.

```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Alınacak kapsayıcı özelliğinin tanımlayıcısı.

*l*<br/>
Özelliği almak için değişken.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

ATL belirli özellikleri almak için bir dizi yardımcı işlevi sağlamıştır, örneğin, [CComControlBase:: Getambentbackcolor](#getambientbackcolor). Uygun bir yöntem yoksa, kullanın `GetAmbientProperty` .

## <a name="ccomcontrolbasegetambientrighttoleft"></a><a name="getambientrighttoleft"></a> CComControlBase:: GetAmbientRightToLeft

İçeriğin kapsayıcı tarafından gösterileceği yönü DISPID_AMBIENT_RIGHTTOLEFT alır.

```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```

### <a name="parameters"></a>Parametreler

*Parlak Ttoleft*<br/>
Özellik DISPID_AMBIENT_RIGHTTOLEFT. İçerik sağdan sola görüntüleniyorsa TRUE, sağdan sola görüntüleniyorsa FALSE olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="ccomcontrolbasegetambientscaleunits"></a><a name="getambientscaleunits"></a> CComControlBase:: Getambentscaleunits

Etiketleme görüntüleri için kapsayıcının çevresel birimlerinin (inç veya santimetre gibi) DISPID_AMBIENT_SCALEUNITS alır.

```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```

### <a name="parameters"></a>Parametreler

*bstrScaleUnits*<br/>
Özellik DISPID_AMBIENT_SCALEUNITS.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientshowgrabhandles"></a><a name="getambientshowgrabhandles"></a> CComControlBase:: Getambentshowgrabhandles

Kapsayıcının, denetimin etkin olduğunda kendi kendine yönelik tutamaçları görüntülemesine izin verip içermediğini belirten bir bayrak alır DISPID_AMBIENT_SHOWGRABHANDLES.

```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```

### <a name="parameters"></a>Parametreler

*bShowGrabHandles*<br/>
Özellik DISPID_AMBIENT_SHOWGRABHANDLES.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientshowhatching"></a><a name="getambientshowhatching"></a> CComControlBase:: Getambentshowhadikiş

Kapsayıcının denetimin kullanıcı arabirimi etkinken denetimin kendisini bir hagesle görüntülemesine izin verip içermediğini belirten bir bayrak alır DISPID_AMBIENT_SHOWHATCHING.

```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```

### <a name="parameters"></a>Parametreler

*Bshowhadikiş*<br/>
Özellik DISPID_AMBIENT_SHOWHATCHING.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambientsupportsmnemonics"></a><a name="getambientsupportsmnemonics"></a> CComControlBase:: GetAmbientSupportsMnemonics

Kapsayıcının klavye anımsatıcılarını destekleyip desteklemediğini gösteren bir bayrak DISPID_AMBIENT_SUPPORTSMNEMONICS alır.

```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```

### <a name="parameters"></a>Parametreler

*bSupportsMnemonics*<br/>
Özellik DISPID_AMBIENT_SUPPORTSMNEMONICS.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambienttextalign"></a><a name="getambienttextalign"></a> CComControlBase:: Getambenttextalign

Kapsayıcının tercih ettiği metin hizalamasını DISPID_AMBIENT_TEXTALIGN alır: Genel hizalama için 0 (rakamlar sağ, metin sola), sol hizalama için 1, orta hizalama için 2 ve sağ hizalama için 3.

```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```

### <a name="parameters"></a>Parametreler

*nTextAlign*<br/>
Özellik DISPID_AMBIENT_TEXTALIGN.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetambienttoptobottom"></a><a name="getambienttoptobottom"></a> CComControlBase:: Getambenttoptobottom

İçeriğin kapsayıcı tarafından gösterileceği yönü DISPID_AMBIENT_TOPTOBOTTOM alır.

```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```

### <a name="parameters"></a>Parametreler

*bTopToBottom*<br/>
Özellik DISPID_AMBIENT_TOPTOBOTTOM. Metin üstten en alta görüntüleniyorsa TRUE, en alta ise FALSE olarak ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="ccomcontrolbasegetambientuidead"></a><a name="getambientuidead"></a> CComControlBase:: Getambentuıdead

Kapsayıcının denetimin kullanıcı arabirimi eylemlerine yanıt vermesini isteyip istemediğini belirten bir bayrak olan DISPID_AMBIENT_UIDEAD alır.

```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```

### <a name="parameters"></a>Parametreler

*Buıdead*<br/>
Özellik DISPID_AMBIENT_UIDEAD.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

TRUE ise denetim yanıt vermemelidir. Bu bayrak DISPID_AMBIENT_USERMODE bayrağını ne olursa olsun geçerlidir. Bkz. [CComControlBase:: Getambentkullanıcı modu](#getambientusermode).

## <a name="ccomcontrolbasegetambientusermode"></a><a name="getambientusermode"></a> CComControlBase:: Getambentkullanıcı modu

Kapsayıcının çalışma modunda (TRUE) veya tasarım modunda (FALSE) olup olmadığını belirten bir bayrak DISPID_AMBIENT_USERMODE alır.

```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```

### <a name="parameters"></a>Parametreler

*bUserMode*<br/>
Özellik DISPID_AMBIENT_USERMODE.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

## <a name="ccomcontrolbasegetdirty"></a><a name="getdirty"></a> CComControlBase:: GetDirty

Veri üyesinin değerini döndürür `m_bRequiresSave` .

```
BOOL GetDirty();
```

### <a name="return-value"></a>Dönüş Değeri

[M_bRequiresSave](#m_brequiressave)veri üyesinin değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu değer [CComControlBase:: SetDirty](#setdirty)kullanılarak ayarlanır.

## <a name="ccomcontrolbasegetzoominfo"></a><a name="getzoominfo"></a> CComControlBase:: GetZoomInfo

Yerinde düzenlenmek üzere etkinleştirilen bir denetim için yakınlaştırma faktörünün pay ve paydasın x ve y değerlerini alır.

```cpp
void GetZoomInfo(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*içerik*<br/>
Yakınlaştırma faktörünün pay ve paydasını tutacağız yapı. Daha fazla bilgi için bkz. [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md).

### <a name="remarks"></a>Açıklamalar

Yakınlaştırma faktörü, denetimin doğal boyutunun geçerli kapsamına oranını sağlar.

## <a name="ccomcontrolbaseinplaceactivate"></a><a name="inplaceactivate"></a> CComControlBase:: InPlaceActivate

Denetimin etkin olmayan durumdan, *ıverb* 'teki fiilin gösterdiği herhangi bir duruma geçişine neden olur.

```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```

### <a name="parameters"></a>Parametreler

*ıverb*<br/>
[IOleObjectImpl::D oVerb](../../atl/reference/ioleobjectimpl-class.md#doverb)tarafından gerçekleştirilecek eylemi belirten değer.

*prcPosRect*<br/>
Yerinde denetimin konumuna yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, etkinleştirmeden önce, denetimin bir istemci sitesine sahip olup olmadığını denetler, denetimin ne kadarının görünür olduğunu denetler ve üst penceredeki denetimin konumunu alır. Denetim etkinleştirildikten sonra, bu yöntem denetimin kullanıcı arabirimini etkinleştirir ve kapsayıcıya denetimi görünür hale getirir.

Bu yöntem ayrıca `IOleInPlaceSite` `IOleInPlaceSiteEx` Denetim için bir, veya `IOleInPlaceSiteWindowless` arabirim işaretçisi alır ve bunu denetim sınıfının veri üyesi [CComControlBase:: m_spInPlaceSite](#m_spinplacesite)içinde depolar. [CComControlBase](#m_binplacesiteex):: m_bInPlaceSiteEx, CComControlBase: [: m_bWndLess](#m_bwndless), ccomcontrolbase:: [M_bWasOnceWindowless](#m_bwasoncewindowless)ve [CComControlBase:: m_bNegotiatedWnd](#m_bnegotiatedwnd) denetim sınıfı veri üyeleri uygun şekilde doğru olarak ayarlanmıştır.

## <a name="ccomcontrolbaseinternalgetsite"></a><a name="internalgetsite"></a> CComControlBase:: ınternalgetsite

Tanımlanan arabirime yönelik bir işaretçinin denetim sitesini sorgulamak için bu yöntemi çağırın.

```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```

### <a name="parameters"></a>Parametreler

*riıd*<br/>
*PpUnkSite* içinde döndürülmesi gereken ARABIRIM işaretçisinin IID 'si.

*Ppunksıte*<br/>
*Riid* içinde istenen arabirim işaretçisini alan işaretçi değişkeninin adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Site, *riid* içinde istenen arabirimi destekliyorsa, Işaretçi *ppUnkSite* aracılığıyla döndürülür. Aksi halde *Ppunksıte* null olarak ayarlanır.

## <a name="ccomcontrolbasem_bautosize"></a><a name="m_bautosize"></a> CComControlBase:: m_bAutoSize

Denetimin başka bir boyut olmadığını belirten bayrak.

```
unsigned m_bAutoSize:1;
```

### <a name="remarks"></a>Açıklamalar

Bu bayrak tarafından denetlenir `IOleObjectImpl::SetExtent` ve true ise işlevin E_FAIL döndürmesine neden olur.

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

ATL Denetim Sihirbazı 'nın [Stok özellikleri](../../atl/reference/stock-properties-atl-control-wizard.md) sekmesine **otomatik boyut** seçeneğini eklerseniz, sihirbaz otomatik olarak bu veri üyesini denetim sınıfınızda oluşturur, özellik için Put ve Get yöntemlerini oluşturur ve özellik değiştiğinde kapsayıcıyı otomatik olarak bildirmek Için [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) 'yi destekler.

## <a name="ccomcontrolbasem_bdrawfromnatural"></a><a name="m_bdrawfromnatural"></a> CComControlBase:: m_bDrawFromNatural

`IDataObjectImpl::GetData`' In ' ı belirten ve `CComControlBase::GetZoomInfo` denetim boyutunu from yerine olarak ayarlaması gerektiğini belirten bayrak `m_sizeNatural` `m_sizeExtent` .

```
unsigned m_bDrawFromNatural:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_bdrawgetdatainhimetric"></a><a name="m_bdrawgetdatainhimetric"></a> CComControlBase:: m_bDrawGetDataInHimetric

`IDataObjectImpl::GetData`Çizim sırasında piksel değil, HIMETRIK birimleri kullanması gerektiğini belirten bayrak.

```
unsigned m_bDrawGetDataInHimetric:1;
```

### <a name="remarks"></a>Açıklamalar

Her mantıksal HIMETRIK birimi 0,01 milimetredir.

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_binplaceactive"></a><a name="m_binplaceactive"></a> CComControlBase:: m_bInPlaceActive

Denetimin yerinde etkin olduğunu belirten bayrak.

```
unsigned m_bInPlaceActive:1;
```

### <a name="remarks"></a>Açıklamalar

Bu, denetimin görünür olduğu ve pencere, varsa, menüleri ve araç çubuklarının etkin olmaması anlamına gelir. `m_bUIActive`Bayrak, denetimin menü gibi Kullanıcı arabiriminin de etkin olduğunu gösterir.

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_binplacesiteex"></a><a name="m_binplacesiteex"></a> CComControlBase:: m_bInPlaceSiteEx

Kapsayıcının, `IOleInPlaceSiteEx` penceresiz ve titreşimsiz denetimler gibi arabirim ve OCX96 denetim özelliklerini desteklediğini belirten bayrak.

```
unsigned m_bInPlaceSiteEx:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

Veri üyesi, `m_spInPlaceSite` ve bayraklarının değerine [](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite)bağlı olarak bir IOleInPlaceSiteEx veya [ıoleınplacesitepenceresiz](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arabirimine işaret eder [](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex) `m_bWndLess` `m_bInPlaceSiteEx` . ( `m_bNegotiatedWnd` İşaretçinin geçerli olması için veri ÜYESININ doğru olması gerekir `m_spInPlaceSite` .)

`m_bWndLess`Yanlış ise ve `m_bInPlaceSiteEx` true ise `m_spInPlaceSite` bir `IOleInPlaceSiteEx` arabirim işaretçisidir. Bu üç veri üyesi arasındaki ilişkiyi gösteren tablo için bkz. [m_spInPlaceSite](#m_spinplacesite) .

## <a name="ccomcontrolbasem_bnegotiatedwnd"></a><a name="m_bnegotiatedwnd"></a> CComControlBase:: m_bNegotiatedWnd

Denetimin, OCX96 denetim özellikleri (titreşimsiz ve Penceresiz denetimler gibi) için destek hakkında kapsayıcınıza ve denetimin pencereli mi yoksa penceresiz mi olduğunu belirten bayrak.

```
unsigned m_bNegotiatedWnd:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

`m_bNegotiatedWnd`İşaretçinin geçerli olması için BAYRAĞıN doğru olması gerekir `m_spInPlaceSite` .

## <a name="ccomcontrolbasem_brecomposeonresize"></a><a name="m_brecomposeonresize"></a> CComControlBase:: m_bRecomposeOnResize

Kapsayıcı denetimin görüntüleme boyutunu değiştirdiğinde denetimin sunumunu yeniden oluşturmak istediğini belirten bayrak.

```
unsigned m_bRecomposeOnResize:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

Bu bayrak, [IOleObjectImpl:: SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) tarafından DENETLENIR ve true ise, `SetExtent` Görünüm değişikliğini kapsayıcısına bildirir. Bu bayrak ayarlandıysa, [Olemisc](/windows/win32/api/oleidl/ne-oleidl-olemisc) numaralandırmasında OLEMISC_RECOMPOSEONRESIZE bit de ayarlanmalıdır.

## <a name="ccomcontrolbasem_brequiressave"></a><a name="m_brequiressave"></a> CComControlBase:: m_bRequiresSave

Denetimin son kaydedduğundan bu yana değiştiğini belirten bayrak.

```
unsigned m_bRequiresSave:1;
```

### <a name="remarks"></a>Açıklamalar

Değeri `m_bRequiresSave` [CComControlBase:: SetDirty](#setdirty) Ile ayarlanabilir ve [CComControlBase:: GetDirty](#getdirty)ile elde edilebilir.

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_bresizenatural"></a><a name="m_bresizenatural"></a> CComControlBase:: m_bResizeNatural

Kapsayıcı denetimin görüntüleme boyutunu değiştirdiğinde denetimin doğal kapsamını (ölçeklendirilmemiş fiziksel boyut) yeniden boyutlandırmak istediğini belirten bayrak.

```
unsigned m_bResizeNatural:1;
```

### <a name="remarks"></a>Açıklamalar

Bu bayrak tarafından denetlenir `IOleObjectImpl::SetExtent` ve true ise, öğesine geçirilen boyut `SetExtent` atanır `m_sizeNatural` .

Öğesine geçirilen boyut, `SetExtent` değerine bakılmaksızın her zaman öğesine atanır `m_sizeExtent` `m_bResizeNatural` .

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_buiactive"></a><a name="m_buiactive"></a> CComControlBase:: m_bUIActive

Denetimin, menüler ve araç çubukları gibi kullanıcı arabirimini belirten bayrak etkin.

```
unsigned m_bUIActive:1;
```

### <a name="remarks"></a>Açıklamalar

`m_bInPlaceActive`Bayrak, denetimin etkin olduğunu, ancak kullanıcı arabiriminin etkin olduğunu gösterir.

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_busingwindowrgn"></a><a name="m_busingwindowrgn"></a> CComControlBase:: m_bUsingWindowRgn

Denetimin kapsayıcı tarafından sağlanan pencere bölgesini kullandığını belirten bayrak.

```
unsigned m_bUsingWindowRgn:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_bwasoncewindowless"></a><a name="m_bwasoncewindowless"></a> CComControlBase:: m_bWasOnceWindowless

Denetimin penceresiz olduğunu belirten bayrak, ancak şu anda penceresiz olabilir veya görünmeyebilir.

```
unsigned m_bWasOnceWindowless:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_bwindowonly"></a><a name="m_bwindowonly"></a> CComControlBase:: m_bWindowOnly

Kapsayıcı penceresiz denetimleri desteklese bile denetimin pencereli olması gerektiğini belirten bayrak.

```
unsigned m_bWindowOnly:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_bwndless"></a><a name="m_bwndless"></a> CComControlBase:: m_bWndLess

Denetimin penceresiz olduğunu belirten bayrak.

```
unsigned m_bWndLess:1;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

Veri üyesi, `m_spInPlaceSite` ve CComControlBase:: m_bInPlaceSiteEx bayraklarının değerine bağlı olarak bir IOleInPlaceSiteEx veya [ıoleınplacesitepenceresiz](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arabirimine işaret eder [](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite) [](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex) `m_bWndLess` . [](#m_binplacesiteex) (CComControlBase [:: m_bNegotiatedWnd](#m_bnegotiatedwnd) veri üyesi [ccomcontrolbase:: m_spInPlaceSite](#m_spinplacesite) IŞARETÇISININ geçerli olması için true olmalıdır.)

`m_bWndLess`True ise `m_spInPlaceSite` bir `IOleInPlaceSiteWindowless` arabirim işaretçisidir. Bu veri üyeleri arasındaki tüm ilişkiyi gösteren bir tablo için bkz. [CComControlBase:: m_spInPlaceSite](#m_spinplacesite) .

## <a name="ccomcontrolbasem_hwndcd"></a><a name="m_hwndcd"></a> CComControlBase:: m_hWndCD

Denetimle ilişkili pencere tanıtıcısına bir başvuru içerir.

```
HWND& m_hWndCD;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_nfreezeevents"></a><a name="m_nfreezeevents"></a> CComControlBase:: m_nFreezeEvents

Bir olay çözme (olayların kabulü) olmadan, kapsayıcının dondurulmuş olaylara (olayları kabul etmek için reddedildi) sahip olduğu sayıda sayı.

```
short m_nFreezeEvents;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_rcpos"></a><a name="m_rcpos"></a> CComControlBase:: m_rcPos

Denetimin piksel cinsinden konumu, kapsayıcının koordinatları cinsinden ifade edilir.

```
RECT m_rcPos;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_sizeextent"></a><a name="m_sizeextent"></a> CComControlBase:: m_sizeExtent

Belirli bir görüntü için HIMETRIK birimlerde (her birim 0,01 milimetre) denetimin kapsamı.

```
SIZE m_sizeExtent;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

Bu boyut, ekran tarafından ölçeklendirilir. Denetimin fiziksel boyutu `m_sizeNatural` veri üyesinde belirtilir ve sabittir.

[AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)genel işlevi ile boyutu piksellere dönüştürebilirsiniz.

## <a name="ccomcontrolbasem_sizenatural"></a><a name="m_sizenatural"></a> CComControlBase:: m_sizeNatural

Denetimin HIMETRIK birimlerde fiziksel boyutu (her birim 0,01 milimetre 'dir).

```
SIZE m_sizeNatural;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

Bu boyut sabittir,, içindeki boyut `m_sizeExtent` görüntüleme ile ölçeklendirilir.

[AtlHiMetricToPixel](pixel-himetric-conversion-global-functions.md#atlhimetrictopixel)genel işlevi ile boyutu piksellere dönüştürebilirsiniz.

## <a name="ccomcontrolbasem_spadvisesink"></a><a name="m_spadvisesink"></a> CComControlBase:: m_spAdviseSink

Kapsayıcıda doğrudan danışmanlık bağlantısına yönelik bir işaretçi (kapsayıcının [ıvısesink](/windows/win32/api/objidl/nn-objidl-iadvisesink)).

```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_spambientdispatch"></a><a name="m_spambientdispatch"></a> CComControlBase:: m_spAmbientDispatch

`CComDispatchDriver`Nesnenin özelliklerini bir işaretçi aracılığıyla almanıza ve ayarlamanıza imkan tanıyan bir nesne `IDispatch` .

```
CComDispatchDriver m_spAmbientDispatch;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_spclientsite"></a><a name="m_spclientsite"></a> CComControlBase:: m_spClientSite

Kapsayıcının içindeki denetimin istemci sitesine yönelik bir işaretçi.

```
CComPtr<IOleClientSite>
    m_spClientSite;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

## <a name="ccomcontrolbasem_spdataadviseholder"></a><a name="m_spdataadviseholder"></a> CComControlBase:: m_spDataAdviseHolder

Veri nesneleri ve öneri havuzları arasında danışmanlık bağlantılarını tutmak için standart bir yol sağlar.

```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

Veri nesnesi, verileri aktarabilen ve bu, yöntemleri verilerin biçimini ve aktarım ortamını belirten [IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)'yi uygulayan bir denetimdir.

Arabirim, `m_spDataAdviseHolder` kapsayıcıya yönelik danışmanlık bağlantıları oluşturmak ve silmek Için [ıdataobject::D Advise](/windows/win32/api/objidl/nf-objidl-idataobject-dadvise) ve [IDataObject::D Unadvise](/windows/win32/api/objidl/nf-objidl-idataobject-dunadvise) yöntemlerini uygular. Denetimin kapsayıcısının [ıvısesink](/windows/win32/api/objidl/nn-objidl-iadvisesink) arabirimini destekleyerek bir öneri havuzu uygulaması gerekir.

## <a name="ccomcontrolbasem_spinplacesite"></a><a name="m_spinplacesite"></a> CComControlBase:: m_spInPlaceSite

Kapsayıcının [IOleInPlaceSite](/windows/win32/api/oleidl/nn-oleidl-ioleinplacesite), [IOleInPlaceSiteEx](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesiteex)veya [ıoleınplacesitepenceresiz](/windows/win32/api/ocidl/nn-ocidl-ioleinplacesitewindowless) arabirim işaretçisine yönelik bir işaretçi.

```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

`m_spInPlaceSite`İşaretçi yalnızca [M_BNEGOTIATEDWND](#m_bnegotiatedwnd) bayrağı true olduğunda geçerlidir.

Aşağıdaki tabloda, `m_spInPlaceSite` işaretçi türünün [m_bWndLess](#m_bwndless) ve [m_bInPlaceSiteEx](#m_binplacesiteex) veri üyesi bayraklarına nasıl bağlı olduğu gösterilmektedir:

|m_spInPlaceSite türü|m_bWndLess değeri|m_bInPlaceSiteEx değeri|
|---------------------------|-----------------------|-----------------------------|
|`IOleInPlaceSiteWindowless`|TRUE|TRUE veya FALSE|
|`IOleInPlaceSiteEx`|FALSE|TRUE|
|`IOleInPlaceSite`|FALSE|FALSE|

## <a name="ccomcontrolbasem_spoleadviseholder"></a><a name="m_spoleadviseholder"></a> CComControlBase:: m_spOleAdviseHolder

Danışmanlık bağlantılarını tutan bir yol için standart bir uygulama sağlar.

```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu veri üyesini denetim sınıfınız içinde kullanmak için, onu denetim sınıfınıza bir veri üyesi olarak bildirmeniz gerekir. Taban sınıftaki bir Union içinde bildirildiği için denetim sınıfınız bu veri üyesini taban sınıftan almayacaktır.

Arabirim, `m_spOleAdviseHolder` kapsayıcıya yönelik danışmanlık bağlantıları oluşturmak ve silmek Için [IOleObject:: Advise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-advise) ve [IOleObject:: Unadvise](/windows/win32/api/oleidl/nf-oleidl-ioleobject-unadvise) yöntemlerini uygular. Denetimin kapsayıcısının [ıvısesink](/windows/win32/api/objidl/nn-objidl-iadvisesink) arabirimini destekleyerek bir öneri havuzu uygulaması gerekir.

## <a name="ccomcontrolbaseondraw"></a><a name="ondraw"></a> CComControlBase:: OnDraw

Denetiminizi çizmek için bu yöntemi geçersiz kılın.

```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*içerik*<br/>
Çizim en boy, denetim sınırları ve çizimin iyileştirilme gibi çizim bilgilerini içeren [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) yapısına yönelik bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `OnDraw` [CComControlBase:: OnDrawAdvanced](#ondrawadvanced)içinde ayarlanan bayraklara bağlı olarak, cihaz bağlamını siler veya geri yükler ya da hiçbir şey yapmaz.

`OnDraw`Atl Denetim Sihirbazı ile denetiminizi oluştururken denetim sınıfınıza bir yöntem otomatik olarak eklenir. Sihirbazın varsayılan `OnDraw` etiketi "ATL 8,0" etiketiyle bir dikdörtgen çizer.

### <a name="example"></a>Örnek

[CComControlBase:: Getambentappearance](#getambientappearance)örneğine bakın.

## <a name="ccomcontrolbaseondrawadvanced"></a><a name="ondrawadvanced"></a> CComControlBase:: OnDrawAdvanced

Varsayılan değer, `OnDrawAdvanced` Çizim için Normalleştirilmemiş bir cihaz bağlamı hazırlar, sonra denetim sınıfınızın `OnDraw` yöntemini çağırır.

```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```

### <a name="parameters"></a>Parametreler

*içerik*<br/>
Çizim en boy, denetim sınırları ve çizimin iyileştirilme gibi çizim bilgilerini içeren [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) yapısına yönelik bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Kapsayıcı tarafından geçirilen cihaz bağlamını normalleştirmeden kabul etmek istiyorsanız bu yöntemi geçersiz kılın.

Daha fazla ayrıntı için bkz. [CComControlBase:: OnDraw](#ondraw) .

## <a name="ccomcontrolbaseonkillfocus"></a><a name="onkillfocus"></a> CComControlBase:: OnKillFocus

Denetimin yerinde etkin olduğunu ve geçerli bir denetim sitesine sahip olduğunu denetler, sonra kapsayıcıya denetimin odağa sahip olduğunu bildirir.

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

*Bişlenmiş*<br/>
Pencere iletisinin başarıyla işlendiğini belirten bayrak. Varsayılan değer FALSE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

## <a name="ccomcontrolbaseonmouseactivate"></a><a name="onmouseactivate"></a> CComControlBase:: OnMouseActivate

Kullanıcı ARABIRIMININ Kullanıcı modunda olduğunu denetler, sonra denetimi etkinleştirir.

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

*Bişlenmiş*<br/>
Pencere iletisinin başarıyla işlendiğini belirten bayrak. Varsayılan değer FALSE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

## <a name="ccomcontrolbaseonpaint"></a><a name="onpaint"></a> CComControlBase:: OnPaint

Kapsayıcıyı boyama için hazırlar, denetimin istemci alanını alır, sonra Denetim sınıfının `OnDrawAdvanced` yöntemini çağırır.

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
Var olan bir HDC.

*lParam*<br/>
Ayrılmış.

*lResult*<br/>
Ayrılmış.

### <a name="return-value"></a>Dönüş Değeri

Her zaman sıfır döndürür.

### <a name="remarks"></a>Açıklamalar

*WParam* null değilse, `OnPaint` geçerli bir HDC Içerdiğini varsayar ve [CComControlBase:: m_hWndCD](#m_hwndcd)yerine bunu kullanır.

## <a name="ccomcontrolbaseonsetfocus"></a><a name="onsetfocus"></a> CComControlBase:: OnSetFocus

Denetimin yerinde etkin olduğunu ve geçerli bir denetim sitesine sahip olduğunu denetler ve sonra denetimin odağa sahip olduğu kapsayıcıyı bilgilendirir.

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

*Bişlenmiş*<br/>
Pencere iletisinin başarıyla işlendiğini belirten bayrak. Varsayılan değer FALSE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Her zaman 1 döndürür.

### <a name="remarks"></a>Açıklamalar

Kapsayıcıya, denetimin odak aldığını belirten bir bildirim gönderir.

## <a name="ccomcontrolbasepretranslateaccelerator"></a><a name="pretranslateaccelerator"></a> CComControlBase::P reTranslateAccelerator

Kendi klavye Hızlandırıcısı işleyicilerinizi sağlamak için bu yöntemi geçersiz kılın.

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

## <a name="ccomcontrolbasesendonclose"></a><a name="sendonclose"></a> CComControlBase:: SendOnClose

Denetim kapatılmış olan öneri sahibine kayıtlı tüm danışmanlık havuzlarını bilgilendirir.

```
HRESULT SendOnClose();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin danışmanlık havuzlarını kapattığını belirten bir bildirim gönderir.

## <a name="ccomcontrolbasesendondatachange"></a><a name="sendondatachange"></a> CComControlBase:: SendOnDataChange

Denetim verilerinin değiştiği öneri sahibine kayıtlı tüm danışmanlık havuzlarını bilgilendirir.

```
HRESULT SendOnDataChange(DWORD advf = 0);
```

### <a name="parameters"></a>Parametreler

*ADVF*<br/>
[Ivsesink:: OnDataChange](/windows/win32/api/objidl/nf-objidl-iadvisesink-ondatachange) çağrısının nasıl yapıldığını belirten öneri bayrakları. Değerler, [ADVF](/windows/win32/api/objidl/ne-objidl-advf) numaralandırmasından alınır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

## <a name="ccomcontrolbasesendonrename"></a><a name="sendonrename"></a> CComControlBase:: SendOnRename

Tüm danışmanlık havuzlarını, denetimin yeni bir adı olan öneri sahibine kayıtlı olduğunu bildirir.

```
HRESULT SendOnRename(IMoniker* pmk);
```

### <a name="parameters"></a>Parametreler

*süreyi*<br/>
Denetimin yeni adının işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin bilinen adının değiştiğini belirten bir bildirim gönderir.

## <a name="ccomcontrolbasesendonsave"></a><a name="sendonsave"></a> CComControlBase:: SendOnSave

Tüm danışmanlık havuzları ' nın, denetimin kaydedildiği öneri sahibine kayıtlı olduğunu bildirir.

```
HRESULT SendOnSave();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Denetimin verilerini kaydettiği bir bildirim gönderir.

## <a name="ccomcontrolbasesendonviewchange"></a><a name="sendonviewchange"></a> CComControlBase:: SendOnViewChange

Tüm kayıtlı danışmanlık havuzlarını denetim görünümü ' nin değiştiğini bildirir.

```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```

### <a name="parameters"></a>Parametreler

*dwAspect*<br/>
Denetimin en boy veya görünümü.

*Lindex*<br/>
Görünümün değiştiği bölüm. Yalnızca-1 geçerlidir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

`SendOnViewChange`[ıvısesink:: OnViewChange](/windows/win32/api/objidl/nf-objidl-iadvisesink-onviewchange)öğesini çağırır. Şu anda desteklenen *Lindex* 'in tek değeri-1 ' dir. Bu, tüm görünümün ilgi olduğunu gösterir.

## <a name="ccomcontrolbasesetcontrolfocus"></a><a name="setcontrolfocus"></a> CComControlBase:: SetControlFocus

Klavye odağını denetimden veya denetiminden kaldırır.

```
BOOL SetControlFocus(BOOL bGrab);
```

### <a name="parameters"></a>Parametreler

*BIN*<br/>
DOĞRU ise, klavye odağını çağırma denetimine ayarlar. FALSE ise, odağı içeren, çağırma denetiminden klavye odağını kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Denetim başarıyla odağı alırsa TRUE döndürür; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Pencereli bir denetim için, Windows API işlevi [SetFocus](/windows/win32/api/winuser/nf-winuser-setfocus) çağırılır. Penceresiz bir denetim için, [ıoleınplacesitepenceresiz:: SetFocus](/windows/win32/api/ocidl/nf-ocidl-ioleinplacesitewindowless-setfocus) çağırılır. Bu çağrı sayesinde, penceresiz bir denetim klavye odağını edinir ve pencere iletilerine yanıt verebilir.

## <a name="ccomcontrolbasesetdirty"></a><a name="setdirty"></a> CComControlBase:: SetDirty

Veri üyesini `m_bRequiresSave` *bDirty* içindeki değere ayarlar.

```cpp
void SetDirty(BOOL bDirty);
```

### <a name="parameters"></a>Parametreler

*bDirty*<br/>
[CComControlBase:: m_bRequiresSave](#m_brequiressave)veri üyesinin değeri.

### <a name="remarks"></a>Açıklamalar

`SetDirty(TRUE)` son kaydedildiği zamandan sonra denetimin değiştiğini işaretlemek için çağrılmalıdır. Değeri `m_bRequiresSave` [CComControlBase:: GetDirty](#getdirty)ile alınır.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
