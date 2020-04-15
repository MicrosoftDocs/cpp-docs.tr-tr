---
title: CMFCVisualManagerWindows7 Sınıfı
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
ms.openlocfilehash: 6686afecc2b8ef97ea24ef45ff5225433677a954
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319843"
---
# <a name="cmfcvisualmanagerwindows7-class"></a>CMFCVisualManagerWindows7 Sınıfı

Bir `CMFCVisualManagerWindows7` uygulamaya Windows 7 uygulaması görünümü verir.

## <a name="syntax"></a>Sözdizimi

```
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7)|Varsayılan oluşturucu.|
|[CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7](#_dtorcmfcvisualmanagerwindows7)|Varsayılan yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCVisualManagerWindows7::CleanStyle`|Geçerli görsel stili temizler ve varsayılan görsel stili sıfırlar.|
|`CMFCVisualManagerWindows7::CleanUp`|Kullanıcı arabirimindeki tüm nesneleri temizler ve menüleri sıfırlar.|
|`CMFCVisualManagerWindows7::DrawNcBtn`|Çerçevedeki istemci olmayan alanda bir düğme çizer. Çerçeve, pencere çerçevesinin sağ üst köşesindeki düğmeleri en aza indirmek, en üst düzeye çıkarmak, kapatmak ve geri yüklemek için bu yöntemi kullanır. Bu yöntem yalnızca program bir `Aero` tema kullandığında çağrılır.|
|`CMFCVisualManagerWindows7::DrawNcText`|Çerçeveüzerinde istemci olmayan alana metin çizer. Çerçeve, çerçeve penceresinin üst kısmındaki başlık çubuğundaki uygulama başlığını çizmek için bu yöntemi kullanır.|
|`CMFCVisualManagerWindows7::DrawSeparator`|[CMFCToolBar Sınıfı'na](../../mfc/reference/cmfctoolbar-class.md)bir ayırıcı çizer.|
|`CMFCVisualManagerWindows7::GetRibbonBar`|Kullanıcı arabirimiyle ilişkili [CMFCRibbonBar Sınıfını](../../mfc/reference/cmfcribbonbar-class.md) alır.|
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](#getribboneditbackgroundcolor)|Şerit li kutu arka plan rengini alır.|
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|[CMFCVisualManager geçersiz kılar::GetRibbonPopupBorderSize](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|[CMFCVisualManager geçersiz kılar::GetRibbonQuickAccessToolToolChevronOffset](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)|
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|[CMFCVisualManager geçersiz kılar::GetRibbonQuickAccessToolBarRightMargin](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)|
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|[CMFCVisualManagerWindows geçersiz kılar::IsHighlightWholeMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)|
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|[CMFCVisualManager geçersiz kılar::IsOwnerDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)|
|`CMFCVisualManagerWindows7::IsRibbonPresent`|A'nın `CMFCRibbonBar` var ve görünür olup olmadığını belirler.|
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|[CMFCVisualManagerWindows geçersiz kılar::OnDrawButtonBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|[CMFCVisualManagerWindows geçersiz kılar::OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)|
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|[CMFCVisualManagerWindows geçersiz kılar::OnDrawComboDropButton](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)|
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|[CMFCVisualManager geçersiz kılar::OnDrawDefaultRibbonImage](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)|
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|[CMFCVisualManagerWindows geçersiz kılar::OnDrawMenuBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)|
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|[CMFCVisualManager geçersiz kılar::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)|
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|[CMFCVisualManager geçersiz kılar::OnDrawMenuLabel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)|
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Geçersiz kılınır`CMFCVisualManager::OnDrawRadioButton`|
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonApplicationButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonCaptionButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonKategori](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)|
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)|
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonDefaultPaneButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonGalleryButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Geçersiz kılınır`CMFCVisualManager::OnDrawRibbonLaunchButton`|
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonMenuCheckFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonPanel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonPanelCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption)|
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonProgressBar](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar)|
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonRecentFilesFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonSliderChannel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonSliderThumb](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb)|
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonSliderZoomButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton)|
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonStatusBarPane](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane)|
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|[CMFCVisualManager geçersiz kılar::OnDrawRibbonTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe)|
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|[CMFCVisualManagerWindows geçersiz kılar::OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox)|
|`CMFCVisualManagerWindows7::OnFillBarBackground`|[CMFCVisualManagerWindows geçersiz kılar::OnFillBarBackground](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground)|
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|[CMFCVisualManagerWindows geçersiz kılar::OnFillButtonInterior](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior)|
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](#onfillmenuimagerect)|Çerçeve, menü öğesi görüntülerinin etrafındaki alanı doldururken bu yöntemi çağırır.|
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|[CMFCVisualManager geçersiz kılar::OnFillRibbonButton](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)|
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|[CMFCVisualManager geçersiz kılar::OnFillRibbonQuickAccessToolToolPopup](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)|
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|[CMFCVisualManagerWindows geçersiz kılar::OnHighlightMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)|
|`CMFCVisualManagerWindows7::OnNcActivate`|[CMFCVisualManager geçersiz kılar::OnNcActivate](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)|
|`CMFCVisualManagerWindows7::OnNcPaint`|[CMFCVisualManager geçersiz kılar::OnNcPaint](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)|
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|[CMFCVisualManagerWindows geçersiz kılar::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)|
|`CMFCVisualManagerWindows7::SetResourceHandle`|Görsel yöneticinin özniteliklerini açıklayan kaynak tutamacını ayarlar.|
|`CMFCVisualManagerWindows7::SetStyle`|GUI'nin renk `CMFCVisualManagerWindows7` düzenini ayarlar.|

## <a name="remarks"></a>Açıklamalar

Varsayılan `CMFCVisualManagerWindows7` bir Windows 7 uygulamasını taklit etmek için uygulamanızın görünümünü değiştirmek için sınıfı kullanın. Uygulamanız Windows 7'den önceki bir Windows sürümünde çalışıyorsa, bu sınıf geçerli olmayabilir. Bu senaryoda, uygulama [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)tanımlanan varsayılan görsel yöneticisi kullanır.

CMFCVisualManagerWindows7, hem [CMFCVisualManagerWindows Sınıfından](../../mfc/reference/cmfcvisualmanagerwindows-class.md) hem de `CMFCVisualManager` sınıftan birden çok yöntem devralır. Önceki bölümde listelenen yöntemler sınıfa `CMFCVisualManagerWindows7` yeni yöntemlerdir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

[CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)

[CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)

[CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)

`CMFCVisualManagerWindows7`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxvisualmanagerwindows7.h

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="_dtorcmfcvisualmanagerwindows7"></a>CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7

Varsayılan yıkıcı.

```
virtual ~CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7cmfcvisualmanagerwindows7"></a><a name="cmfcvisualmanagerwindows7"></a>CMFCVisualManagerWindows7::CMFCVisualManagerWindows7

Varsayılan oluşturucu.

```
CMFCVisualManagerWindows7();
```

## <a name="cmfcvisualmanagerwindows7getribboneditbackgroundcolor"></a><a name="getribboneditbackgroundcolor"></a>CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor

Şeritli bir edit kutusunun arka plan rengini alır.

```
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,
    BOOL bIsHighlighted,
    BOOL bIsPaneHighlighted,
    BOOL bIsDisabled);
```

### <a name="parameters"></a>Parametreler

*pEdit*<br/>
[içinde] Denetime işaretçi. Bu değer NULL olamaz.

*bIsVurgulu*<br/>
[çıkış] Şerit kutusunun vurgulanıp vurgulanmadığını verir.

*bIsPaneVurgulu*<br/>
[çıkış] *pEdit* içeren şerit paneli vurgulanırsa TRUE döndürür.

*bIsDisabled*<br/>
[çıkış] *PEdit* devre dışı olup olmadığını döndürür.

### <a name="return-value"></a>Dönüş Değeri

Edit kutusunun arka plan rengi *pEdit*.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcvisualmanagerwindows7onfillmenuimagerect"></a><a name="onfillmenuimagerect"></a>CMFCVisualManagerWindows7::OnFillMenuImageRect

Çerçeve, bir menü öğesi görüntüsünün etrafındaki alanı doldururken bu yöntemi çağırır.

```
virtual void OnFillMenuImageRect(
    CDC* pDC,
    CMFCToolBarButton* pButton,
    CRect rectangle,
    CMFCVisualManager::AFX_BUTTON_STATE state);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Menü düğmesinin aygıt bağlamına işaretçi.

*pDüğme*<br/>
[içinde] Bir işaretçi `CMFCToolBarButton`. Çerçeve bu düğmenin arka planını doldurur.

*Dikdörtgen*<br/>
[içinde] Menü düğmesi görüntü alanının sınırlarını belirten bir dikdörtgen.

*durum*<br/>
[içinde] Düğme durumu.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager Sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)<br/>
[CMFCVisualManagerWindows Sınıfı](../../mfc/reference/cmfcvisualmanagerwindows-class.md)
