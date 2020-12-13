---
description: 'Daha fazla bilgi edinin: CMFCVisualManagerWindows7 Class'
title: CMFCVisualManagerWindows7 sınıfı
ms.date: 03/27/2019
f1_keywords:
- CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::OnFillMenuImageRect
helpviewer_keywords:
- CMFCVisualManagerWindows7 Class [MFC]
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
ms.openlocfilehash: 108d4144bbcfbfcb82d91678611435f14365302e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331632"
---
# <a name="cmfcvisualmanagerwindows7-class"></a>CMFCVisualManagerWindows7 sınıfı

, `CMFCVisualManagerWindows7` Bir uygulamanın Windows 7 uygulamasının görünümünü sağlar.

## <a name="syntax"></a>Syntax

```
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7)|Varsayılan Oluşturucu.|
|[CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7](#_dtorcmfcvisualmanagerwindows7)|Varsayılan yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCVisualManagerWindows7::CleanStyle`|Geçerli görsel stilini temizler ve varsayılan görsel stilini sıfırlar.|
|`CMFCVisualManagerWindows7::CleanUp`|Kullanıcı arabirimindeki tüm nesneleri temizler ve menüleri sıfırlar.|
|`CMFCVisualManagerWindows7::DrawNcBtn`|Çerçevedeki istemci olmayan alanda bir düğme çizer. Framework, pencere çerçevesinin sağ üst köşesindeki Simge durumuna küçült, Ekranı Kapla, kapat ve geri yükle düğmelerini çizmek için bu yöntemi kullanır. Bu yöntem yalnızca program bir tema kullandığında çağırılır `Aero` .|
|`CMFCVisualManagerWindows7::DrawNcText`|Çerçevedeki istemci olmayan alanda metin çizer. Framework, çerçeve penceresinin üst kısmındaki başlık çubuğunda uygulama başlığını çizmek için bu yöntemi kullanır.|
|`CMFCVisualManagerWindows7::DrawSeparator`|[CMFCToolBar sınıfında](../../mfc/reference/cmfctoolbar-class.md)bir ayırıcı çizer.|
|`CMFCVisualManagerWindows7::GetRibbonBar`|Kullanıcı arabirimiyle ilişkili [CMFCRibbonBar sınıfını](../../mfc/reference/cmfcribbonbar-class.md) alır.|
|[CMFCVisualManagerWindows7:: GetRibbonEditBackgroundColor](#getribboneditbackgroundcolor)|Bir şerit düzenleme kutusu arka plan rengi alır.|
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|[CMFCVisualManager:: GetRibbonPopupBorderSize](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize) geçersiz kılar|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|[CMFCVisualManager:: GetRibbonQuickAccessToolBarChevronOffset](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset) geçersiz kılar|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|[CMFCVisualManager:: GetRibbonQuickAccessToolBarRightMargin](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin) geçersiz kılınır|
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|[CMFCVisualManagerWindows:: ıshighlightwholemenuitem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem) geçersiz kılar|
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|[CMFCVisualManager:: IsOwnerDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck) geçersiz kılar|
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Bir nesnenin `CMFCRibbonBar` mevcut ve görünür olup olmadığını belirler.|
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|[CMFCVisualManagerWindows:: OnDrawButtonBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|[CMFCVisualManagerWindows:: OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|[CMFCVisualManagerWindows:: OnDrawComboDropButton](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|[CMFCVisualManager:: Ondrawdefaultribbonımage](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|[CMFCVisualManagerWindows:: OnDrawMenuBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|[CMFCVisualManager:: OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|[CMFCVisualManager:: OnDrawMenuLabel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Kılma `CMFCVisualManager::OnDrawRadioButton`|
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|[CMFCVisualManager:: OnDrawRibbonApplicationButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|[CMFCVisualManager:: OnDrawRibbonButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|[CMFCVisualManager:: OnDrawRibbonCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|[CMFCVisualManager:: OnDrawRibbonCaptionButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|[CMFCVisualManager:: OnDrawRibbonCategory](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|[CMFCVisualManager:: OnDrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab) üzerine yazar|
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|[CMFCVisualManager:: Ondrawribbondefaultbölmesi düğmesini](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|[CMFCVisualManager:: Ondrawribbongallerbutton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Kılma `CMFCVisualManager::OnDrawRibbonLaunchButton`|
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|[CMFCVisualManager:: OnDrawRibbonMenuCheckFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|[CMFCVisualManager:: OnDrawRibbonPanel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel) 'i geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|[CMFCVisualManager:: OnDrawRibbonPanelCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|[CMFCVisualManager:: OnDrawRibbonProgressBar](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar) geçersiz kılınır|
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|[CMFCVisualManager:: OnDrawRibbonRecentFilesFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|[CMFCVisualManager:: OnDrawRibbonSliderChannel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|[CMFCVisualManager:: OnDrawRibbonSliderThumb](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|[CMFCVisualManager:: OnDrawRibbonSliderZoomButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|[CMFCVisualManager:: OnDrawRibbonStatusBarPane](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|[CMFCVisualManager:: OnDrawRibbonTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|[CMFCVisualManagerWindows:: OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnFillBarBackground`|[CMFCVisualManagerWindows:: OnFillBarBackground](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|[CMFCVisualManagerWindows:: Onfillbuttoniç](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior) geçersiz kılar|
|[CMFCVisualManagerWindows7:: OnFillMenuImageRect](#onfillmenuimagerect)|Framework, menü öğesi görüntülerinin etrafında alan doldururken bu yöntemi çağırır.|
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|[CMFCVisualManager:: OnFillRibbonButton](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|[CMFCVisualManager:: OnFillRibbonQuickAccessToolBarPopup](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|[CMFCVisualManagerWindows:: OnHighlightMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnNcActivate`|[CMFCVisualManager:: Onncackıda](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnNcPaint`|[CMFCVisualManager:: OnNcPaint](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint) geçersiz kılar|
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|[CMFCVisualManagerWindows:: OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors) geçersiz kılar|
|`CMFCVisualManagerWindows7::SetResourceHandle`|Visual Manager 'ın özniteliklerini açıklayan kaynak tanıtıcısını ayarlar.|
|`CMFCVisualManagerWindows7::SetStyle`|GUI 'nin renk şemasını ayarlar `CMFCVisualManagerWindows7` .|

## <a name="remarks"></a>Açıklamalar

`CMFCVisualManagerWindows7`Varsayılan bir Windows 7 uygulamasını taklit etmek için uygulamanızın görünüşünü değiştirmek üzere sınıfını kullanın. Uygulamanız Windows 7 ' den önceki bir Windows sürümünde çalışıyorsa bu sınıf geçerli olmayabilir. Bu senaryoda, uygulama [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)'da tanımlanan varsayılan Visual Manager 'ı kullanır.

CMFCVisualManagerWindows7, hem [CMFCVisualManagerWindows sınıfından](../../mfc/reference/cmfcvisualmanagerwindows-class.md) hem de sınıfından birden çok yöntemi devralır `CMFCVisualManager` . Önceki bölümde listelenen yöntemler, sınıfının yeni bir yöntemleridir `CMFCVisualManagerWindows7` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

`CMFCVisualManagerWindows7`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxvisualmanagerwindows7. h

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="_dtorcmfcvisualmanagerwindows7"></a> CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7

Varsayılan yok edicisi.

```
virtual ~CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="cmfcvisualmanagerwindows7"></a> CMFCVisualManagerWindows7::CMFCVisualManagerWindows7

Varsayılan Oluşturucu.

```
CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7getribboneditbackgroundcolor"></a><a name="getribboneditbackgroundcolor"></a> CMFCVisualManagerWindows7:: GetRibbonEditBackgroundColor

Şerit düzenleme kutusunun arka plan rengini alır.

```
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,
    BOOL bIsHighlighted,
    BOOL bIsPaneHighlighted,
    BOOL bIsDisabled);
```

### <a name="parameters"></a>Parametreler

*pEdit*<br/>
'ndaki Düzenleme denetimine yönelik bir işaretçi. Bu değer NULL olamaz.

*Bisvurgulu*<br/>
dışı Şerit kutusunun vurgulanıp vurgulanmadığını döndürür.

*bIsPaneHighlighted*<br/>
dışı *PEdit* içeren şerit paneli VURGULANDıĞıNDA true döndürür.

*Bıdısabled*<br/>
dışı *PEdit* 'in devre dışı olup olmadığını döndürür.

### <a name="return-value"></a>Dönüş Değeri

Düzenleme kutusunun *pEdit*'in arka plan rengi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcvisualmanagerwindows7onfillmenuimagerect"></a><a name="onfillmenuimagerect"></a> CMFCVisualManagerWindows7:: OnFillMenuImageRect

Framework, bir menü öğesi görüntüsünün etrafındaki alanı doldururken bu yöntemi çağırır.

```
virtual void OnFillMenuImageRect(
    CDC* pDC,
    CMFCToolBarButton* pButton,
    CRect rectangle,
    CMFCVisualManager::AFX_BUTTON_STATE state);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Bir menü düğmesinin cihaz bağlamına yönelik bir işaretçi.

*pButton*<br/>
'ndaki Bir işaretçisi `CMFCToolBarButton` . Çerçeve bu düğme için arka planı doldurur.

*dikdörtgen*<br/>
'ndaki Menü düğmesi görüntü alanının sınırlarını belirten bir dikdörtgen.

*durumunda*<br/>
'ndaki Düğme durumu.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CMFCVisualManagerWindows sınıfı](../../mfc/reference/cmfcvisualmanagerwindows-class.md)
