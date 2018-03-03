---
title: "CMFCColorBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorBar [MFC], CMFCColorBar
- CMFCColorBar [MFC], ContextToSize
- CMFCColorBar [MFC], CreateControl
- CMFCColorBar [MFC], Create
- CMFCColorBar [MFC], EnableAutomaticButton
- CMFCColorBar [MFC], EnableOtherButton
- CMFCColorBar [MFC], GetColor
- CMFCColorBar [MFC], GetCommandID
- CMFCColorBar [MFC], GetHighlightedColor
- CMFCColorBar [MFC], GetHorzMargin
- CMFCColorBar [MFC], GetVertMargin
- CMFCColorBar [MFC], IsTearOff
- CMFCColorBar [MFC], SetColor
- CMFCColorBar [MFC], SetColorName
- CMFCColorBar [MFC], SetCommandID
- CMFCColorBar [MFC], SetDocumentColors
- CMFCColorBar [MFC], SetHorzMargin
- CMFCColorBar [MFC], SetVertMargin
- CMFCColorBar [MFC], AdjustLocations
- CMFCColorBar [MFC], AllowChangeTextLabels
- CMFCColorBar [MFC], AllowShowOnList
- CMFCColorBar [MFC], CalcSize
- CMFCColorBar [MFC], CreatePalette
- CMFCColorBar [MFC], GetColorGridSize
- CMFCColorBar [MFC], GetExtraHeight
- CMFCColorBar [MFC], InitColors
- CMFCColorBar [MFC], OnKey
- CMFCColorBar [MFC], OnSendCommand
- CMFCColorBar [MFC], OnUpdateCmdUI
- CMFCColorBar [MFC], OpenColorDialog
- CMFCColorBar [MFC], Rebuild
- CMFCColorBar [MFC], SelectPalette
- CMFCColorBar [MFC], SetPropList
- CMFCColorBar [MFC], ShowCommandMessageString
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04dcf7628e45d4c43ffbd5bbcd85132092ca04a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccolorbar-class"></a>CMFCColorBar sınıfı
`CMFCColorBar` Sınıfı, bir belgenin veya uygulamanın renkleri seçebilirsiniz yerleşik bir denetim çubuğu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|Oluşturan bir `CMFCColorBar` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorBar::ContextToSize](#contexttosize)|Renk çubuğu denetimi düğmeleri içermesi gerekir ve bu düğmeleri konumunu ayarlar dikey ve yatay kenar boşluklarını hesaplar.|  
|[CMFCColorBar::CreateControl](#createcontrol)|Renk çubuğu denetimi penceresi oluşturur, ekleninceye `CMFCColorBar` nesne ve Denetim belirtilen renk paletini içerecek şekilde yeniden boyutlandırır.|  
|[CMFCColorBar::Create](#create)|Renk çubuğu denetimi penceresi oluşturur ve ona ekler `CMFCColorBar` nesnesi.|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Gösterir veya gizler otomatik düğmesi.|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Etkinleştirir veya daha fazla renk seçmesini sağlayan bir iletişim kutusu görüntülenmesini devre dışı bırakır.|  
|[CMFCColorBar::GetColor](#getcolor)|Seçili renk alır.|  
|[CMFCColorBar::GetCommandID](#getcommandid)|Geçerli renk çubuğu denetiminin komut Kimliğini alır.|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Bir renk düğmesi odağa sahip güveninin rengi alır; diğer bir deyişle, düğme olan *etkin*.|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Sol veya sağ renk hücre ve istemci alanı sınır arasındaki boşluğu yatay kenar alır.|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Üst veya alt renk hücre ve istemci alanı sınır arasındaki boşluğu Dikey Kenar alır.|  
|[CMFCColorBar::IsTearOff](#istearoff)|Geçerli renk çubuğu aygıtsa olup olmadığını gösterir.|  
|[CMFCColorBar::SetColor](#setcolor)|Şu anda seçili rengini belirler.|  
|[CMFCColorBar::SetColorName](#setcolorname)|Belirli bir renk için yeni bir ad ayarlar.|  
|[CMFCColorBar::SetCommandID](#setcommandid)|Renk çubuğu denetimi için yeni bir komut kimliği ayarlar.|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Geçerli belgede kullanılan renk listesi ayarlar.|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Sol veya sağ renk hücre ve istemci alanı sınır arasındaki boşluk yatay boşluğu ayarlar.|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Üst veya alt renk hücre ve istemci alanı sınır arasındaki boşluk dikey boşluğu ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Renk çubuğu denetimi renk düğmeleri konumlarını ayarlar.|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Renk düğmelerinin metin etiketi değişip değişemeyeceğini gösterir.|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|Renk çubuğu denetim nesnesi özelleştirme işlemi sırasında bir araç çubuğu listesinde görünüp görünmediğini gösterir.|  
|[CMFCColorBar::CalcSize](#calcsize)|Düzen hesaplama işleminin parçası olarak çerçevesi tarafından çağrılır.|  
|[CMFCColorBar::CreatePalette](#createpalette)|Palet renkleri belirtilen bir dizi renkleri ile Initalizes.|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Satır ve sütun sayısı, bir renk çubuğu denetiminin kılavuzunda hesaplar.|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Geçerli renk çubuğu gibi çeşitli kullanıcı arabirimi öğeleri görüntülemek için gerekli ek yüksekliği hesaplar **diğer** düğmesi, belge renkleri ve benzeri.|  
|[CMFCColorBar::InitColors](#initcolors)|Renklerle belirtilen paleti veya sistem varsayılan palet renkleri dizisini başlatır.|  
|[CMFCColorBar::OnKey](#onkey)|Bir kullanıcı bir klavye düğmesine bastığında çerçevesi tarafından çağrılır.|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|Açılan denetimler hiyerarşisini kapatmak için çerçevesi tarafından çağrılır.|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Etkinleştirmek veya öğeyi görüntülenmeden önce bir kullanıcı arabirimi öğesi bir renk çubuğu denetiminin devre dışı bırakmak için çerçevesi tarafından çağrılır.|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Renk iletişim kutusu açılır.|  
|[CMFCColorBar::Rebuild](#rebuild)|Renk çubuğu denetimi tamamen yeniden çizer.|  
|[CMFCColorBar::SelectPalette](#selectpalette)|Belirtilen cihaz bağlamı mantıksal paletini geçerli renk çubuğu denetiminin üst düğmesi paletini belirler.|  
|[CMFCColorBar::SetPropList](#setproplist)|Ayarlar `m_pWndPropList` belirtilen işaretçiyi özelliği ızgara denetimine veri üyesini korumalı.|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Durum çubuğunda ileti satırı güncelleştirmek için renk çubuğu denetim sahibi çerçeve penceresi ister.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`m_bInternal`|Fare olayları işlenip işlenmediğini belirleyen bir Boolean alan. Bu alan olduğunda fare olayları genellikle, işlenen `TRUE` ve özelleştirme modu `FALSE`.|  
|`m_bIsEnabled`|Bir denetim etkin olup olmadığını gösteren bir Boole değeri.|  
|`m_bIsTearOff`|Renk çubuğu denetimi yerleştirme destekleyip desteklemediğini belirten bir Boole değeri.|  
|`m_BoxSize`|A [CSize](../../atl-mfc-shared/reference/csize-class.md) nesne bir renk çubuğu kılavuzunda bir hücre boyutunu belirtir.|  
|`m_bShowDocColorsWhenDocked`|Renk çubuğu yerleştirildiğinde belge renkleri gösterilip gösterilmeyeceğini belirten bir Boole değeri. Daha fazla bilgi için bkz: [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_bStdColorDlg`|Standart sistem renk iletişim kutusu gösterilip gösterilmeyeceğini belirten bir Boole değeri veya [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu. Daha fazla bilgi için bkz: [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) geçerli otomatik renk depolar. Daha fazla bilgi için bkz: [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorNames`|Bir [CMap](../../mfc/reference/cmap-class.md) RGB kümesi ilişkilendirir nesne adlarını renkleri.|  
|`m_colors`|A [CArray](../../mfc/reference/carray-class.md) , [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) renk çubuğu denetiminde gösterilen renkleri içeren değerleri.|  
|`m_ColorSelected`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) değeri kullanıcının şu anda renk çubuğu denetimini seçtiği rengi.|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md) , [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) bir belgede şu anda kullanılmakta olan renkleri içeren değerleri.|  
|`m_nCommandID`|Bir renk düğmesi komut kimliği imzalanmamış tamsayı.|  
|`m_nHorzMargin`|Yatay kenar kılavuzunda renklerin renk düğmeleri arasında bir tamsayı.|  
|`m_nHorzOffset`|Renk düğmesi merkezine yatay uzaklığı bir tamsayı. Bu değer, düğme metin veya görüntü renk yanı sıra görüntülerse önemlidir.|  
|`m_nNumColumns`|Renklerin renk çubuğu denetim kılavuzunda sütun sayısı bir tamsayı.|  
|`m_nNumColumnsVert`|Renk dikey yönelimli bir kılavuzdaki sütunları sayısı bir tamsayı.|  
|`m_nNumRowsHorz`|Renk yatay olarak yönlendirilmiş bir kılavuzdaki sütunları sayısı bir tamsayı.|  
|`m_nRowHeight`|Bir kılavuz renklerin renk düğmeleri satırının yüksekliğini bir tamsayı.|  
|`m_nVertMargin`|Dikey boşluğu kılavuzunda renklerin renk düğmeleri arasında bir tamsayı.|  
|`m_nVertOffset`|Renk düğmesi merkezine dikey uzaklığı bir tamsayı. Bu değer, düğme metin veya görüntü renk yanı sıra görüntülerse önemlidir.|  
|`m_Palette`|A [CPalette](../../mfc/reference/cpalette-class.md) renklerin renk çubuğu denetiminde kullanılır.|  
|`m_pParentBtn`|Bir işaretçi bir [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) geçerli düğme üst nesne. Renk düğmesi hiyerarşisinde araç çubuğu denetimleri, ya bir renk özelliği kılavuz denetiminde ise bu önemli bir değerdir.|  
|`m_pParentRibbonBtn`|Bir işaretçi bir [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) Şerit'te ve geçerli düğmesinin üst düğme nesne. Renk düğmesi hiyerarşisinde araç çubuğu denetimleri, ya bir renk özelliği kılavuz denetiminde ise bu önemli bir değerdir.|  
|`m_pWndPropList`|Bir işaretçi bir [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) nesnesi.|  
|`m_strAutoColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) diğer bir deyişle görüntülenen metin **otomatik** düğmesi. Daha fazla bilgi için bkz: [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|  
|`m_strDocColors`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) diğer bir deyişle belge renkleri düğmesinde görüntülenen metin. Daha fazla bilgi için bkz: [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_strOtherColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) diğer bir deyişle görüntülenen metin *diğer* düğmesi. Daha fazla bilgi için bkz: [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, değil oluşturduğunuz bir `CMFCColorBar` doğrudan nesne. Bunun yerine, [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) (menüleri ve araç çubuklarını kullanılır) veya [CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md) oluşturur `CMFCColorBar` nesnesi.  
  
 `CMFCColorBar` Sınıfı aşağıdaki işlevleri sağlar:  
  
-   Otomatik olarak belge renk listesi ayarlar.  
  
-   Kaydeder ve belge durumu ile birlikte durumuna geri yükler.  
  
-   "Otomatik" düğmesine yönetir.  
  
-   Kullanan [CMFCColorPickerCtrl sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md) özel bir renk seçmek için denetim.  
  
-   "Etiketleri" durumu destekler (kullanarak oluşturulursa [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md)).  
  
 İçerecek şekilde `CMFCColorBar` uygulamanıza işlevsellik:  
  
1.  Normal menü düğmesi oluşturun ve kimliği, örneğin ID_CHAR_COLOR atayın.  
  
2.  Çerçeve penceresi sınıfında geçersiz kılma [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) yöntemi ve Değiştir normal menü düğmesi ile bir [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) nesne (çağırarak [CMFCToolBar: : ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).  
  
3.  Tüm stilleri ayarlamak ve etkinleştirmek veya özellikleri devre dışı `CMFCColorBar` sırasında nesne [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) oluşturma. `CMFCColorMenuButton` Nesnesi dinamik olarak oluşturur `CMFCColorBar` nesne framework çağrıları sonra `CreatePopupMenu` yöntemi.  
  
 Kullanıcı bir renk çubuğu denetimi düğmesine tıkladığında, çerçeve kullanır `ON_COMMAND` renk çubuğu denetiminin üst bildirmek için makrosu. Makro komut kimliği parametresi renk çubuğu denetimi düğmesini (Bu örnekte ID_CHAR_COLOR) 1. adımda atadığınız değerdir. Daha fazla bilgi için bkz: [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndExsınıfı](../../mfc/reference/cframewndex-class.md), ve [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfları.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir renk çubuğu çeşitli yöntemlerle kullanarak yapılandırmak gösterilmiştir `CMFCColorBar` sınıfı. Yöntemleri yatay ve dikey kenar boşluklarını ayarlama, diğer düğmesini etkinleştirin, renk çubuğu denetimi penceresi oluşturun ve şu anda seçili rengini belirler. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcolorbar.h  
  
##  <a name="adjustlocations"></a>CMFCColorBar::AdjustLocations  
 Renk çubuğu denetimi renk düğmeleri konumlarını ayarlar.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem sırasında çerçevesi tarafından çağrılır `WM_SIZE` ileti işleme.  
  
##  <a name="allowchangetextlabels"></a>CMFCColorBar::AllowChangeTextLabels  
 Renk düğmelerinin metin etiketi değişip değişemeyeceğini gösterir.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem her zaman döndürür `FALSE`, metin etiketleri başka bir deyişle, değiştirilemez. Değiştirme metin etiketleri etkinleştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="allowshowonlist"></a>CMFCColorBar::AllowShowOnList  
 Renk çubuğu denetim nesnesi özelleştirme işlemi sırasında bir araç çubuğu listesinde görünüp görünmediğini gösterir.  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman `TRUE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem her zaman döndürür `TRUE`, framework başka bir deyişle, renk çubuğu denetimi özelleştirme işlemi sırasında görüntüleyebilirsiniz. Farklı bir davranış uygulamak için bu yöntemi geçersiz kılın.  
  
##  <a name="calcsize"></a>CMFCColorBar::CalcSize  
 Düzen hesaplama işleminin parçası olarak çerçevesi tarafından çağrılır.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bVertDock`  
 `TRUE`renk çubuğu denetimi dikey olarak yerleştirilir belirtmek için; `FALSE` renk çubuğu denetimi yatay yerleştirildiğini belirtmek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Renk çubuğu denetimi renk düğmeleri dizi büyüklüğü.  
  
##  <a name="cmfccolorbar"></a>CMFCColorBar::CMFCColorBar  
 Oluşturan bir `CMFCColorBar` nesnesi.  
  
```  
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    int nRowsDockHorz,  
    int nColDockVert,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCColorButton* pParentBtn);

 
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCRibbonColorButton* pParentRibbonBtn);

 
CMFCColorBar(
    CMFCColorBar& src,  
    UINT uiCommandID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`colors`  
 Renk çubuğu denetiminde framework görüntüler renkleri dizisi.  
  
 [in]`color`  
 Başlangıçta seçilen rengi.  
  
 [in]`lpszAutoColor`  
 Metin etiketini *otomatik* (varsayılan) renk düğmesi veya `NULL`.  
  
 Otomatik düğmesi için standart etiket **otomatik**.  
  
 [in]`lpszOtherColor`  
 Metin etiketini *diğer* daha fazla rengi seçimleri görüntüleyen düğmesini veya `NULL`.  
  
 Diğer düğmesi için standart etiket **daha renkleri...** .  
  
 [in]`lpszDocColors`  
 Belge renkleri düğmesi metin etiketi. Belge renk paleti belge şu anda kullandığı tüm renkleri listeler.  
  
 [in]`lstDocColors`  
 Belge şu anda kullandığı renk listesi.  
  
 [in]`nColumns`  
 Renkleri dizisi sahip sütun sayısı.  
  
 [in]`nRowsDockHorz`  
 Renk çubuğu yatay yerleştirildiğinde olan satırların sayısı.  
  
 [in]`nColDockVert`  
 Renk Çubuğu dikey yerleştirildiğinde olan sütun sayısı.  
  
 [in]`colorAutomatic`  
 Otomatik Düğmeye tıkladığınızda, framework uygulanan varsayılan rengi.  
  
 [in]`nCommandID`  
 Renk çubuğu denetim komut kimliği.  
  
 [in]`pParentBtn`  
 Bir üst düğmesini gösteren bir işaretçi.  
  
 [in]`src`  
 Var olan `CMFCColorBar` yeni içine kopyalanacak nesne `CMFCColorBar` nesne.  
  
 [in]`uiCommandID`  
 Komut kimliği.  
  
##  <a name="contexttosize"></a>CMFCColorBar::ContextToSize  
 Renk çubuğu denetimi düğmeleri içermesi gerekir ve bu düğmeleri konumunu ayarlar dikey ve yatay kenar boşluklarını hesaplar.  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`bSquareButtons`|`TRUE`renk çubuğu denetimi düğmeleri şeklini kare; olduğunu belirtmek için Aksi takdirde `FALSE`. Varsayılan değer `TRUE` şeklindedir.|  
|[in]`bCenterButtons`|`TRUE`içeriği bir renk çubuğu denetimi düğmesi değişmiştir ortalanır belirtmek için; Aksi takdirde `FALSE`. Varsayılan değer `TRUE` şeklindedir.|  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>CMFCColorBar::Create  
 Renk çubuğu denetimi penceresi oluşturur ve ona ekler `CMFCColorBar` nesnesi.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle,  
    UINT nID,  
    CPalette* pPalette=NULL,  
    int nColumns=0,  
    int nRowsDockHorz=0,  
    int nColDockVert=0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParentWnd`  
 Üst pencere işaretçi.  
  
 [in]`dwStyle`  
 Bit düzeyinde bileşimini (veya) [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in]`nID`  
 Komut kimliği.  
  
 [in]`pPalette`  
 Renk paletini işaretçi. Varsayılan, `NULL` değeridir.  
  
 [in]`nColumns`  
 Renk çubuğu denetiminde sütunların sayısı. Varsayılan değer 0'dır.  
  
 [in]`nRowsDockHorz`  
 Yatay yerleştirildiğinde renk çubuğu denetiminde satırların sayısı. Varsayılan değer 0'dır.  
  
 [in]`nColDockVert`  
 Dikey yerleştirildiğinde renk çubuğu denetiminde sütunların sayısı. Varsayılan değer 0'dır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak için bir `CMFCColorBar` nesne, sınıf oluşturucu sonra bu yöntemi çağırın. `Create` Yöntemi Windows denetimi oluşturur ve renk listesi başlatır.  
  
##  <a name="createcontrol"></a>CMFCColorBar::CreateControl  
 Renk çubuğu denetimi penceresi oluşturur, ekleninceye `CMFCColorBar` nesne ve belirtilen renk paletini içerecek şekilde denetim yeniden boyutlandırır.  
  
```  
virtual BOOL CreateControl(
    CWnd* pParentWnd,  
    const CRect& rect,  
    UINT nID,  
    int nColumns=-1,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pParentWnd`  
 Üst pencere işaretçi. Olamaz `NULL`.  
  
 [in]`rect`  
 Renk çubuğu denetimi çizmek konumu belirtir sınırlayıcı dikdörtgenini.  
  
 [in]`nID`  
 Denetim kimliği.  
  
 [in]`nColumns`  
 Renk çubuğu denetiminde sütunların ideal sayısı. Bu yöntem, belirtilen renk paletini sığması için bu sayıyı değiştirir. Bu parametre belirtilmezse anlamına gelir -1 varsayılandır.  
  
 [in]`pPalette`  
 Renk paletini işaretçi veya `NULL`. Bu parametre ise `NULL`, 20 renkleri belirtilmiş olması durumunda gibi bu yöntem renk çubuğu denetiminin boyutu hesaplar. Varsayılan, `NULL` değeridir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `rect`, `nColumns`, ve `pPalette` uygun rakam veya satırları ve sütunları renk çubuğu denetimi ve ardından çağrıları hesaplamak için parametreleri [CMFCColorBar::Create](#create) yöntemi.  
  
##  <a name="createpalette"></a>CMFCColorBar::CreatePalette  
 Palet renkleri belirtilen bir dizi renkleri ile başlatır.  
  
```  
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,   
    CPalette& palette);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`arColors`|Renkleri dizisi.|  
|[in]`palette`|Renk paletini.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
##  <a name="enableautomaticbutton"></a>CMFCColorBar::EnableAutomaticButton  
 Gösterir veya gizler otomatik düğmesi.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Metin etiketini *otomatik* (varsayılan) renk düğmesi veya `NULL`.  
  
 Otomatik düğmesi için standart etiket **otomatik**.  
  
 [in]`colorAutomatic`  
 Otomatik Düğmeye tıkladığınızda, framework uygulanan varsayılan rengi.  
  
 [in]`bEnable`  
 `TRUE`Otomatik düğmesini etkinleştirmek için; `FALSE` otomatik düğmesi devre dışı bırakmak için. Varsayılan değer `TRUE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin etiketi otomatik düğmesinin silinir `lpszLabel` parametresi `NULL` veya `bEnable` parametresi `FALSE`.  
  
##  <a name="enableotherbutton"></a>CMFCColorBar::EnableOtherButton  
 Etkinleştirir veya daha fazla renk seçmesini sağlayan bir iletişim kutusu görüntülenmesini devre dışı bırakır.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszLabel`  
 Metin etiketini *diğer* daha fazla rengi seçimleri görüntüleyen düğmesini veya `NULL`.  
  
 Bu düğme için standart etiket **daha renkleri...** .  
  
 [in]`bAltColorDlg`  
 `TRUE`Görüntülenecek [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu; `FALSE` standart görüntülenecek [CColorDialog](../../mfc/reference/ccolordialog-class.md) iletişim kutusu. Varsayılan değer `TRUE` şeklindedir.  
  
 [in]`bEnable`  
 `TRUE`Düğme etkinleştirmek için; `FALSE` düğmesi devre dışı bırakmak için. Varsayılan değer `TRUE` şeklindedir.  
  
##  <a name="getcolor"></a>CMFCColorBar::GetColor  
 Seçili renk alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda seçili rengi.  
  
##  <a name="getcolorgridsize"></a>CMFCColorBar::GetColorGridSize  
 Satır ve sütun sayısı, bir renk çubuğu denetiminin kılavuzunda hesaplar.  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`bVertDock`|`TRUE`dikey olarak yerleşik renk çubuğu denetimi için hesaplama gerçekleştirmek için; Aksi takdirde, hesaplama için yatay olarak sabitlenmiş bir denetim gerçekleştirir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesindeki `cx` sütunlar ve özelliği sayısını içeriyor. bileşen `cy` bileşeni satır sayısını içerir.  
  
##  <a name="getcommandid"></a>CMFCColorBar::GetCommandID  
 Geçerli renk çubuğu denetiminin komut Kimliğini alır.  
  
```  
UINT GetCommandID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı yeni bir renk seçtiğinde framework komut kimliği gönderir bir `WM_COMMAND` üst bildirmek için ileti `CMFCColorBar` nesnesi.  
  
##  <a name="getextraheight"></a>CMFCColorBar::GetExtraHeight  
 Çeşitli kullanıcı arabirimi öğeleri gibi görüntülenecek geçerli renk çubuğu gerektiren ek yüksekliği hesaplar **diğer** düğmesini veya belge rengi.  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`nNumColumns`|Renk çubuğu denetimi belge renkler, belge renkleri ızgarada gösterilecek sütunları sayısını içeriyorsa. Aksi takdirde, bu değer kullanılmaz.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerekli olan hesaplanan ek yüksekliği.  
  
##  <a name="gethighlightedcolor"></a>CMFCColorBar::GetHighlightedColor  
 Bir renk düğmesi odağa sahip güveninin rengi alır; diğer bir deyişle, düğme olan *etkin*.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethorzmargin"></a>CMFCColorBar::GetHorzMargin  
 Sol veya sağ renk hücre ve istemci alanı sınır arasındaki boşluğu yatay kenar alır.  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yatay boşluğu.  
  
##  <a name="getvertmargin"></a>CMFCColorBar::GetVertMargin  
 Üst veya alt renk hücre ve istemci alanı sınır arasındaki boşluğu Dikey Kenar alır.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikey boşluğu.  
  
##  <a name="initcolors"></a>CMFCColorBar::InitColors  
 Belirtilen palet renkleri veya sistem varsayılan palet renkleri dizisini başlatır.  
  
```  
static int InitColors(
    CPalette* pPalette,   
    CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`pPalette`|Palet nesnesine bir işaretçi veya `NULL`. Bu parametre ise `NULL`, bu yöntem işletim sisteminin varsayılan paleti kullanır.|  
|[in]`arColors`|Renkleri dizisi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Renkleri dizideki öğelerin sayısı.  
  
##  <a name="istearoff"></a>CMFCColorBar::IsTearOff  
 Geçerli renk çubuğu aygıtsa olup olmadığını gösterir.  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Geçerli renk çubuğu denetimi aygıtsa Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk çubuğu denetimi aygıtsa, bir denetim çubuğu bozuk ve başka bir konumda yerleştirildi.  
  
##  <a name="onkey"></a>CMFCColorBar::OnKey  
 Bir kullanıcı bir klavye düğmesine bastığında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nChar`  
 Bir kullanıcı basılı anahtarı sanal anahtar kodu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem, belirtilen anahtar; işlediğinde Aksi takdirde `FALSE`.  
  
##  <a name="onsendcommand"></a>CMFCColorBar::OnSendCommand  
 Açılan denetimler hiyerarşisini kapatmak için çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`pButton`|Araç çubuğunda bulunan denetimine işaretçi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Bu yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
##  <a name="onupdatecmdui"></a>CMFCColorBar::OnUpdateCmdUI  
 Etkinleştirmek veya öğeyi görüntülenmeden önce bir kullanıcı arabirimi öğesi bir renk çubuğu denetiminin devre dışı bırakmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pTarget`  
 Güncelleştirilecek kullanıcı arabirimi öğesi içeren bir pencere için işaretçi.  
  
 [in]`bDisableIfNoHndler`  
 `TRUE`kullanıcı arabirimi öğesi hiçbir işleyici varsa devre dışı bırakmak için ileti eşlemesi içinde tanımlanan; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı, uygulamanızın bir kullanıcı arabirimi öğeyi tıklattığında öğesi, etkin olarak görüntülenmesi gerekip gerekmediğini bilmeniz gerekir ya da devre dışı. Komut ileti hedef uygulayarak bu bilgileri sağlar. bir `ON_UPDATE_COMMAND_UI` komut işleyici. Komutu işlemeye yardımcı olmak için bu yöntemi kullanın. Daha fazla bilgi için bkz: [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="opencolordialog"></a>CMFCColorBar::OpenColorDialog  
 Renk iletişim kutusu açılır.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`colorDefault`  
 Renk iletişim kutusu açıldığında, varsayılan olarak seçili rengi.  
  
 [out]`colorRes`  
 Bir kullanıcı seçili rengi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Kullanıcı bir renk; seçtiyseniz `FALSE` kullanıcı renk iletişim kutusunu iptal ederseniz.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="rebuild"></a>CMFCColorBar::Rebuild  
 Renk çubuğu denetimi tamamen yeniden çizer.  
  
```  
virtual void Rebuild();
```  
  
##  <a name="selectpalette"></a>CMFCColorBar::SelectPalette  
 Belirtilen cihaz bağlamı mantıksal paletini geçerli renk çubuğu denetiminin üst düğmesi paletini belirler.  
  
```  
CPalette* SelectPalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`pDC`|Cihaz bağlamı geçerli renk çubuğu denetiminin üst düğmesinin işaretçi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli renk çubuğu denetiminin üst düğmesi palet tarafından değiştirilir palet işaretçi.  
  
##  <a name="setcolor"></a>CMFCColorBar::SetColor  
 Şu anda seçili rengini belirler.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`color`  
 RGB renk değeri.  
  
##  <a name="setcolorname"></a>CMFCColorBar::SetColorName  
 Belirli bir renk için yeni bir ad ayarlar.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`color`  
 Bir renk RGB değeri.  
  
 [in]`strName`  
 Belirtilen renk için yeni ad.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tüm belirtilen renk adını değiştirir `CMFCColorBar` uygulamanızdaki nesneleri.  
  
##  <a name="setcommandid"></a>CMFCColorBar::SetCommandID  
 Renk çubuğu denetimi için yeni bir komut kimliği ayarlar.  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nCommandID`  
 Komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk çubuğu denetiminin komut Kimliğini değiştirmek için ve üst pencere kimliği değişti denetiminin bildirmek için bu yöntemi çağırın.  
  
##  <a name="setdocumentcolors"></a>CMFCColorBar::SetDocumentColors  
 Geçerli belgede kullanılan renk listesi ayarlar.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszCaption`  
 Renk çubuğu denetimi yerleştirilmemişse olduğunda görüntülenen bir resim yazısı.  
  
 [in]`lstDocColors`  
 Geçerli belge renkleri değiştirir renk listesi.  
  
 [in]`bShowWhenDocked`  
 `TRUE`renk çubuğu denetimi yerleştirildiğinde belge renkleri göstermek için; Aksi takdirde `FALSE`. Varsayılan değer `FALSE` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 *Belge renkleri* bir belgede şu anda kullanılmakta olan renkler. Framework belge renkleri listesini otomatik olarak korur, ancak listesini değiştirmek için bu yöntemi kullanabilirsiniz.  
  
##  <a name="sethorzmargin"></a>CMFCColorBar::SetHorzMargin  
 Sol veya sağ renk hücre ve istemci alanını sınır arasındaki boşluk yatay boşluğu ayarlar.  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nHorzMargin`  
 Piksel yatay boşluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Oluşturucusu 4 piksel olarak yatay boşluğu ayarlar.  
  
##  <a name="setproplist"></a>CMFCColorBar::SetPropList  
 Ayarlar `m_pWndPropList` belirtilen işaretçiyi özelliği ızgara denetimine veri üyesini korumalı.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`pWndList`|Özellik kılavuz denetim nesnesine işaretçi.|  
  
##  <a name="setvertmargin"></a>CMFCColorBar::SetVertMargin  
 Üst veya alt renk hücre ve istemci alanı sınır arasındaki boşluk dikey boşluğu ayarlar.  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nVertMargin`  
 Piksel dikey boşluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Oluşturucusu 4 piksel dikey boşluğu ayarlar.  
  
##  <a name="showcommandmessagestring"></a>CMFCColorBar::ShowCommandMessageString  
 Durum çubuğunda ileti satırı güncelleştirmek için renk çubuğu denetim sahibi çerçeve penceresi ister.  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`uiCmdId`  
 Komut kimliği. (Bu parametre yoksayılır.)  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir `WM_SETMESSAGESTRING` renk çubuğu denetim sahibi ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
