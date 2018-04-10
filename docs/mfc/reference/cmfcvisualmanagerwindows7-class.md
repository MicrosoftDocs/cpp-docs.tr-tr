---
title: CMFCVisualManagerWindows7 sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor
- AFXVISUALMANAGERWINDOWS7/CMFCVisualManagerWindows7::OnFillMenuImageRect
dev_langs:
- C++
helpviewer_keywords:
- CMFCVisualManagerWindows7 Class [MFC]
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96168e569ff2207e43663f50989eb0686d3d52a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcvisualmanagerwindows7-class"></a>CMFCVisualManagerWindows7 sınıfı
`CMFCVisualManagerWindows7` Uygulamanın görünümünü sunan bir [!INCLUDE[win7](../../build/includes/win7_md.md)] uygulama.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7)|Varsayılan Oluşturucu.|  
|[CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7](#cmfcvisualmanagerwindows7__~cmfcvisualmanagerwindows7)|Varsayılan yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCVisualManagerWindows7::CleanStyle`|Geçerli görsel stil temizler ve varsayılan görsel stil sıfırlar.|  
|`CMFCVisualManagerWindows7::CleanUp`|Kullanıcı arabiriminde nesnelerin tümünü temizler ve menüleri sıfırlar.|  
|`CMFCVisualManagerWindows7::DrawNcBtn`|Bir düğme çerçevesi istemci olmayan alanında çizer. Framework kullandığı çizmek için bu yöntem simge durumuna küçült, en üst düzeye çıkarmak, kapatın ve pencere çerçevesi sağ üst köşesindeki düğmeleri geri yükleyin. Program Aero olmayan bir tema kullandığında bu yöntem çağrılmaz.|  
|`CMFCVisualManagerWindows7::DrawNcText`|Metin çerçevesi istemci olmayan alanında çizer. Çerçeve çerçeve pencerenin üstündeki başlık çubuğunda uygulama başlığı çizmek için bu yöntemi kullanır.|  
|`CMFCVisualManagerWindows7::DrawSeparator`|Ayırıcı çizer [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md).|  
|`CMFCVisualManagerWindows7::GetRibbonBar`|Alır [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md) kullanıcı arabirimiyle ilişkilendirilmiş.|  
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](#getribboneditbackgroundcolor)|Şerit düzenleme kutusuna arka plan rengi alır.|  
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|Geçersiz kılmaları [CMFCVisualManager::GetRibbonPopupBorderSize](../../mfc/reference/cmfcvisualmanager-class.md#getribbonpopupbordersize)|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|Geçersiz kılmaları [CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarchevronoffset)|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|Geçersiz kılmaları [CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin](../../mfc/reference/cmfcvisualmanager-class.md#getribbonquickaccesstoolbarrightmargin)|  
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|Geçersiz kılmaları [CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ishighlightwholemenuitem)|  
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|Geçersiz kılmaları [CMFCVisualManager::IsOwnerDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#isownerdrawmenucheck)|  
|`CMFCVisualManagerWindows7::IsRibbonPresent`|Belirler olup bir `CMFCRibbonBar` mevcut ve görünür durumda.|  
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnDrawButtonBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawbuttonborder)|  
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnDrawCheckBoxEx](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcheckboxex)|  
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnDrawComboDropButton](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawcombodropbutton)|  
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|Geçersiz kılmaları [CMFCVisualManager::OnDrawDefaultRibbonImage](../../mfc/reference/cmfcvisualmanager-class.md#ondrawdefaultribbonimage)|  
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnDrawMenuBorder](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawmenuborder)|  
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|Geçersiz kılmaları [CMFCVisualManager::OnDrawMenuCheck](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenucheck)|  
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|Geçersiz kılmaları [CMFCVisualManager::OnDrawMenuLabel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawmenulabel)|  
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|Geçersiz kılmaları`CMFCVisualManager::OnDrawRadioButton`|  
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonApplicationButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonapplicationbutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonButtonBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonbuttonborder)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaption)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonCaptionButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncaptionbutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonCategory](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategory)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonCategoryTab](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribboncategorytab)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbondefaultpanebutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonGalleryButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbongallerybutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|Geçersiz kılmaları`CMFCVisualManager::OnDrawRibbonLaunchButton`|  
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonmenucheckframe)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonPanel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanel)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonPanelCaption](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonpanelcaption)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonProgressBar](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonprogressbar)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonrecentfilesframe)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonSliderChannel](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderchannel)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonSliderThumb](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderthumb)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonsliderzoombutton)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonStatusBarPane](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbonstatusbarpane)|  
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|Geçersiz kılmaları [CMFCVisualManager::OnDrawRibbonTabsFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawribbontabsframe)|  
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../../mfc/reference/cmfcvisualmanagerwindows-class.md#ondrawstatusbarsizebox)|  
|`CMFCVisualManagerWindows7::OnFillBarBackground`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnFillBarBackground](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbarbackground)|  
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnFillButtonInterior](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onfillbuttoninterior)|  
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](#onfillmenuimagerect)|Menü öğesi görüntüleri etrafına doldurduğunda framework bu yöntemi çağırır.|  
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|Geçersiz kılmaları [CMFCVisualManager::OnFillRibbonButton](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonbutton)|  
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|Geçersiz kılmaları [CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../../mfc/reference/cmfcvisualmanager-class.md#onfillribbonquickaccesstoolbarpopup)|  
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnHighlightMenuItem](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onhighlightmenuitem)|  
|`CMFCVisualManagerWindows7::OnNcActivate`|Geçersiz kılmaları [CMFCVisualManager::OnNcActivate](../../mfc/reference/cmfcvisualmanager-class.md#onncactivate)|  
|`CMFCVisualManagerWindows7::OnNcPaint`|Geçersiz kılmaları [CMFCVisualManager::OnNcPaint](../../mfc/reference/cmfcvisualmanager-class.md#onncpaint)|  
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|Geçersiz kılmaları [CMFCVisualManagerWindows::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanagerwindows-class.md#onupdatesystemcolors)|  
|`CMFCVisualManagerWindows7::SetResourceHandle`|Görsel Yöneticisi özniteliklerini açıklayan kaynağı tanıtıcısı ayarlar.|  
|`CMFCVisualManagerWindows7::SetStyle`|Renk düzenini ayarlar `CMFCVisualManagerWindows7` GUI.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CMFCVisualManagerWindows7` varsayılan taklit etmek için uygulamanızın görünümünü değiştirmek için sınıf [!INCLUDE[win7](../../build/includes/win7_md.md)] uygulama. Bu sınıf, uygulamanızın bir Windows sürümünde çalışıyorsa, geçerli olmayabilir öncesi [!INCLUDE[win7](../../build/includes/win7_md.md)]. Bu senaryoda, uygulama içinde tanımlanan varsayılan visual Yöneticisi kullanır [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).  
  
 Birden çok yöntem hem de CMFCVisualManagerWindows7 devralır [CMFCVisualManagerWindows sınıfı](../../mfc/reference/cmfcvisualmanagerwindows-class.md) ve `CMFCVisualManager` sınıfı. Önceki bölümde listelenen yöntemleri için yeni yöntemler şunlardır `CMFCVisualManagerWindows7` sınıfı.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
 `CMFCVisualManagerWindows7`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxvisualmanagerwindows7.h  
  
##  <a name="_dtorcmfcvisualmanagerwindows7"></a>CMFCVisualManagerWindows7:: ~ CMFCVisualManagerWindows7  
 Varsayılan yıkıcı.  
  
```  
virtual ~CMFCVisualManagerWindows7();
```  
  
##  <a name="cmfcvisualmanagerwindows7"></a>CMFCVisualManagerWindows7::CMFCVisualManagerWindows7  
 Varsayılan Oluşturucu.  
  
```  
CMFCVisualManagerWindows7();
```  
  
##  <a name="getribboneditbackgroundcolor"></a>CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor  
 Şerit düzenleme kutusu arka plan rengini alır.  
  
```  
virtual COLORREF GetRibbonEditBackgroundColor (
    CMFCRibbonRichEditCtrl* pEdit,  
    BOOL bIsHighlighted,  
    BOOL bIsPaneHighlighted,  
    BOOL bIsDisabled);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pEdit`  
 Düzenleme denetimine işaretçi. Bu değer olamaz `NULL`.  
  
 [out]`bIsHighlighted`  
 Şerit kutusunu vurgulanmış olup olmadığını döndürür.  
  
 [out]`bIsPaneHighlighted`  
 Döndürür `TRUE` Şerit panel varsa `pEdit` vurgulanır.  
  
 [out]`bIsDisabled`  
 Döndürür olup olmadığını `pEdit` devre dışı bırakılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenleme kutusuna arka plan rengini `pEdit`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onfillmenuimagerect"></a>CMFCVisualManagerWindows7::OnFillMenuImageRect  
 Menü öğesi görüntüsü etrafına doldurduğunda framework bu yöntemi çağırır.  
  
```  
virtual void OnFillMenuImageRect(
    CDC* pDC,  
    CMFCToolBarButton* pButton,  
    CRect rect,  
    CMFCVisualManager::AFX_BUTTON_STATE state);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Menü düğmesinin cihaz bağlamı için bir işaretçi.  
  
 [in]`pButton`  
 Bir işaretçi bir `CMFCToolBarButton`. Bu düğme için arka plan framework doldurur.  
  
 [in]`rect`  
 Menü düğmesine görüntü alanını sınırlarının belirtir dikdörtgen.  
  
 [in]`state`  
 Düğme durumu.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerWindows Sınıfı](../../mfc/reference/cmfcvisualmanagerwindows-class.md)
