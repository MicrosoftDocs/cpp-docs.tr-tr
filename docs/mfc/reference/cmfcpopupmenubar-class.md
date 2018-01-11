---
title: "CMFCPopupMenuBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
dev_langs: C++
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 002e059fd905930409cb5f2745628f8ac1dea103
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar sınıfı
Menü çubuğu açılır menü katıştırılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCPopupMenuBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Hemen bir bölme düzenini yeniden hesaplar. (Geçersiz kılmaları [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|  
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Açılan menü öğelerini belirtilen menü kaynaktan yükler.|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Gecikmeli açılan menü düğmesi kapatır.|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Açılan menü düğmelerini menüsünden oluşturur.|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Araç, burada belirtilen bir nokta arasındadır bulur.|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Menü düğmesine görüntülerinin boyutunu belirtir.|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Varsayılan menü öğesi tanımlayıcısını döndürür.|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|En son çağırılan menü komutu dizinini alır.|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Açılan menü çubuğu satır uzaklığını alır.|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Açılan menü düğmesi belirtilen menüden alır.|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Açılan menü çubuğundaki açılan aşağı liste modunda olup olmadığını gösterir.|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Açılan menü çubuğu palet modunda olup olmadığını gösterir.|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Bu bir Şerit panel olup olmadığını gösterir ( `FALSE` varsayılan olarak).|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Bu normal modda bir Şerit panel olup olmadığını gösterir ( `FALSE` varsayılan olarak).|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Arşivlenen menü yükler.|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Açılan menü çubuğu kapatma Gecikmeli menü düğmesi geri yükler.|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Verilen dizinde araç çubuğu düğmesi stilini ayarlar. (Geçersiz kılmaları [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Açılan menü çubuğu satır uzaklığı ayarlar.|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Belirtilen Gecikmeli açılan menü düğmesi süreölçer başlatır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Uygulama bir Windows XP görünümü olduğunda gri kenar görüntülenip görüntülenmeyeceğini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCPopupMenuBar` Aynı zamanda oluşturulan bir [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) ve onun içindeki katıştırılmış. `CMFCPopupMenuBar` Tüm istemci alanını kapsayan `CMFCPopupMenu` nesnesi. Klavye ve fare girişi destekler. Bu ayrıca, giriş iletişim kurar `CMFCPopupMenu` ve en üst düzey çerçeve penceresi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl başlatılacağını gösteren bir `CMFCPopupMenuBar` nesnesinin bir `CMFCPopupMenu` nesnesi. Bu kod parçacığını parçası olan [çizin istemci örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxpopupmenubar.h  
  
##  <a name="adjustsizeimmediate"></a>CMFCPopupMenuBar::AdjustSizeImmediate  
 Hemen açılan menü çubuğu bölmesinin düzenini yeniden hesaplar. (Geçersiz kılmaları [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bRecalcLayout`  
 `TRUE`otomatik olarak açılan menü çubuğu bölmesinin düzenini yeniden hesapla için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="buildorigitems"></a>CMFCPopupMenuBar::BuildOrigItems  
 Açılan menü öğelerini belirtilen menü kaynaktan yükler.  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiMenuResID`  
 Yüklemek için menü kaynağı menü Kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` başarılı olursa ya da `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="closedelayedsubmenu"></a>CMFCPopupMenuBar::CloseDelayedSubMenu  
 Ertelendi bir açılır menü düğmesi kapatır.  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="exporttomenu"></a>CMFCPopupMenuBar::ExportToMenu  
 Açılan menü düğmelerini menüsünden oluşturur.  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni menüsüne bir işleyici döner.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="finddestintationtoolbar"></a>CMFCPopupMenuBar::FindDestintationToolBar  
 Araç, burada belirtilen bir nokta arasındadır bulur.  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 Ekran noktasında.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Therei, ise bir tanıtıcı araç çubuğuna burada noktası arasındadır, döndürür veya `NULL` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcurrentmenuimagesize"></a>CMFCPopupMenuBar::GetCurrentMenuImageSize  
 Menü düğmesine görüntülerinin boyutunu belirtir.  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü düğmesine görüntülerinin boyutunu araç çubuğunda döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdefaultmenuid"></a>CMFCPopupMenuBar::GetDefaultMenuId  
 Varsayılan menü öğesi tanımlayıcısını döndürür.  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılan menü çubuğunda varsayılan menü öğesi tanımlayıcısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getlastcommandindex"></a>CMFCPopupMenuBar::GetLastCommandIndex  
 En son çağırılan menü komutu dizinini alır.  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çağrılmış son menü komutu dizinini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getoffset"></a>CMFCPopupMenuBar::GetOffset  
 Açılan menü çubuğu satır uzaklığını alır.  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılan menü çubuğu satır uzaklığını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer kullanılarak ayarlanan [CMFCPopupMenuBar::SetOffset](#setoffset).  
  
##  <a name="importfrommenu"></a>CMFCPopupMenuBar::ImportFromMenu  
 Açılan menü düğmesi belirtilen menüden alır.  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hMenu`  
 Menü açılan menü düğmelerini içeri aktarılacak.  
  
 [in]`bShowAllCommands`  
 `TRUE`İçeri aktarılacak menüsünde tüm komutları olup olmadığını veya `FALSE` ender kullanılan olanları gizli.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` menü düğmelerini menüsünden başarıyla içeri aktarıldı olsaydı veya `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isdropdownlistmode"></a>CMFCPopupMenuBar::IsDropDownListMode  
 Açılan menü çubuğundaki açılan aşağı liste modunda olup olmadığını gösterir.  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` açılır menü çubuğu açılan aşağı liste modunda değilse veya `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ispalettemode"></a>CMFCPopupMenuBar::IsPaletteMode  
 Açılan menü çubuğu palet modunda olup olmadığını gösterir.  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` palet modu etkinleştirildiğinde veya `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü çubuğu palet moda ayarlandığında, menü öğeleri birden çok sütun ve satırlar, sınırlı sayıda görünür.  
  
##  <a name="isribbonpanel"></a>CMFCPopupMenuBar::IsRibbonPanel  
 Bu bir Şerit panel olup olmadığını gösterir ( `FALSE` varsayılan olarak).  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `FALSE` bunun bir Şerit panel olmadığını belirten varsayılan.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isribbonpanelinregularmode"></a>CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 Bu normal modda bir Şerit panel olup olmadığını gösterir ( `FALSE` varsayılan olarak).  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `FALSE` varsayılan olarak bu bir Şerit panel normal modda olduğunu gösteren.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="loadfromhash"></a>CMFCPopupMenuBar::LoadFromHash  
 Arşivlenen menü yükler.  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hMenu`  
 Yükleme için arşivlenmiş menüsüne işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` menü başarıyla yüklüyse veya `FALSE` değilse.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_bdisablesidebarinxpmode"></a>CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Bir Windows XP görünümü sahip olduğunda, uygulamanızın gri kenar olup olmadığını belirten bir Boole parametresi.  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye değişkeni ayarlanmışsa `FALSE` ve uygulamanızı bir Windows XP görünümü sahipse, uygulamanızda gri kenar framework çizer.  
  
 Varsayılan değer `FALSE` şeklindedir.  
  
##  <a name="restoredelayedsubmenu"></a>CMFCPopupMenuBar::RestoreDelayedSubMenu  
 Açılan menü çubuğu kapatma Gecikmeli menü düğmesi geri yükler.  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setbuttonstyle"></a>CMFCPopupMenuBar::SetButtonStyle  
 Verilen dizinde araç çubuğu düğmesi stilini ayarlar. (Geçersiz kılmaları [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nIndex`  
 Ayarlanacak stilini iş araç çubuğu düğmesi sıfır tabanlı dizini.  
  
 [in]`nStyle`  
 Düğmesinin stili. Bkz: [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md) kullanılabilir araç çubuğu düğmesi stilleri listesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setoffset"></a>CMFCPopupMenuBar::SetOffset  
 Açılan menü çubuğu satır uzaklığı ayarlar.  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`iOffset`  
 Açılan menü çubuğu uzaklığı, satır sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="startpopupmenutimer"></a>CMFCPopupMenuBar::StartPopupMenuTimer  
 Belirtilen Gecikmeli açılan menü düğmesi süreölçer başlatır.  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pMenuButton`  
 Gecikme Zamanlayıcı ayarlanacak menü düğmesi işaretçi.  
  
 [in]`nDelayFactor`  
 Bir gecikme faktörü, en az biri, standart menü gecikme süresini (genellikle bir yarım saniye arasında beş saniye) tarafından çarpılacağı eşittir.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)
