---
title: CMFCMenuBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuBar [MFC], AdjustLocations
- CMFCMenuBar [MFC], AllowChangeTextLabels
- CMFCMenuBar [MFC], AllowShowOnPaneMenu
- CMFCMenuBar [MFC], CalcFixedLayout
- CMFCMenuBar [MFC], CalcLayout
- CMFCMenuBar [MFC], CalcMaxButtonHeight
- CMFCMenuBar [MFC], CanBeClosed
- CMFCMenuBar [MFC], CanBeRestored
- CMFCMenuBar [MFC], Create
- CMFCMenuBar [MFC], CreateEx
- CMFCMenuBar [MFC], CreateFromMenu
- CMFCMenuBar [MFC], EnableHelpCombobox
- CMFCMenuBar [MFC], EnableMenuShadows
- CMFCMenuBar [MFC], GetAvailableExpandSize
- CMFCMenuBar [MFC], GetColumnWidth
- CMFCMenuBar [MFC], GetDefaultMenu
- CMFCMenuBar [MFC], GetDefaultMenuResId
- CMFCMenuBar [MFC], GetFloatPopupDirection
- CMFCMenuBar [MFC], GetForceDownArrows
- CMFCMenuBar [MFC], GetHelpCombobox
- CMFCMenuBar [MFC], GetHMenu
- CMFCMenuBar [MFC], GetMenuFont
- CMFCMenuBar [MFC], GetMenuItem
- CMFCMenuBar [MFC], GetRowHeight
- CMFCMenuBar [MFC], GetSystemButton
- CMFCMenuBar [MFC], GetSystemButtonsCount
- CMFCMenuBar [MFC], GetSystemMenu
- CMFCMenuBar [MFC], HighlightDisabledItems
- CMFCMenuBar [MFC], IsButtonExtraSizeAvailable
- CMFCMenuBar [MFC], IsHighlightDisabledItems
- CMFCMenuBar [MFC], IsMenuShadows
- CMFCMenuBar [MFC], IsRecentlyUsedMenus
- CMFCMenuBar [MFC], IsShowAllCommands
- CMFCMenuBar [MFC], IsShowAllCommandsDelay
- CMFCMenuBar [MFC], LoadState
- CMFCMenuBar [MFC], OnChangeHot
- CMFCMenuBar [MFC], OnDefaultMenuLoaded
- CMFCMenuBar [MFC], OnSendCommand
- CMFCMenuBar [MFC], OnSetDefaultButtonText
- CMFCMenuBar [MFC], OnToolHitTest
- CMFCMenuBar [MFC], PreTranslateMessage
- CMFCMenuBar [MFC], RestoreOriginalstate
- CMFCMenuBar [MFC], SaveState
- CMFCMenuBar [MFC], SetDefaultMenuResId
- CMFCMenuBar [MFC], SetForceDownArrows
- CMFCMenuBar [MFC], SetMaximizeMode
- CMFCMenuBar [MFC], SetMenuButtonRTC
- CMFCMenuBar [MFC], SetMenuFont
- CMFCMenuBar [MFC], SetRecentlyUsedMenus
- CMFCMenuBar [MFC], SetShowAllCommands
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63e7fd651cf8a5524f3dc6c521de742ced7741ac
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039277"
---
# <a name="cmfcmenubar-class"></a>CMFCMenuBar sınıfı
Menü çubuğu yerleştirme uygular.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(Geçersiz kılmaları `CMFCToolBar::AdjustLocations`.)|  
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|Metin etiketleri araç çubuğu düğmelerini görüntülerinde altında gösterilen olup olmadığını belirtir. (Geçersiz kılmaları [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Geçersiz kılmaları `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Araç çubuğunun yatay boyutunu hesaplar. (Geçersiz kılmaları [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|  
|[CMFCMenuBar::CalcLayout](#calclayout)|(Geçersiz kılmaları `CMFCToolBar::CalcLayout`.)|  
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Araç çubuğu düğmeleri en fazla yüksekliği hesaplar. (Geçersiz kılmaları [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|  
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|Bir kullanıcı araç kapatabilirsiniz olup olmadığını belirtir. (Geçersiz kılmaları [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|  
|[CMFCMenuBar::CanBeRestored](#canberestored)|Sistemi bir araç çubuğu özgün durumuna geri özelleştirme sonrasında geri yükleyebilirsiniz olup olmadığını belirler. (Geçersiz kılmaları [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCMenuBar::Create](#create)|Menü denetimi oluşturur ve ona ekler bir `CMFCMenuBar` nesnesi.|  
|[CMFCMenuBar::CreateEx](#createex)|Oluşturur bir `CMFCMenuBar` ek stil seçeneklerini nesnesiyle.|  
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|Başlatır bir `CMFCMenuBar` nesnesi. Kabul eden bir `HMENU` doldurulan bir için bir şablon olarak davranan parametresi `CMFCMenuBar`.|  
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Sağlayan bir **yardımcı** menü çubuğu sağ tarafta bulunan açılan kutusu.|  
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|Açılır menüler gölgesi görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(Geçersiz kılmaları [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|  
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|Araç çubuğu düğmelerini genişliğini döndürür. (Geçersiz kılmaları [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|  
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Kaynak dosyasında özgün menüsüne bir işleyici döner.|  
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Kaynak dosyasında özgün menüsü kaynak tanımlayıcısını döndürür.|  
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||  
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||  
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Bir işaretçi döndürür **yardımcı** birleşik giriş kutusu.|  
|[CMFCMenuBar::GetHMenu](#gethmenu)|Bağlı menüsüne işleyicisini döndürür `CMFCMenuBar` nesnesi.|  
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Menü nesneler için geçerli genel yazı tipi döndürür.|  
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Sağlanan öğe dizini ile ilişkili araç çubuğu düğmesi döndürür.|  
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Araç çubuğu düğmeleri yüksekliğini döndürür. (Geçersiz kılmaları [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||  
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||  
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||  
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Devre dışı bırakılmış menü öğeleri vurgulanmıştır olup olmadığını gösterir.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Araç çubuğu kenarlık genişletilmiş düğmeleri görüntülemek olup olmadığını belirler. (Geçersiz kılmaları [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|Devre dışı öğeler vurgulanır olup olmadığını gösterir.|  
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Açılır menüler için gölge çizilmiş olup olmadığını gösterir.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|Son kullanılan menü komutlarını menü çubuğunda görüntülenip görüntülenmeyeceğini gösterir.|  
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|Açılır menüler tüm komutları görüntülemek olup olmadığını gösterir.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Tüm komutları kısa bir gecikmeyle menülerini olup olmadığını gösterir.|  
|[CMFCMenuBar::LoadState](#loadstate)|Durumu yükler `CMFCMenuBar` kayıt defterinden nesnesi.|  
|[CMFCMenuBar::OnChangeHot](#onchangehot)|Bir kullanıcı bir araç çubuğu düğmesini seçtiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Çerçeve penceresi kaynak dosyasından varsayılan menüsünü yüklediğinde çerçevesi tarafından çağrılır.|  
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(Geçersiz kılmaları `CMFCToolBar::OnSendCommand`.)|  
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|Menü özelleştirme modundayken ve menü öğesinin metin kullanıcı değişiklikleri çerçevesi tarafından çağrılır.|  
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(Geçersiz kılmaları `CMFCToolBar::OnToolHitTest`.)|  
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Geçersiz kılmaları `CMFCToolBar::PreTranslateMessage`.)|  
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|Bir menüyü özelleştirme modunda olduğunda ve kullanıcının seçtiği çerçevesi tarafından çağrılır **sıfırlama** menü çubuğu için.|  
|[CMFCMenuBar::SaveState](#savestate)|Durumunu kaydeder `CMFCMenuBar` kayıt defterine nesnesi.|  
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Özgün menüsü kaynak dosyasında ayarlar.|  
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||  
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|MDI alt pencere görüntü modu değiştiğinde çerçevesi tarafından çağrılır. MDI alt pencere yeni ekranı ya da artık ekranı, bu yöntem menü çubuğu güncelleştirir.|  
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Kullanıcı Dinamik menü düğmelerini oluşturduğunda oluşturan çalışma zamanı sınıf bilgileri ayarlar.|  
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Tüm menü yazı tipini uygulamada ayarlar.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|Menü çubuğu son kullanılan menü komutlarını görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|Menü çubuğu tüm komutları gösterip göstermediğini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCMenuBar` Takma işlevselliğini hayata geçiren bir menü çubuğu bir sınıftır. Bu bir araç benzer ancak onu kapatılamaz - her zaman görüntülenir.  
  
 `CMFCMenuBar` Son kullanılan menü öğesi nesnelerini görüntüleme seçeneğini destekler. Bu seçenek etkinleştirilirse, `CMFCMenuBar` ilk görüntülemek yalnızca bir alt kullanılabilir komutlar kümesini görüntüler. Bundan sonra son kullanılan komutlar özgün komutları alt kümesi ile birlikte görüntülenir. Ayrıca, kullanıcının her zaman kullanılabilir tüm komutları görüntülemek için menüsünde genişletebilirsiniz. Bu nedenle, her kullanılabilir komut sürekli görüntülemek veya yalnızca, son seçilmişse görüntülemek için yapılandırılır.  
  
 Kullanılacak bir `CMFCMenuBar` nesne, ana pencereyi çerçeve nesne ekleme. İşleme sırasında `WM_CREATE` iletisi, çağrı `CMFCMenuBar::Create` veya `CMFCMenuBar::CreateEx`. İşlev oluşturduğunuz bağımsız olarak kullanmak, ana çerçeve penceresi için bir işaretçi geçirin. Çağırarak yerleştirme etkinleştirmek [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Bu menü çağırarak yerleştirme [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCMenuBar` sınıfı. Örnek, bölmesinin stilini ayarlama, Özelleştir düğmesini etkinleştirin, Yardım kutusunu etkinleştirin, açılır menüler gölgesi etkinleştirmek ve menü çubuğu güncelleştirme gösterilmektedir. Bu kod parçacığını parçası olan [IE gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 `CMFCMenuBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmenubar.h  
  
##  <a name="adjustlocations"></a>  CMFCMenuBar::AdjustLocations  
 Menü öğeleri menü çubuğunda konumlarını ayarlar.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="allowchangetextlabels"></a>  CMFCMenuBar::AllowChangeTextLabels  
 Metin etiketleri resimleri menü çubuğunda altında izin verilip verilmediğini belirler.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` kullanıcı metin etiketleri görüntüleri altında göstermeyi seçerseniz.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="allowshowonpanemenu"></a>  CMFCMenuBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcfixedlayout"></a>  CMFCMenuBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bStretch*  
 [in] *bHorz*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calclayout"></a>  CMFCMenuBar::CalcLayout  

  
```  
virtual CSize CalcLayout(
    DWORD dwMode,  
    int nLength = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwMode*  
 [in] *nLength*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcmaxbuttonheight"></a>  CMFCMenuBar::CalcMaxButtonHeight  

  
```  
virtual int CalcMaxButtonHeight();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="canbeclosed"></a>  CMFCMenuBar::CanBeClosed  

  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="canberestored"></a>  CMFCMenuBar::CanBeRestored  

  
```  
virtual BOOL CanBeRestored() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>  CMFCMenuBar::Create  
 Menü denetimi oluşturur ve ona ekler bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesi.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT nID = AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pParentWnd*  
 Yeni üst penceresine işaretçi `CMFCMenuBar` nesnesi.  
  
 [in] *dwStyle*  
 Yeni menü çubuğu stili.  
  
 [in] *nID*  
 Alt pencere menü çubuğunun kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturduktan sonra bir `CMFCMenuBar` nesne çağırmanız gerekir `Create`. Bu yöntem oluşturur `CMFCMenuBar` denetlemek ve ekleninceye `CMFCMenuBar` nesnesi.  
  
 Araç çubuğu stilleri hakkında daha fazla bilgi için bkz: [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).  
  
##  <a name="createex"></a>  CMFCMenuBar::CreateEx  
 Oluşturur bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesi ile belirtilen Genişletilmiş stili.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = TBSTYLE_FLAT,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    CRect rcBorders = CRect(1,
    1,
    1,
    1),  
    UINT nID =AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pParentWnd*  
 Yeni üst pencere işaretçi `CMFCMenuBar` nesnesi.  
  
 [in] *dwCtrlStyle*  
 Yeni menü çubuğu için ek stiller.  
  
 [in] *dwStyle*  
 Yeni menü çubuğu ana stili.  
  
 [in] *rcBorders*  
 A `CRect` kenarlıklarını boyutları belirten parametre `CMFCMenuBar` nesnesi.  
  
 [in] *nID*  
 Alt pencere menü çubuğunun kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yerine kullanmalısınız [CMFCMenuBar::Create](#create) stilleri araç çubuğu stili yanı sıra belirtmek istediğinizde. Sık kullanılan bazı ek stillerdir `TBSTYLE_TRANSPARENT` ve `CBRS_TOP`.  
  
 Ek stilleri bir listesi için bkz: [araç çubuğu denetimi ve düğme stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760439), [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498), ve [ortak pencere stilleri](http://msdn.microsoft.com/library/windows/desktop/ms632600).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `CreateEx` yöntemi `CMFCMenuBar` sınıfı. Bu kod parçacığını parçası olan [IE gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]  
  
##  <a name="createfrommenu"></a>  CMFCMenuBar::CreateFromMenu  
 Başlatır bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesi. Bu yöntem modelleri `CMFCMenuBar` sonra nesnesi bir `HMENU` parametresi.  
  
```  
virtual void CreateFromMenu(
    HMENU hMenu,  
    BOOL bDefaultMenu = FALSE,  
    BOOL bForceUpdate = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hMenu*  
 Menü kaynağı için tanıtıcı. `CreateFromMenu` Bu kaynak için bir şablon olarak kullanan `CMFCMenuBar`.  
  
 [in] *bDefaultMenu*  
 Yeni menü varsayılan menüsünü olup olmadığını belirten bir Boole değeri.  
  
 [in] *bForceUpdate*  
 Bu yöntem menü güncelleştirme zorlar olup olmadığını belirten bir Boole değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü kaynak olarak aynı menü öğeleri için bir menü denetimi istiyorsanız bu yöntemi kullanın. Ya da çağırdıktan sonra bu yöntemi çağırabilmeniz [CMFCMenuBar::Create](#create) veya [CMFCMenuBar::CreateEx](#createex).  
  
##  <a name="enablehelpcombobox"></a>  CMFCMenuBar::EnableHelpCombobox  
 Sağlayan bir **yardımcı** menü çubuğu sağ tarafta bulunan açılan kutusu.  
  
```  
void EnableHelpCombobox(
    UINT uiID,  
    LPCTSTR lpszPrompt = NULL,  
    int nComboBoxWidth = 150);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiID*  
 Düğmesine komut kimliği **yardımcı** birleşik giriş kutusu.  
  
 [in] *lpszPrompt*  
 Boş ve etkin değil ise, açılan kutuda framework görüntüleyen metni içeren bir dize. Örneğin, "metin girin burada".  
  
 [in] *nComboBoxWidth*  
 Birleşik giriş kutusu piksel cinsinden düğmenin genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 **Yardımcı** birleşik giriş kutusu benzer **yardımcı** menü çubuğunda birleşik giriş kutusu [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)].  
  
 Bu yöntemle çağırdığınızda *uiID* 0 olarak ayarlanırsa, bu yöntem birleşik giriş kutusu gizler. Aksi takdirde, bu yöntem birleşik giriş kutusu menü çubuğu sağ tarafta otomatik olarak görüntüler. Bu yöntemini çağırdıktan sonra arama [CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) eklenen bir işaretçi almak için [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesnesi.  
  
##  <a name="enablemenushadows"></a>  CMFCMenuBar::EnableMenuShadows  
 Açılır menüler gölgesi sağlar.  
  
```  
static void EnableMenuShadows(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Gölgeleri açılır menüler için etkin olup olmadığını gösteren bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından kullanılan algoritmasını karmaşıktır ve yavaş sistemlerde, uygulamanızın performansını düşürebilir.  
  
##  <a name="getavailableexpandsize"></a>  CMFCMenuBar::GetAvailableExpandSize  

  
```  
virtual int GetAvailableExpandSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcolumnwidth"></a>  CMFCMenuBar::GetColumnWidth  

  
```  
virtual int GetColumnWidth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdefaultmenu"></a>  CMFCMenuBar::GetDefaultMenu  
 Özgün menü işleyici alır. Framework özgün menüsü kaynak dosyadan yükler.  
  
```  
HMENU GetDefaultMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü kaynağı için tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı bir menü özelleştirir, özgün menü için bir tanıtıcı almak için bu yöntemi kullanabilirsiniz.  
  
##  <a name="getdefaultmenuresid"></a>  CMFCMenuBar::GetDefaultMenuResId  
 Varsayılan menüsünü kaynak tanımlayıcısını alır.  
  
```  
UINT GetDefaultMenuResId() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü kaynak tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçevesi için varsayılan menü yükler `CMFCMenuBar` kaynak dosyasından nesnesi.  
  
##  <a name="getfloatpopupdirection"></a>  CMFCMenuBar::GetFloatPopupDirection  

  
```  
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getforcedownarrows"></a>  CMFCMenuBar::GetForceDownArrows  

  
```  
BOOL GetForceDownArrows();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethelpcombobox"></a>  CMFCMenuBar::GetHelpCombobox  
 Bir işaretçi döndürür **yardımcı** birleşik giriş kutusu.  
  
```  
CMFCToolBarComboBoxButton* GetHelpCombobox();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi **yardımcı** birleşik giriş kutusu. `NULL` varsa **yardımcı** birleşik giriş kutusu gizli ya da etkinleştirilmemiş.  
  
### <a name="remarks"></a>Açıklamalar  
 **Yardımcı** birleşik giriş kutusu menü çubuğu sağ tarafta bulunur. Yöntemi çağırma [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) bu birleşik giriş kutusu etkinleştirmek için.  
  
##  <a name="gethmenu"></a>  CMFCMenuBar::GetHMenu  
 Bağlı menü tanıtıcısını alır [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesi.  
  
```  
HMENU GetHMenu() const;  
```  
  
##  <a name="getmenufont"></a>  CMFCMenuBar::GetMenuFont  
 Geçerli yazı tipi menüsü alır.  
  
```  
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bHorz*  
 Yatay veya dikey yazı tipi döndürülmeyeceğini belirten Boolean bir parametre. `TRUE` Yatay yazı tipini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CFont](../../mfc/reference/cfont-class.md) geçerli menü çubuğu yazı tipini içeren parametre.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen yazı tipi, uygulama için genel bir parametredir. İki genel yazı tipleri tüm korunur `CMFCMenuBar` nesneleri. Bu ayrı yazı tipleri yatay ve dikey menü çubukları için kullanılır.  
  
##  <a name="getmenuitem"></a>  CMFCMenuBar::GetMenuItem  
 Alır bir [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) menü çubuğundaki nesne tabanlı öğesi dizini.  
  
```  
CMFCToolBarButton* GetMenuItem(int iItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iItem*  
 Döndürülecek menü öğesi dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CMFCToolBarButton` tarafından belirtilen dizin eşleşen nesne *iItem*. `NULL` dizin geçersiz durumunda.  
  
##  <a name="getrowheight"></a>  CMFCMenuBar::GetRowHeight  

  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getsystembutton"></a>  CMFCMenuBar::GetSystemButton  

  
```  
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,  
    BOOL bByCommand = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiBtn*  
 [in] *bByCommand*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getsystembuttonscount"></a>  CMFCMenuBar::GetSystemButtonsCount  

  
```  
int GetSystemButtonsCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getsystemmenu"></a>  CMFCMenuBar::GetSystemMenu  

  
```  
CMFCToolBarSystemMenuButton* GetSystemMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="highlightdisableditems"></a>  CMFCMenuBar::HighlightDisabledItems  
 Framework devre dışı bırakılmış menü öğelerini vurgular olup olmadığını denetler.  
  
```  
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bHighlight*  
 Framework kullanılamaz menü öğelerini vurgular olup olmadığını gösteren bir Boolean parametresiyle.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı fare işaretçisini üzerlerine getirdiğinde varsayılan olarak, framework kullanılamaz menü öğelerini vurgulayın değil.  
  
##  <a name="isbuttonextrasizeavailable"></a>  CMFCMenuBar::IsButtonExtraSizeAvailable  

  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ishighlightdisableditems"></a>  CMFCMenuBar::IsHighlightDisabledItems  
 Framework kullanılamaz menü öğelerini vurgular olup olmadığını gösterir.  
  
```  
static BOOL IsHighlightDisabledItems();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` kullanılamayan menü öğeleri vurgulanır; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı fare işaretçisini üzerlerine getirdiğinde varsayılan olarak, framework kullanılamaz menü öğelerini vurgulayın değil. Kullanım [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) bu özelliği etkinleştirmek için yöntemi.  
  
##  <a name="ismenushadows"></a>  CMFCMenuBar::IsMenuShadows  
 Çerçeve gölgesi açılır menüler çizer olup olmadığını gösterir.  
  
```  
static BOOL IsMenuShadows();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Menü gölgeleri framework çizer Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCMenuBar::EnableMenuShadows](#enablemenushadows) etkinleştirin veya bu özelliği devre dışı bırakmak için yöntem.  
  
##  <a name="isrecentlyusedmenus"></a>  CMFCMenuBar::IsRecentlyUsedMenus  
 Son kullanılan menü komutlarını menü çubuğunda görüntülenip görüntülenmeyeceğini gösterir.  
  
```  
static BOOL IsRecentlyUsedMenus();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CMFCMenuBar` nesnesini gösterir son kullanılan menü komutlarını; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevini [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus) denetlemek için menü çubuğundaki son olup olmadığını gösterir menü komutlarını kullanılır.  
  
##  <a name="isshowallcommands"></a>  CMFCMenuBar::IsShowAllCommands  
 Menüleri tüm komutları görüntüler olup olmadığını gösterir.  
  
```  
static BOOL IsShowAllCommands();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CMFCMenuBar` tüm görüntüler komutları; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CMFCMenuBar` nesne ya da tüm komutları ya komutları yalnızca bir kısmı göstermek için yapılandırılabilir. Bu özellik hakkında daha fazla bilgi için bkz: [CMFCMenuBar sınıfı](../../mfc/reference/cmfcmenubar-class.md).  
  
 `IsShowAllCommands` Bu özellik için nasıl yapılandırıldığını söyleyecektir `CMFCMenuBar` nesnesi. Hangi menü komutlarını gösterilen denetlemek için yöntemleri kullanın [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) ve [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus).  
  
##  <a name="isshowallcommandsdelay"></a>  CMFCMenuBar::IsShowAllCommandsDelay  
 Gösterir olup olmadığını [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesne kısa bir gecikmeyle tüm komutları görüntüler.  
  
```  
static BOOL IsShowAllCommandsDelay();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü çubuğu kısa bir gecikmeyle menülerin görüntülerse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü çubuğunda görünen son kullanılan öğeler için yapılandırdığınızda, menü çubuğundaki iki yoldan biriyle tam menüsünü görüntüler:  
  
-   Ne zaman menünün altındaki okunu üzerinden imleç kullanıcı gezinen gelen programlı bir gecikmeden sonra tam menüsünü görüntüler.  
  
-   Kullanıcı menü ekranın alt kısmındaki oka tıkladıktan sonra tam menüsünü görüntüler.  
  
 Varsayılan olarak, tüm `CMFCMenuBar` nesneleri kısa bir gecikmeyle tam menüsünü görüntülemek için seçeneği kullanın. Bu seçenek programlı olarak değiştirilemez `CMFCMenuBar` sınıfı. Ancak, bir kullanıcı davranışı araç çubuğunu özelleştirme sırasında kullanarak değiştirebilir **Özelleştir** iletişim kutusu...  
  
##  <a name="loadstate"></a>  CMFCMenuBar::LoadState  
 Menü çubuğu durumunu Windows kayıt defterinden yükler.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Windows kayıt defteri anahtarının yolunu içeren bir dize.  
  
 [in] *nIndex*  
 Menü çubuğu denetim kimliği.  
  
 [in] *uiID*  
 Ayrılmış bir değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCMenuBar::SaveState](#savestate) yöntemi menü çubuğu durumunu kayıt defterine Kaydet. Kaydedilen bilgi menü öğeleri, yerleştirme durumu ve menü çubuğu konumunu içerir.  
  
 Çoğu durumda, uygulamanızın arama `LoadState`. Framework çalışma başlatır, bu yöntemi çağırır.  
  
##  <a name="onchangehot"></a>  CMFCMenuBar::OnChangeHot  

  
```  
virtual void OnChangeHot(int iHot);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iHot*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondefaultmenuloaded"></a>  CMFCMenuBar::OnDefaultMenuLoaded  
 Kaynak dosyadan menüsü kaynak yüklediğinde framework bu yöntemi çağırır.  
  
```  
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hMenu*  
 Menü tanıtıcı bağlı `CMFCMenuBar` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev varsayılan uygulaması hiçbir şey yapmaz. Kaynak dosyadan menüsü kaynak framework yüklendikten sonra özel kod yürütmek için bu işlevi geçersiz kılar.  
  
##  <a name="onsendcommand"></a>  CMFCMenuBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsetdefaultbuttontext"></a>  CMFCMenuBar::OnSetDefaultButtonText  
 Kullanıcı menü çubuğunda bir öğe metninin değiştirdiğinde framework bu yöntemi çağırır.  
  
```  
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
 Bir işaretçi [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) özelleştirmek için kullanıcının istediği nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` framework menü çubuğunda kullanıcı değişiklikleri uygulanıyor; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için varsayılan uygulaması düğmenin metni kullanıcı sağlar metne dönüştürür.  
  
##  <a name="ontoolhittest"></a>  CMFCMenuBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *noktası*  
 [in] *PTI*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="pretranslatemessage"></a>  CMFCMenuBar::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMsg*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="restoreoriginalstate"></a>  CMFCMenuBar::RestoreOriginalstate  
 Kullanıcının seçtiği zaman çerçevesi tarafından çağrılır **sıfırlama** gelen **Özelleştir** iletişim kutusu.  
  
```  
virtual BOOL RestoreOriginalstate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı seçtiğinde bu yöntem çağrılır **sıfırlama** özelleştirme menüsünde. El ile de program aracılığıyla menü çubuğu durumunu sıfırlamak için bu yöntemi çağırabilirsiniz. Bu yöntem, özgün durumuna kaynak dosyadan yükler.  
  
 Kullanıcı seçtiğinde herhangi işleme yapmak istiyorsanız bu yöntemi geçersiz kılın **sıfırlama** seçeneği.  
  
##  <a name="savestate"></a>  CMFCMenuBar::SaveState  
 Durumunu kaydeder [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Windows kayıt defterinde nesnesi.  
  
```  
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT)-1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Windows kayıt defteri anahtarının yolunu içeren bir dize.  
  
 [in] *nIndex*  
 Menü çubuğu denetim kimliği.  
  
 [in] *uiID*  
 Ayrılmış bir değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` başarılı olursa; Aksi takdirde `FALSE`;  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, uygulamanızın arama `SaveState`. Çalışma alanı serileştirildiğinde framework bu yöntemi çağırır. Daha fazla bilgi için bkz: [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
 Kaydedilen bilgi menü öğeleri, yerleştirme durumu ve menü çubuğu konumunu içerir.  
  
##  <a name="setdefaultmenuresid"></a>  CMFCMenuBar::SetDefaultMenuResId  
 Ayarlar için varsayılan menü bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesne tabanlı kaynak kimliğine göre  
  
```  
void SetDefaultMenuResId(UINT uiResId);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiResId*  
 Yeni varsayılan menü kaynak kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) yöntemi kaynak dosyasından varsayılan menüsünü geri yükler.  
  
 Kullanım [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) geri yüklemeden varsayılan menüsünü alma yöntemi.  
  
##  <a name="setforcedownarrows"></a>  CMFCMenuBar::SetForceDownArrows  

  
```  
void SetForceDownArrows(BOOL bValue);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bDeğer*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setmaximizemode"></a>  CMFCMenuBar::SetMaximizeMode  
 Çerçeve bir MDI alt görüntü modu değiştirir ve menü çubuğu güncelleştirilmelidir bu yöntemi çağırır.  
  
```  
void SetMaximizeMode(
    BOOL bMax,  
    CWnd* pWnd = NULL,  
    BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bMax*  
 Modunu belirten bir Boole değeri. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 [in] *pWnd*  
 Değişen MDI alt pencere için bir işaretçi.  
  
 [in] *bRecalcLayout*  
 Menü çubuğu yerleşimini hemen hesaplanması olup olmadığını belirten bir Boole değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 MDI alt pencere ekranı, MDI ana çerçeve penceresine bağlı bir menü çubuğunda Sistem menüsünü görüntüler ve **simge durumuna küçült**, **Ekranı Kapla** ve **Kapat** düğmeler. Varsa *bMax* olan `TRUE` ve *pWnd* değil `NULL`, MDI alt pencere ekranı ve menü çubuğunda ek denetimleri eklemeniz gerekir. Aksi takdirde, menü çubuğundaki normal durumuna geri döner.  
  
##  <a name="setmenubuttonrtc"></a>  CMFCMenuBar::SetMenuButtonRTC  
 Kullanıcı düğmeleri oluşturduğunda framework kullandığı çalışma zamanı sınıf bilgileri ayarlar.  
  
```  
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMenuButtonRTC*  
 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bilgi bir sınıf için türetilen [CMFCMenuButton sınıfı](../../mfc/reference/cmfcmenubutton-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı menü çubuğuna yeni düğmeler ekler, framework düğmelerin dinamik olarak oluşturur. Varsayılan olarak, oluşturduğu `CMFCMenuButton` nesneleri. Framework oluşturur düğmesi nesnelerin türünü değiştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="setmenufont"></a>  CMFCMenuBar::SetMenuFont  
 Tüm menü çubukları yazı tipini uygulamanızda ayarlar.  
  
```  
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpLogFont*  
 Bir işaretçi bir [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/bb773327) ayarlamak için yazı tipini tanımlar yapısı.  
  
 [in] *bHorz*  
 İstiyorsanız, doğru *lpLogFont* yatay yazı tipi için kullanılacak istiyorsanız dikey yazı tipini FALSE kullanılacak parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 İki yazı tipi kullanılan tüm `CMFCMenuBar` nesneleri. Bu ayrı yazı tipleri yatay ve dikey menü çubukları için kullanılır.  
  
 Yazı tipi ayarlarını genel değişkenleri ve tüm etkiler `CMFCMenuBar` nesneleri.  
  
##  <a name="setrecentlyusedmenus"></a>  CMFCMenuBar::SetRecentlyUsedMenus  
 Menü komutları olup bir menü çubuğu son görüntüler kullanılan denetimler.  
  
```  
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iyi*  
 Son kullanılan menü komutlarını görüntülenip görüntülenmediğini denetler bir Boole değeri.  
  
##  <a name="setshowallcommands"></a>  CMFCMenuBar::SetShowAllCommands  
 Bir menüdeki kullanılabilir tüm komutları gösterip göstermediğini denetler.  
  
```  
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bShowAllCommands*  
 Açılır menüde tüm menü komutlarını gösterip göstermediğini belirten bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir menüyü tüm menü komutlarını görüntülenmiyorsa, nadiren kullanılan komutları gizler. Menü komutları görüntüleme hakkında daha fazla bilgi için bkz: [CMFCMenuBar sınıfı](../../mfc/reference/cmfcmenubar-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
