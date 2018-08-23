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
ms.openlocfilehash: a4d8961cc929196c21838fd21132146deddabcc1
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42466282"
---
# <a name="cmfcmenubar-class"></a>CMFCMenuBar sınıfı
Yerleştirme uygulayan bir menü çubuğu.  
 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(Geçersiz kılmaları `CMFCToolBar::AdjustLocations`.)|  
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|Araç çubuğu düğmeleri görüntülerinde altındaki metin etiketi gösterilip gösterilemeyeceğini belirtir. (Geçersiz kılmaları [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Geçersiz kılmaları `CPane::AllowShowOnPaneMenu`.)|  
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Araç yatay boyutunu hesaplar. (Geçersiz kılmaları [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|  
|[CMFCMenuBar::CalcLayout](#calclayout)|(Geçersiz kılmaları `CMFCToolBar::CalcLayout`.)|  
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Araç çubuğu düğmeleri maksimum yüksekliğini hesaplar. (Geçersiz kılmaları [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|  
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|Kullanıcı araç çubuğunu kapat olup olmadığını belirtir. (Geçersiz kılmaları [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|  
|[CMFCMenuBar::CanBeRestored](#canberestored)|Sistem bir araç çubuğunun özgün durumuna özelleştirme sonrasında geri yükleyebilirsiniz olup olmadığını belirler. (Geçersiz kılmaları [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|  
|[CMFCMenuBar::Create](#create)|Bir menü denetimi oluşturur ve ona bağlanan bir `CMFCMenuBar` nesne.|  
|[CMFCMenuBar::CreateEx](#createex)|Oluşturur bir `CMFCMenuBar` ek stil seçeneklerini nesne.|  
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|Başlatan bir `CMFCMenuBar` nesne. Doldurulmuş bir için şablon görevi gören bir HMENU parametreyi kabul eden `CMFCMenuBar`.|  
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Sağlayan bir **yardımcı** menü çubuğunun sağ tarafında bulunan açılan kutusu.|  
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|Açılır menüler gölgesi görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(Geçersiz kılmaları [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|  
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|Araç çubuğu düğmeleri genişliğini döndürür. (Geçersiz kılmaları [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|  
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Özgün kaynak dosya menüsüne bir tanıtıcı döndürür.|  
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Kaynak dosyanın özgün menüsü kaynak tanımlayıcısı döndürür.|  
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||  
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||  
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Bir işaretçi döndürür **yardımcı** birleşik giriş kutusu.|  
|[CMFCMenuBar::GetHMenu](#gethmenu)|Bağlı menüsüne tanıtıcısını döndürür `CMFCMenuBar` nesne.|  
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Menu nesnelerinin geçerli genel yazı tipini döndürür.|  
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Sağlanan öğe dizini ile ilişkili araç çubuğu düğmesini döndürür.|  
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Araç çubuğu düğmeleri yüksekliğini döndürür. (Geçersiz kılmaları [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|  
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||  
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||  
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||  
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Devre dışı bırakılmış menü öğeleri vurgulanır olup olmadığını gösterir.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Araç çubuğu kenarlık genişletilmiş düğmeleri görüntüleyip görüntülemeyeceğini belirler. (Geçersiz kılmaları [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|  
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|Devre dışı öğeler vurgulanmıştır olup olmadığını gösterir.|  
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Shadows için açılır menüler çizilir gösterir.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|Son kullanılan menü komutlarını menü çubuğundan görüntülenip görüntülenmeyeceğini gösterir.|  
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|Açılır menüler tüm komutları görüntüleyip görüntülemediğini gösterir.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Menüleri, kısa bir gecikmeden sonra tüm komutları görüntüleyip görüntülemediğini gösterir.|  
|[CMFCMenuBar::LoadState](#loadstate)|Durumunu yükler `CMFCMenuBar` kayıt defterinden nesne.|  
|[CMFCMenuBar::OnChangeHot](#onchangehot)|Kullanıcı araç çubuğunda bir düğmeyi seçtiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Çerçeve penceresi kaynak dosyasından varsayılan menüsünü yüklendiğinde framework tarafından çağırılır.|  
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(Geçersiz kılmaları `CMFCToolBar::OnSendCommand`.)|  
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|Bir menü özelleştirme modunda olduğunda ve kullanıcı bir menü öğesinin metni değiştirir framework tarafından çağırılır.|  
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(Geçersiz kılmaları `CMFCToolBar::OnToolHitTest`.)|  
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Geçersiz kılmaları `CMFCToolBar::PreTranslateMessage`.)|  
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|Bir menü özelleştirme modunda ve kullanıcının seçtiği framework tarafından çağırılır **sıfırlama** bir menü çubuğu için.|  
|[CMFCMenuBar::SaveState](#savestate)|Durumunu kaydeder `CMFCMenuBar` kayıt defterine nesne.|  
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Özgün menüsü kaynak dosyasında ayarlar.|  
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||  
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|Bir MDI alt penceresinin kendi görüntü modu değiştiğinde framework tarafından çağırılır. Bu yöntem, MDI alt penceresi yeni ekranı veya artık tam ekran, menü çubuğu günceller.|  
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Kullanıcı, dinamik olarak menü düğmesi oluşturduğunda, oluşturulan çalışma zamanı sınıf bilgileri ayarlar.|  
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Uygulamadaki tüm menüleri yazı tipini ayarlar.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|Bir menü çubuğu son kullanılan menü komutları görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|Menü çubuğu tüm komutları gösterip göstermediğini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCMenuBar` Yerleştirme işlevlerini uygulayan bir menü çubuğu bir sınıftır. Bu araç çubuğu benzer olsa da, kapatılamaz - her zaman görüntülenir.  
  
 `CMFCMenuBar` Son kullanılan menü öğesi nesneleri görüntüleme seçeneği destekler. Bu seçenek etkinleştirilirse, `CMFCMenuBar` ilk görüntülenirken yalnızca kullanılabilir komutları kümesini görüntüler. Bundan sonra yakın zamanda kullanılan komutlar komutları özgün alt kümesi ile birlikte görüntülenir. Ayrıca, kullanıcının her zaman tüm kullanılabilir komutları görüntülemek için menü genişletebilirsiniz. Bu nedenle, her bir kullanılabilir komut sürekli görüntülemek veya yalnızca, son seçilmişse görüntülemek için yapılandırılır.  
  
 Kullanılacak bir `CMFCMenuBar` nesne, ana pencere çerçevesi nesnesinde ekleme. İşleme sırasında `WM_CREATE` iletisi, çağrı `CMFCMenuBar::Create` veya `CMFCMenuBar::CreateEx`. İşlevi oluşturduğunuz bağımsız olarak kullanmak için ana çerçeve penceresine bir işaretçi geçirin. Ardından çağırarak yerleştirme etkinleştirin [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Bu menü çağırarak dock [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCMenuBar` sınıfı. Örnek bölmesinin stilini ayarlayın, özelleştirme düğmesini etkinleştir, etkinleştir Yardım kutusu, gölge açılır menüler için etkinleştirmek ve menü çubuğu güncelleştirmek nasıl gösterir. Bu kod parçacığı parçasıdır [IE gösterim örneği](../../visual-cpp-samples.md).  
  
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
 Menü çubuğundaki menü öğelerinin konumları ayarlar.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="allowchangetextlabels"></a>  CMFCMenuBar::AllowChangeTextLabels  
 Metin etiketlerini menü çubuğundaki resim altında izin verilip verilmeyeceğini belirler.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin etiketlerini resim altında göstermek kullanıcı seçebilir, TRUE döndürür.  
  
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
 Bir menü denetimi oluşturur ve ona bağlanan bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesne.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,  
    UINT nID = AFX_IDW_MENUBAR);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pParentWnd*  
 Yeni üst penceresine bir işaretçi `CMFCMenuBar` nesne.  
  
 [in] *dwStyle*  
 Yeni menü çubuğu stili.  
  
 [in] *nID*  
 Alt pencere menü çubuğunun kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturun, sonra bir `CMFCMenuBar` nesne çağırmanız `Create`. Bu yöntem oluşturur `CMFCMenuBar` denetlemek ve ekler `CMFCMenuBar` nesne.  
  
 Toolbar stilleri hakkında daha fazla bilgi için bkz: [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).  
  
##  <a name="createex"></a>  CMFCMenuBar::CreateEx  
 Oluşturur bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) belirtilen Genişletilmiş stiller nesnesi.  
  
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
 Yeni üst pencere işaretçisi `CMFCMenuBar` nesne.  
  
 [in] *dwCtrlStyle*  
 Ek stilleri için yeni menü çubuğu.  
  
 [in] *dwStyle*  
 Yeni menü çubuğunun ana stili.  
  
 [in] *rcBorders*  
 A `CRect` kenarlıklarını boyutunu belirten parametresi `CMFCMenuBar` nesne.  
  
 [in] *nID*  
 Alt pencere menü çubuğunun kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi yerine kullanmalısınız [CMFCMenuBar::Create](#create) araç çubuğu stili yanı sıra stilleri belirtmek istediğinizde. Bazı sık kullanılan ek TBSTYLE_TRANSPARENT ve CBRS_TOP stillerdir.  
  
 Ek stilleri bir listesi için bkz. [araç çubuğu denetimi ve düğme stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760439), [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498), ve [ortak pencere stilleri](http://msdn.microsoft.com/library/windows/desktop/ms632600).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `CreateEx` yöntemi `CMFCMenuBar` sınıfı. Bu kod parçacığı parçasıdır [IE gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]  
  
##  <a name="createfrommenu"></a>  CMFCMenuBar::CreateFromMenu  
 Başlatan bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesne. Bu yöntem modelleri `CMFCMenuBar` HMENU parametresi sonra nesne.  
  
```  
virtual void CreateFromMenu(
    HMENU hMenu,  
    BOOL bDefaultMenu = FALSE,  
    BOOL bForceUpdate = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hMenu*  
 Bir menü kaynağı için tanıtıcı. `CreateFromMenu` Bu kaynak için bir şablon olarak kullandığı `CMFCMenuBar`.  
  
 [in] *bDefaultMenu*  
 Yeni menü varsayılan menüsünü olup olmadığını belirten bir Boole değeri.  
  
 [in] *bForceUpdate*  
 Bu yöntem bir menü güncelleştirme zorlar olup olmadığını gösteren bir Boole değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir menü kaynağı olarak aynı menü öğeleri için bir menü denetimi istiyorsanız bu yöntemi kullanın. Ya da çağırdıktan sonra bu yöntemi çağırmanız [CMFCMenuBar::Create](#create) veya [CMFCMenuBar::CreateEx](#createex).  
  
##  <a name="enablehelpcombobox"></a>  CMFCMenuBar::EnableHelpCombobox  
 Sağlayan bir **yardımcı** menü çubuğunun sağ tarafında bulunan açılan kutusu.  
  
```  
void EnableHelpCombobox(
    UINT uiID,  
    LPCTSTR lpszPrompt = NULL,  
    int nComboBoxWidth = 150);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiID*  
 Komut Kimliği düğmesine **yardımcı** birleşik giriş kutusu.  
  
 [in] *lpszPrompt*  
 Boş ve etkin değil ise birleşik giriş kutusunda framework görüntüleyen metni içeren bir dize. Örneğin, "Enter metnini buraya".  
  
 [in] *nComboBoxWidth*  
 Birleşik giriş kutusu piksel cinsinden düğmenin genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
 **Yardımcı** birleşik giriş kutusu benzer **yardımcı** Microsoft Word'ün menü çubuğundaki birleşik giriş kutusu.  
  
 Bu yöntemi çağırdığınızda *uiID* 0 olarak ayarlanırsa, bu yöntem birleşik giriş kutusu gizler. Aksi takdirde, bu yöntem birleşik giriş kutusu menü çubuğunun sağ tarafında otomatik olarak görüntüler. Bu yöntem çağrısından sonra çağrı [CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) eklenen bir işaretçi alma için [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesne.  
  
##  <a name="enablemenushadows"></a>  CMFCMenuBar::EnableMenuShadows  
 Açılır menüler için gölgeleri sağlar.  
  
```  
static void EnableMenuShadows(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Shadows açılır menüler için etkin olup olmadığını gösteren bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemde algoritması karmaşıktır ve yavaş sistemlerde uygulamanızın performansını düşürebilir.  
  
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
 Özgün menünün işleyici alır. Framework özgün menüsü kaynak dosyadan yükler.  
  
```  
HMENU GetDefaultMenu() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir menü kaynağı için tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı bir menüsünü özelleştiren, özgün menüsüne bir tanıtıcı almak için bu yöntemi kullanabilirsiniz.  
  
##  <a name="getdefaultmenuresid"></a>  CMFCMenuBar::GetDefaultMenuResId  
 Varsayılan menüsü kaynak tanımlayıcısını alır.  
  
```  
UINT GetDefaultMenuResId() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir menü kaynak tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework yükler için varsayılan menü `CMFCMenuBar` kaynak dosyasından nesnesi.  
  
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
 Bir işaretçi **yardımcı** birleşik giriş kutusu. NULL ise **yardımcı** birleşik giriş kutusu gizli veya etkin değil.  
  
### <a name="remarks"></a>Açıklamalar  
 **Yardımcı** birleşik giriş kutusu menü çubuğunun sağ tarafında bulunur. Yöntem çağrısı [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) bu birleşik giriş kutusu etkinleştirmek için.  
  
##  <a name="gethmenu"></a>  CMFCMenuBar::GetHMenu  
 Menü iliştirilmiş tanıtıcısını alır [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesne.  
  
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
 Yatay veya dikey yazı tipi döndürülüp döndürülmeyeceğini belirleyen bir Boole parametresi. TRUE, yatay yazı tipini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CFont](../../mfc/reference/cfont-class.md) geçerli menü çubuğu yazı tipi içeren bir parametre.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen yazı tipi, uygulama için genel bir parametredir. İki genel yazı tipleri tüm korunur `CMFCMenuBar` nesneleri. Bu ayrı yazı tipleri, yatay ve dikey menü çubukları için kullanılır.  
  
##  <a name="getmenuitem"></a>  CMFCMenuBar::GetMenuItem  
 Alır bir [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) bir menü çubuğu nesnesine bağlı öğesi dizini.  
  
```  
CMFCToolBarButton* GetMenuItem(int iItem) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iItem*  
 Döndürülecek menü öğesi dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi `CMFCToolBarButton` tarafından belirtilen dizin eşleşen nesne *iItem*. Dizin geçersiz olduğu yoksa NULL.  
  
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
 Framework devre dışı bırakılmış menü öğeleri vurgular olup olmadığını denetler.  
  
```  
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bHighlight*  
 Framework kullanılabilir menü öğelerini vurgular olup olmadığını gösteren bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı fareyi üzerine getirdiğinde varsayılan olarak, çerçeve kullanılabilir menü öğelerini vurgulayın değil.  
  
##  <a name="isbuttonextrasizeavailable"></a>  CMFCMenuBar::IsButtonExtraSizeAvailable  

  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ishighlightdisableditems"></a>  CMFCMenuBar::IsHighlightDisabledItems  
 Framework kullanılabilir menü öğelerini vurgular olup olmadığını gösterir.  
  
```  
static BOOL IsHighlightDisabledItems();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanılabilir menü öğelerini vurgulanmış TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı fareyi üzerine getirdiğinde varsayılan olarak, çerçeve kullanılabilir menü öğelerini vurgulayın değil. Kullanım [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) bu özelliği etkinleştirmek için yöntemi.  
  
##  <a name="ismenushadows"></a>  CMFCMenuBar::IsMenuShadows  
 Çerçeve gölgesi açılır menüler çizer olup olmadığını gösterir.  
  
```  
static BOOL IsMenuShadows();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çerçeve menüsü, gölgeler çizer TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCMenuBar::EnableMenuShadows](#enablemenushadows) etkinleştirin veya bu özelliği devre dışı bırakmak için yöntemi.  
  
##  <a name="isrecentlyusedmenus"></a>  CMFCMenuBar::IsRecentlyUsedMenus  
 Son kullanılan menü komutlarını menü çubuğundan görüntülenip görüntülenmeyeceğini gösterir.  
  
```  
static BOOL IsRecentlyUsedMenus();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gösterimiyse `CMFCMenuBar` nesne gösteren kısa bir süre önce kullanılan menü komutları; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevini [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus) denetlemek için menü çubuğunda son olup olmadığını gösterir menü komutları kullanılır.  
  
##  <a name="isshowallcommands"></a>  CMFCMenuBar::IsShowAllCommands  
 Menüler tüm komutları görüntüleyip görüntülemediğini gösterir.  
  
```  
static BOOL IsShowAllCommands();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gösterimiyse `CMFCMenuBar` tüm görüntüler komutları; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CMFCMenuBar` nesne ya da tüm komutlar ya yalnızca bir alt komut göstermek için yapılandırılabilir. Bu özellik hakkında daha fazla bilgi için bkz. [CMFCMenuBar sınıfı](../../mfc/reference/cmfcmenubar-class.md).  
  
 `IsShowAllCommands` Bu özellik için nasıl yapılandırıldığını söyleyecektir `CMFCMenuBar` nesne. Hangi menü komutları gösterilen kontrol etmek için yöntemleri kullanın. [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) ve [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus).  
  
##  <a name="isshowallcommandsdelay"></a>  CMFCMenuBar::IsShowAllCommandsDelay  
 Belirtir olup olmadığını [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesne kısa bir gecikmeden sonra tüm komutları görüntüler.  
  
```  
static BOOL IsShowAllCommandsDelay();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Menü çubuğunda, kısa bir gecikmeyle menülerin görüntüler olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Son kullanılan görünen öğeler için bir menü çubuğu yapılandırdığınızda, menü çubuğu iki yoldan biriyle tam menü görüntüler:  
  
-   Kullanıcı imleci menüsünün alt kısmındaki oka üzerine geldiğinde gelen programlanmış bir gecikmeden sonra tam menü görüntülenir.  
  
-   Kullanıcı menüsünün alt kısmındaki oka tıkladıktan sonra tam menü görüntülenir.  
  
 Varsayılan olarak, tüm `CMFCMenuBar` nesneleri kısa bir gecikmeyle tam menüyü görüntülemek için bu seçeneği kullanın. Bu seçenek programlı olarak değiştirilemez `CMFCMenuBar` sınıfı. Ancak, bir kullanıcı davranışı araç çubuğunu özelleştirme sırasında kullanarak değiştirebilirsiniz **Özelleştir** iletişim kutusu...  
  
##  <a name="loadstate"></a>  CMFCMenuBar::LoadState  
 Menü çubuğunun durumunu Windows kayıt defterinden yükler.  
  
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
 Menü çubuğu denetiminin kimliği.  
  
 [in] *uiID*  
 Ayrılmış bir değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCMenuBar::SaveState](#savestate) menü çubuğunun durumunu kayıt defterine kaydetmek için yöntemi. Menü öğeleri, dock durumu ve menü çubuğunun konumu kaydedilen bilgiler içerir.  
  
 Çoğu durumda, uygulamanızın arama `LoadState`. Çalışma alanı başlattığında framework bu yöntemi çağırır.  
  
##  <a name="onchangehot"></a>  CMFCMenuBar::OnChangeHot  

  
```  
virtual void OnChangeHot(int iHot);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iHot*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondefaultmenuloaded"></a>  CMFCMenuBar::OnDefaultMenuLoaded  
 Kaynak dosyadan menü kaynağı yüklendiğinde framework bu yöntemi çağırır.  
  
```  
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hMenu*  
 Menünün işleyici bağlı `CMFCMenuBar` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevin varsayılan uygulama, hiçbir şey yapmaz. Framework kaynak dosyasından bir menü kaynağı yüklendikten sonra özel kod yürütmek için bu işlevi geçersiz kılar.  
  
##  <a name="onsendcommand"></a>  CMFCMenuBar::OnSendCommand  

  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsetdefaultbuttontext"></a>  CMFCMenuBar::OnSetDefaultButtonText  
 Kullanıcı menü çubuğundaki bir öğenin metin değiştiğinde framework bu yöntemi çağırır.  
  
```  
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pButton*  
 Bir işaretçi [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) özelleştirmek için kullanıcının istediği bir nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Framework menü çubuğuna kullanıcı değişiklikleri geçerliyse TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için varsayılan uygulama düğmenin metni kullanıcının sağladığı metne dönüştürür.  
  
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
 Kullanıcı seçtiğinde framework tarafından çağırılır **sıfırlama** gelen **Özelleştir** iletişim kutusu.  
  
```  
virtual BOOL RestoreOriginalstate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, kullanıcı seçtiğinde çağrılır **sıfırlama** özelleştirme menüsünde. Program aracılığıyla menü çubuğunun durumunu sıfırlamak için bu yöntem el ile de çağırabilirsiniz. Bu yöntem, özgün durumuna kaynak dosyadan yükler.  
  
 Kullanıcının seçtiği herhangi işleme yapmak istiyorsanız bu yöntemi yok sayın **sıfırlama** seçeneği.  
  
##  <a name="savestate"></a>  CMFCMenuBar::SaveState  
 Durumunu kaydeder [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Windows kayıt defterine nesne.  
  
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
 Menü çubuğu denetiminin kimliği.  
  
 [in] *uiID*  
 Ayrılmış bir değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa TRUE; Aksi takdirde FALSE;  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, uygulamanızın arama `SaveState`. Çalışma alanı serileştirilmiş olduğunda framework bu yöntemi çağırır. Daha fazla bilgi için [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
 Menü öğeleri, dock durumu ve menü çubuğunun konumu kaydedilen bilgiler içerir.  
  
##  <a name="setdefaultmenuresid"></a>  CMFCMenuBar::SetDefaultMenuResId  
 Ayarlar için varsayılan menü bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesne kaynak kimliğini temel alarak  
  
```  
void SetDefaultMenuResId(UINT uiResId);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *uiResId*  
 Yeni varsayılan menüsü kaynak kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 [CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) yöntemi varsayılan menüsü kaynak dosyasından geri yükler.  
  
 Kullanım [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) geri yüklemeden varsayılan menüsünü almak için yöntemi.  
  
##  <a name="setforcedownarrows"></a>  CMFCMenuBar::SetForceDownArrows  

  
```  
void SetForceDownArrows(BOOL bValue);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bDeğer*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setmaximizemode"></a>  CMFCMenuBar::SetMaximizeMode  
 Bir MDI alt görüntü modu değişir ve menü çubuğunun güncelleştirilmelidir, framework bu yöntemi çağırır.  
  
```  
void SetMaximizeMode(
    BOOL bMax,  
    CWnd* pWnd = NULL,  
    BOOL bRecalcLayout = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bMax*  
 Modu belirten bir Boolean değer. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
 [in] *pWnd*  
 Değişiyor MDI alt penceresine bir işaretçi.  
  
 [in] *bRecalcLayout*  
 Menü çubuğunun düzenini hemen hesaplanması olup olmadığını belirten bir Boole değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir MDI alt penceresi büyütüldüğünde, MDI ana çerçeve penceresine bağlı bir menü çubuğu sistem menüsünü görüntüler ve **simge durumuna küçült**, **Ekranı Kapla** ve **Kapat** düğmeleri. Varsa *bMax* true'dur ve *pWnd* NULL değil MDI alt penceresi ve menü çubuğu ek denetimler eklemeniz gerekir. Aksi halde menü çubuğu normal durumuna geri döner.  
  
##  <a name="setmenubuttonrtc"></a>  CMFCMenuBar::SetMenuButtonRTC  
 Kullanıcı düğmeleri oluşturduğunda, framework kullandığı çalışma zamanı sınıfı bilgilerini ayarlar.  
  
```  
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pMenuButtonRTC*  
 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bilgi bir sınıf için türetilen [CMFCMenuButton sınıfı](../../mfc/reference/cmfcmenubutton-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı menü çubuğuna yeni düğmeler ekler, framework düğmelerin dinamik olarak oluşturur. Varsayılan olarak, oluşturduğu `CMFCMenuButton` nesneleri. Framework oluşturan düğme nesneleri türünü değiştirmek için bu yöntemi yok sayın.  
  
##  <a name="setmenufont"></a>  CMFCMenuBar::SetMenuFont  
 Tüm menü çubukları için yazı tipini uygulamanızda ayarlar.  
  
```  
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpLogFont*  
 Bir işaretçi bir [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/bb773327) ayarlamak için yazı tipini tanımlar yapısı.  
  
 [in] *bHorz*  
 İsterseniz TRUE *lpLogFont* yatay yazı tipi için kullanılacak istiyorsanız dikey yazı tipini FALSE kullanılacak parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olduysa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 İki yazı tipleri tüm kullanılır `CMFCMenuBar` nesneleri. Bu ayrı yazı tipleri, yatay ve dikey menü çubukları için kullanılır.  
  
 Yazı tipi ayarlarını genel değişkenleri ve tüm etkileyen `CMFCMenuBar` nesneleri.  
  
##  <a name="setrecentlyusedmenus"></a>  CMFCMenuBar::SetRecentlyUsedMenus  
 Menü komutları olup kısa süre önce bir menü çubuğu görüntüler kullanılan denetimler.  
  
```  
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iyi*  
 Son kullanılan menü komutları gösterilip gösterilmediğini denetler bir Boole değeri.  
  
##  <a name="setshowallcommands"></a>  CMFCMenuBar::SetShowAllCommands  
 Bir menü tüm kullanılabilir komutları gösterir olup olmadığını denetler.  
  
```  
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bShowAllCommands*  
 Açılan menüyü menü komutları gösterip göstermediğini belirten bir Boole parametresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir menü menü komutları görüntülenmiyorsa, nadiren kullanılan komutlar gizler. Menü komutlarını görüntüleme hakkında daha fazla bilgi için bkz. [CMFCMenuBar sınıfı](../../mfc/reference/cmfcmenubar-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
