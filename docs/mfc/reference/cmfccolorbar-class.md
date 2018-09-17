---
title: CMFCColorBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5610cd7f5c861fb8f82364e8f1d4d6975a18d7b7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717983"
---
# <a name="cmfccolorbar-class"></a>CMFCColorBar sınıfı
`CMFCColorBar` Sınıfı, bir belge veya uygulamadaki renkleri seçebileceğiniz takma denetim çubuğunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|Oluşturur bir `CMFCColorBar` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorBar::ContextToSize](#contexttosize)|Renk çubuğu denetim çubuğundaki düğmeleri içerecek biçimde gereklidir ve sonra bu düğmeler konumunu ayarlar dikey ve yatay kenar hesaplar.|  
|[CMFCColorBar::CreateControl](#createcontrol)|Bir renk çubuğu denetimi penceresi oluşturur, ekler `CMFCColorBar` nesne ve Denetim belirtilen renk paletini içerecek şekilde yeniden boyutlandırır.|  
|[CMFCColorBar::Create](#create)|Bir renk çubuğu denetimi penceresi oluşturur ve ona ekler `CMFCColorBar` nesne.|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Otomatik düğmenin gizler veya gösterir.|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Etkinleştirir ya da daha fazla renk seçmesine olanak sağlayan bir iletişim kutusunun görüntülenmesini devre dışı bırakır.|  
|[CMFCColorBar::GetColor](#getcolor)|Şu anda seçili rengini alır.|  
|[CMFCColorBar::GetCommandID](#getcommandid)|Geçerli renk çubuğu denetiminin komut Kimliğini alır.|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Bir renk düğmesi odağa sahip olduğunu belirten rengi alır; diğer bir deyişle, düğmesidir *sık erişimli*.|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Sol veya sağ renk hücre istemci alanı sınırı arasındaki alan yatay boşluğu alır.|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Üst veya alt renk hücre ve istemci alanı sınırları arasındaki boşluk Dikey Kenar alır.|  
|[CMFCColorBar::IsTearOff](#istearoff)|Geçerli renk çubuğu yerleştirilebilir olup olmadığını belirtir.|  
|[CMFCColorBar::SetColor](#setcolor)|Şu anda seçili rengini ayarlar.|  
|[CMFCColorBar::SetColorName](#setcolorname)|Belirtilen bir renk için yeni bir ad belirler.|  
|[CMFCColorBar::SetCommandID](#setcommandid)|Yeni bir komut kimliği bir renk çubuğu denetimi için ayarlar.|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Geçerli belgede kullanılan renk listesi ayarlar.|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Sol veya sağ renk hücre istemci alanı sınırı arasındaki alan yatay boşluğu ayarlar.|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Top veya bottom renk hücre ve istemci alanı sınırları arasındaki boşluk olan dikey boşluğu ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Renk çubuğu denetimi renk düğmeleri konumlarını ayarlar.|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Metin etiketi rengi düğmesi değiştirip değiştiremeyeceğini belirtir.|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|Renk çubuğu denetim nesnesi özelleştirme işlemi sırasında bir araç çubuğu listesinde görünüp görünmediğini gösterir.|  
|[CMFCColorBar::CalcSize](#calcsize)|Düzen hesaplama işleminin bir parçası olarak framework tarafından çağırılır.|  
|[CMFCColorBar::CreatePalette](#createpalette)|Palet renkleri, belirtilen bir dizideki renklerle Initalizes.|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Satırlar ve sütunlar renk çubuğu denetim kılavuzundaki sayısını hesaplar.|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Geçerli renk çubuğu gibi çeşitli kullanıcı arabirimi öğeleri görüntülemek için gerekli ek yüksekliği hesaplar **diğer** düğmesi, belge renkleri ve benzeri.|  
|[CMFCColorBar::InitColors](#initcolors)|Renklerle belirtilen bir palet veya sistem varsayılan palet renkleri dizisini başlatır.|  
|[CMFCColorBar::OnKey](#onkey)|Bir kullanıcı bir klavye düğmesine bastığında framework tarafından çağırılır.|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|Açılan denetim hiyerarşisi kapatmak için framework tarafından çağırılır.|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Etkinleştirmek veya öğeyi görüntülenmeden önce bir kullanıcı arabirimi öğesi bir renk çubuğu denetiminin devre dışı bırakmak için framework tarafından çağırılır.|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Renk iletişim kutusu açılır.|  
|[CMFCColorBar::Rebuild](#rebuild)|Tamamen renk çubuğu denetimi yeniden çizer.|  
|[CMFCColorBar::SelectPalette](#selectpalette)|Belirtilen bir cihaz bağlamı mantıksal paletini geçerli renk çubuğu denetiminin üst düğmenin paleti ayarlar.|  
|[CMFCColorBar::SetPropList](#setproplist)|Kümeleri `m_pWndPropList` korumalı veri üyesi için bir özellik Kılavuzu denetimini belirtilen işaretçisi.|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Durum çubuğundaki ileti satırı güncelleştirmek için renk çubuğu denetim sahibi çerçeve penceresi ister.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`m_bInternal`|Fare olayları işlenip işlenmediğini belirleyen bir Boole alan. Genellikle, fare olayları bu alanı TRUE ve FALSE özelleştirme modu olduğunda işlenir.|  
|`m_bIsEnabled`|Bir denetimin etkin olup olmadığını gösteren bir Boole değeri.|  
|`m_bIsTearOff`|Renk çubuğu denetimi yerleştirme destekleyip desteklemediğini belirten bir Boole değeri.|  
|`m_BoxSize`|A [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesini bir renk çubuğu kılavuzda bir hücre boyutunu belirtir.|  
|`m_bShowDocColorsWhenDocked`|Renk çubuğu yerleştirildiğinde, belge renkleri gösterilip gösterilmeyeceğini belirten bir Boole değeri. Daha fazla bilgi için [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_bStdColorDlg`|Standart sistem renk iletişim kutusu gösterilip gösterilmeyeceğini belirten bir Boole değeri veya [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu. Daha fazla bilgi için [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorAutomatic`|A [COLORREF](/windows/desktop/gdi/colorref) , geçerli otomatik renge depolar. Daha fazla bilgi için [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorNames`|Bir [CMap](../../mfc/reference/cmap-class.md) RGB birtakım ilişkilendirir nesne adlarını renkleri.|  
|`m_colors`|A [CArray](../../mfc/reference/carray-class.md) , [COLORREF](/windows/desktop/gdi/colorref) renk çubuğu denetimde görüntülenen renkleri içeren değerleri.|  
|`m_ColorSelected`|A [COLORREF](/windows/desktop/gdi/colorref) değer kullanıcı renk çubuğu denetimi şu anda seçili renk.|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md) , [COLORREF](/windows/desktop/gdi/colorref) değerleri içeren bir belgede şu anda kullanılan renkler.|  
|`m_nCommandID`|Bir renk düğmesi komut kimliği bir işaretsiz tamsayı.|  
|`m_nHorzMargin`|Yatay boşluğu kılavuz renklerin renk düğmeler arasındaki bir tamsayı.|  
|`m_nHorzOffset`|Yatay uzaklığını rengi düğmesi ortasına bir tamsayı. Bu değer, düğme metnini veya resmi bir renk yanı sıra görüntülerse önemlidir.|  
|`m_nNumColumns`|Renklerin renk çubuğu denetim kılavuzundaki sütun sayısı bir tamsayı.|  
|`m_nNumColumnsVert`|Renkleri dikey yönlendirilmiş bir kılavuzda sütun sayısı bir tamsayı.|  
|`m_nNumRowsHorz`|Renkler yatay olarak yönlendirilmiş kılavuzunda sütun sayısı bir tamsayı.|  
|`m_nRowHeight`|Kılavuz renklerin renk düğmesi bir satırın yüksekliğini bir tamsayı.|  
|`m_nVertMargin`|Dikey boşluğu kılavuz renklerin renk düğmeler arasındaki bir tamsayı.|  
|`m_nVertOffset`|Renk düğmesi merkezine dikey uzaklığı bir tamsayı. Bu değer, düğme metnini veya resmi bir renk yanı sıra görüntülerse önemlidir.|  
|`m_Palette`|A [CPalette](../../mfc/reference/cpalette-class.md) renklerin renk çubuğu denetimi kullanılır.|  
|`m_pParentBtn`|Bir işaretçi bir [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) geçerli düğmenin üst nesne. Renk düğmesi araç çubuğu denetimleri bir hiyerarşide veya bir renk özellik Kılavuzu denetimini bu önemli bir değerdir.|  
|`m_pParentRibbonBtn`|Bir işaretçi bir [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) şeritte ve geçerli düğmenin üst düğme nesne. Renk düğmesi araç çubuğu denetimleri bir hiyerarşide veya bir renk özellik Kılavuzu denetimini bu önemli bir değerdir.|  
|`m_pWndPropList`|Bir işaretçi bir [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) nesne.|  
|`m_strAutoColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) diğer bir deyişle görüntülenen metnin **otomatik** düğmesi. Daha fazla bilgi için [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|  
|`m_strDocColors`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) diğer bir deyişle belge renkleri düğmede görüntülenen metin. Daha fazla bilgi için [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_strOtherColor`|A [CString](../../atl-mfc-shared/reference/cstringt-class.md) diğer bir deyişle görüntülenen metnin *diğer* düğmesi. Daha fazla bilgi için [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, oluşturma bir `CMFCColorBar` doğrudan nesne. Bunun yerine, [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) (menüleri ve araç çubukları kullanılan) veya [CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md) oluşturur `CMFCColorBar` nesne.  
  
 `CMFCColorBar` Sınıfı aşağıdaki işlevleri sağlar:  
  
-   Belge renkleri listesini otomatik olarak ayarlar.  
  
-   Kaydeder ve belge durumu ile birlikte durumuna geri yükler.  
  
-   "Otomatik" düğmesini yönetir.  
  
-   Kullanan [CMFCColorPickerCtrl sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md) denetimi özel bir renk seçin.  
  
-   "Etkinleştiriliyorken" durumu destekler (kullanarak oluşturulursa [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md)).  
  
 Birleştirmek için `CMFCColorBar` uygulamanıza işlevsellik:  
  
1.  Normal menü düğmesine oluşturun ve örneğin ID_CHAR_COLOR bir kimliği atayın.  
  
2.  Çerçeve penceresi sınıfınızda geçersiz kılmanız [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) yöntemi ve Değiştir normal menü düğmesi ile bir [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) nesne (çağırarak [CMFCToolBar: : ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).  
  
3.  Stilleri ayarlama ve etkinleştirme veya özellikleri devre dışı `CMFCColorBar` sırasında nesne [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) oluşturma. `CMFCColorMenuButton` Dinamik olarak oluşturur `CMFCColorBar` framework çağırdıktan sonra nesne `CreatePopupMenu` yöntemi.  
  
 Kullanıcı renk çubuğu denetim düğmesine tıkladığında framework kullanan `ON_COMMAND` makrosu renk çubuğu denetiminin üst bildirir. Makro, komut kimliği parametresi renk çubuğu denetim düğmesine (Bu örnekte ID_CHAR_COLOR) 1. adımda atadığınız değerdir. Daha fazla bilgi için [CMFCColorMenuButton sınıfı](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl sınıfı](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndExsınıfı](../../mfc/reference/cframewndex-class.md), ve [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfları.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir renk çubuğu çeşitli yöntemlerle kullanarak yapılandırma işlemi gösterilmektedir `CMFCColorBar` sınıfı. Yöntemleri yatay ve dikey kenar boşluklarının ayarlanmadığı, diğer düğmeyi etkinleştir, bir renk çubuğu denetimi penceresi oluştur ve şu anda seçili rengini ayarlar. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
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
  
##  <a name="adjustlocations"></a>  CMFCColorBar::AdjustLocations  
 Renk çubuğu denetimi renk düğmeleri konumlarını ayarlar.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem WM_SIZE iletisi işlenirken framework tarafından çağırılır.  
  
##  <a name="allowchangetextlabels"></a>  CMFCColorBar::AllowChangeTextLabels  
 Metin etiketi rengi düğmesi değiştirip değiştiremeyeceğini belirtir.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem her zaman yanlış, metin etiketlerini değiştirilemez yani döndürür. Metin etiketlerini değiştirme etkinleştirmek için bu yöntemi yok sayın.  
  
##  <a name="allowshowonlist"></a>  CMFCColorBar::AllowShowOnList  
 Renk çubuğu denetim nesnesi özelleştirme işlemi sırasında bir araç çubuğu listesinde görünüp görünmediğini gösterir.  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman TRUE.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem her zaman TRUE, yani framework renk çubuğu denetimini özelleştirme işlemi sırasında görüntüleyebilirsiniz döndürür. Farklı bir davranış uygulamak için bu yöntemi yok sayın.  
  
##  <a name="calcsize"></a>  CMFCColorBar::CalcSize  
 Düzen hesaplama işleminin bir parçası olarak framework tarafından çağırılır.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Parametreler  
*bVertDock*<br/>
[in] Renk çubuğu denetim dikey olarak yerleştirilir belirtmek için TRUE; Renk çubuğu denetiminin yatay olarak yerleştirildiğini belirtmek için FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Renk çubuğu denetiminde rengi düğmesi bir dizinin boyutu.  
  
##  <a name="cmfccolorbar"></a>  CMFCColorBar::CMFCColorBar  
 Oluşturur bir `CMFCColorBar` nesne.  
  
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
*Renkleri*<br/>
[in] Renk çubuğu denetimi framework görüntüler renkleri dizisi.  
  
*Renk*<br/>
[in] İlk olarak seçilen rengi.  
  
*lpszAutoColor*<br/>
[in] Metin etiketini *otomatik* rengi düğmesi (varsayılan) ya da NULL.  
  
 Standart etiket otomatik düğmenin **otomatik**.  
  
*lpszOtherColor*<br/>
[in] Metin etiketini *diğer* görüntüleyen daha rengi seçimleri veya NULL düğmesi.  
  
 Diğer düğme için standart etiket **daha fazla renk...** .  
  
*lpszDocColors*<br/>
[in] Belge renkleri düğmesinin metin etiketi. Belge renkler paleti belge şu anda kullandığı tüm renkleri listeler.  
  
*lstDocColors*<br/>
[in] Belge şu anda kullandığı renkler listesi.  
  
*nColumns*<br/>
[in] Renkleri dizi sahip sütun sayısı.  
  
*nRowsDockHorz*<br/>
[in] Renk çubuğu yatay yerleştirildiğinde olan satır sayısı.  
  
*nColDockVert*<br/>
[in] Renk Çubuğu dikey yerleştirildiğinde olan sütun sayısı.  
  
*colorAutomatic*<br/>
[in] Otomatik düğmeyi tıklattığınızda, framework uygulanan varsayılan rengi.  
  
*nCommandID*<br/>
[in] Renk çubuğu denetim komut kimliği.  
  
*pParentBtn*<br/>
[in] Bir üst düğme için bir işaretçi.  
  
*src*<br/>
[in] Mevcut bir `CMFCColorBar` yeni içine kopyalanacak nesne `CMFCColorBar` nesne.  
  
*uiCommandID*<br/>
[in] Komut kimliği.  
  
##  <a name="contexttosize"></a>  CMFCColorBar::ContextToSize  
 Renk çubuğu denetim çubuğundaki düğmeleri içerecek biçimde gereklidir ve bu düğmeler konumunu ayarlar dikey ve yatay kenar hesaplar.  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*bSquareButtons*|[in] Renk çubuğu denetim üzerinde düğmeleri şeklini kare olduğunu belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.|  
|*bCenterButtons*|[in] Renk çubuğu denetim düğmesine değişmiştir içeriği ortalanır belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.|  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>  CMFCColorBar::Create  
 Bir renk çubuğu denetimi penceresi oluşturur ve ona ekler `CMFCColorBar` nesne.  
  
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
*pParentWnd*<br/>
[in] Ana pencere işaretçisi.  
  
*dwStyle*<br/>
[in] Bit düzeyinde birleşimi (veya) [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
*nID*<br/>
[in] Komut kimliği.  
  
*pPalette*<br/>
[in] Renk paleti işaretçisi. Varsayılan NULL olur.  
  
*nColumns*<br/>
[in] Renk çubuğu denetiminde sütunların sayısı. Varsayılan değer 0'dır.  
  
*nRowsDockHorz*<br/>
[in] Yatay olarak yerleştirildiğinde renk çubuğu denetiminde satırların sayısı. Varsayılan değer 0'dır.  
  
*nColDockVert*<br/>
[in] Dikey yerleştirildiğinde renk çubuğu denetiminde sütunların sayısı. Varsayılan değer 0'dır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak için bir `CMFCColorBar` nesne, daha sonra bu yöntem sınıf oluşturucusunu çağırın. `Create` Yöntemi Windows denetimi oluşturur ve renk listesi başlatır.  
  
##  <a name="createcontrol"></a>  CMFCColorBar::CreateControl  
 Bir renk çubuğu denetimi penceresi oluşturur, ekler `CMFCColorBar` nesne ve denetimi pencerenin belirtilen renk paletini içerecek şekilde yeniden boyutlandırır.  
  
```  
virtual BOOL CreateControl(
    CWnd* pParentWnd,  
    const CRect& rect,  
    UINT nID,  
    int nColumns=-1,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
*pParentWnd*<br/>
[in] Ana pencere işaretçisi. NULL olamaz.  
  
*Rect*<br/>
[in] Renk çubuğu denetimi çizmek konumu belirtir sınırlayıcı bir dikdörtgen.  
  
*nID*<br/>
[in] Denetim kimliği.  
  
*nColumns*<br/>
[in] Renk çubuğu denetiminde sütunları ideal sayısı. Bu yöntem, bu sayıyı belirtilen renk paletini uyacak şekilde değiştirir. Bu parametre belirtilmezse yani -1 varsayılandır.  
  
*pPalette*<br/>
[in] Palet renkleri ya da NULL işaretçisi. Bu parametre NULL ise 20 renkleri belirtilmiş gibi bu yöntem renk çubuğu denetiminin boyutunu hesaplar. Varsayılan NULL olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemde *rect*, *nColumns*, ve *pPalette* uygun bir sayı veya satırlar ve sütunlar renk çubuğu denetimi ve ardından aramaları hesaplamak için parametreler [CMFCColorBar::Create](#create) yöntemi.  
  
##  <a name="createpalette"></a>  CMFCColorBar::CreatePalette  
 Palet renkleri belirtilen bir dizi renkleri ile başlatır.  
  
```  
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,   
    CPalette& palette);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*arColors*|[in] Renkleri dizisi.|  
|*Palet*|[in] Renkler paleti.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorBar::EnableAutomaticButton  
 Otomatik düğmenin gizler veya gösterir.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
*lpszLabel*<br/>
[in] Metin etiketini *otomatik* rengi düğmesi (varsayılan) ya da NULL.  
  
 Standart etiket otomatik düğmenin **otomatik**.  
  
*colorAutomatic*<br/>
[in] Otomatik düğmeyi tıklattığınızda, framework uygulanan varsayılan rengi.  
  
*bSistemlerde*<br/>
[in] Otomatik düğmenin etkinleştirmek için TRUE; Otomatik düğmenin devre dışı bırakmak için FALSE. Varsayılan değer True'dur.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin etiketini otomatik düğmenin silinir *lpszLabel* parametresi, NULL veya *bSistemlerde* parametredir FALSE.  
  
##  <a name="enableotherbutton"></a>  CMFCColorBar::EnableOtherButton  
 Etkinleştirir ya da daha fazla renk seçmesine olanak sağlayan bir iletişim kutusunun görüntülenmesini devre dışı bırakır.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
*lpszLabel*<br/>
[in] Metin etiketini *diğer* görüntüleyen daha rengi seçimleri veya NULL düğmesi.  
  
 Bu düğme için standart etiket **daha fazla renk...** .  
  
*bAltColorDlg*<br/>
[in] Görüntülemek true [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) ; iletişim kutusu Standart görüntülemek için FALSE [CColorDialog](../../mfc/reference/ccolordialog-class.md) iletişim kutusu. Varsayılan değer True'dur.  
  
*bSistemlerde*<br/>
[in] Düğmesini etkinleştirmek için TRUE; Düğmeyi devre dışı bırakmak için FALSE. Varsayılan değer True'dur.  
  
##  <a name="getcolor"></a>  CMFCColorBar::GetColor  
 Şu anda seçili rengini alır.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda seçili rengi.  
  
##  <a name="getcolorgridsize"></a>  CMFCColorBar::GetColorGridSize  
 Satırlar ve sütunlar renk çubuğu denetim kılavuzundaki sayısını hesaplar.  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*bVertDock*|[in] Dikey olarak yerleşik renk çubuğu denetimi için hesaplama yapmak için TRUE; Aksi takdirde, hesaplama için yatay olarak yerleşik bir denetim gerçekleştirir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi `cx` bileşeni içeren sütunları ve ayarlanmış `cy` bileşeni, satır sayısını içerir.  
  
##  <a name="getcommandid"></a>  CMFCColorBar::GetCommandID  
 Geçerli renk çubuğu denetiminin komut Kimliğini alır.  
  
```  
UINT GetCommandID() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı yeni bir renk seçtiğinde framework komut kimliği üst bildirmek üzere bir WM_COMMAND ileti gönderir. `CMFCColorBar` nesne.  
  
##  <a name="getextraheight"></a>  CMFCColorBar::GetExtraHeight  
 Geçerli renk çubuğu gibi çeşitli kullanıcı arabirimi öğeleri görüntülemek için gerekli ek yüksekliği hesaplar **diğer** düğme veya belge renkleri.  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*nNumColumns*|[in] Renk çubuğu denetimini belge renkleri, belge renkleri kılavuzunda görüntülenecek sütun sayısını içeriyorsa. Aksi takdirde, bu değeri kullanılmaz.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerekli olan hesaplanan ek yüksekliği.  
  
##  <a name="gethighlightedcolor"></a>  CMFCColorBar::GetHighlightedColor  
 Bir renk düğmesi odağa sahip olduğunu belirten rengi alır; diğer bir deyişle, düğmesidir *sık erişimli*.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir RGB değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethorzmargin"></a>  CMFCColorBar::GetHorzMargin  
 Sol veya sağ renk hücre istemci alanı sınırı arasındaki alan yatay boşluğu alır.  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yatay kenar boşluğu.  
  
##  <a name="getvertmargin"></a>  CMFCColorBar::GetVertMargin  
 Üst veya alt renk hücre ve istemci alanı sınırları arasındaki boşluk Dikey Kenar alır.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dikey Kenar boşluğu.  
  
##  <a name="initcolors"></a>  CMFCColorBar::InitColors  
 Renkleri sistem varsayılan paletini ile veya belirtilen bir palet renkleri dizisini başlatır.  
  
```  
static int InitColors(
    CPalette* pPalette,   
    CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*pPalette*|[in] Palet nesne veya NULL bir işaretçi. Bu parametre NULL ise, bu yöntem işletim sisteminin varsayılan palet kullanır.|  
|*arColors*|[in] Renkleri dizisi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Renkler dizideki öğelerin sayısı.  
  
##  <a name="istearoff"></a>  CMFCColorBar::IsTearOff  
 Geçerli renk çubuğu yerleştirilebilir olup olmadığını belirtir.  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli renk çubuğu denetimi yerleştirilebilir ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk çubuğu denetim yerleştirilebilir ise, bir denetim çubuğunu bozuk ve başka bir konumda yerleştirildi.  
  
##  <a name="onkey"></a>  CMFCColorBar::OnKey  
 Bir kullanıcı bir klavye düğmesine bastığında framework tarafından çağırılır.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parametreler  
*nChar*<br/>
[in] Bir kullanıcı basılı anahtarı sanal anahtar kodu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem, belirtilen anahtar işlemleri TRUE; Aksi takdirde FALSE.  
  
##  <a name="onsendcommand"></a>  CMFCColorBar::OnSendCommand  
 Açılan denetimler hiyerarşisini kapatmak için framework tarafından çağırılır.  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*pButton*|[in] Bir araç çubuğu üzerinde bulunduğu bir denetim işaretçisi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.  
  
##  <a name="onupdatecmdui"></a>  CMFCColorBar::OnUpdateCmdUI  
 Etkinleştirmek veya öğeyi görüntülenmeden önce bir kullanıcı arabirimi öğesi bir renk çubuğu denetiminin devre dışı bırakmak için framework tarafından çağırılır.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parametreler  
*pTarget*<br/>
[in] Güncelleştirilecek kullanıcı arabirimi öğesi içeren bir pencere işaretçisi.  
  
*bDisableIfNoHndler*<br/>
[in] İşleyici yok ileti eşlemesi içinde tanımlanmışsa, kullanıcı arabirimi öğesi devre dışı bırakmak için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı, uygulamanızın kullanıcı arabirimi öğesi tıkladığında, öğe, etkin olarak görüntülenip görüntülenmeyeceğini bilmeniz gerekir ya da devre dışı. Komut iletinin hedefi bir on_update_command_uı komut işleyicisi uygulayarak bu bilgileri sağlar. Komutun işlenmesi için bu yöntemi kullanın. Daha fazla bilgi için [Ccmduı sınıfı](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="opencolordialog"></a>  CMFCColorBar::OpenColorDialog  
 Renk iletişim kutusu açılır.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Parametreler  
*colorDefault*<br/>
[in] Renk iletişim kutusu açıldığında, varsayılan olarak seçilidir rengi.  
  
*colorRes*<br/>
[out] Bir kullanıcı seçili rengi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcının seçtiği bir renk TRUE; Renk iletişim kutusu kullanıcı iptal FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="rebuild"></a>  CMFCColorBar::Rebuild  
 Tamamen renk çubuğu denetimi yeniden çizer.  
  
```  
virtual void Rebuild();
```  
  
##  <a name="selectpalette"></a>  CMFCColorBar::SelectPalette  
 Belirtilen bir cihaz bağlamı mantıksal paletini geçerli renk çubuğu denetiminin üst düğmenin paleti ayarlar.  
  
```  
CPalette* SelectPalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*pDC*|[in] Cihaz bağlamı geçerli renk çubuğu denetiminin üst düğmenin işaretçi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli renk çubuğu denetiminin üst düğmenin paleti tarafından değiştirilir palet işaretçisi.  
  
##  <a name="setcolor"></a>  CMFCColorBar::SetColor  
 Şu anda seçili rengini ayarlar.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
*Renk*<br/>
[in] Bir RGB renk değeri.  
  
##  <a name="setcolorname"></a>  CMFCColorBar::SetColorName  
 Belirtilen bir renk için yeni bir ad belirler.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parametreler  
*Renk*<br/>
[in] Renk RGB değeri.  
  
*strName*<br/>
[in] Belirtilen "rengin" yeni adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tüm belirtilen "rengin" adını değiştirir `CMFCColorBar` uygulamanızdaki nesneleri.  
  
##  <a name="setcommandid"></a>  CMFCColorBar::SetCommandID  
 Yeni bir komut kimliği bir renk çubuğu denetimi için ayarlar.  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>Parametreler  
*nCommandID*<br/>
[in] Komut kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Renk çubuğu denetiminin komut Kimliğini değiştirmek ve kimliği değişti denetiminin üst penceresine bildirir için bu yöntemi çağırın.  
  
##  <a name="setdocumentcolors"></a>  CMFCColorBar::SetDocumentColors  
 Geçerli belgede kullanılan renk listesi ayarlar.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
*lpszCaption*<br/>
[in] Renk çubuğu denetimi kilitli olmadığında görüntülenen başlığı.  
  
*lstDocColors*<br/>
[in] Geçerli belge renkleri değiştirir renkleri listesi.  
  
*bShowWhenDocked*<br/>
[in] Renk çubuğu denetimi yerleştirildiğinde, belge renkleri göstermek için TRUE; Aksi takdirde FALSE. Varsayılan değer FALSE olur.  
  
### <a name="remarks"></a>Açıklamalar  
 *Belge renkleri* belgede şu anda kullanılan renkler. Framework belge renkleri listesini otomatik olarak bulundurur, ancak listesini değiştirmek için bu yöntemi kullanabilirsiniz.  
  
##  <a name="sethorzmargin"></a>  CMFCColorBar::SetHorzMargin  
 Sol veya sağ renk hücre ve istemci alanı sınırları arasındaki boşluk olan yatay boşluğu ayarlar.  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>Parametreler  
*nHorzMargin*<br/>
[in] Piksel cinsinden yatay boşluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Oluşturucusu yatay boşluğu 4 piksel olarak ayarlar.  
  
##  <a name="setproplist"></a>  CMFCColorBar::SetPropList  
 Kümeleri `m_pWndPropList` korumalı veri üyesi için bir özellik Kılavuzu denetimini belirtilen işaretçisi.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*pWndList*|[in] Özellik Kılavuzu denetimini nesnesi işaretçisi.|  
  
##  <a name="setvertmargin"></a>  CMFCColorBar::SetVertMargin  
 Top veya bottom renk hücre ve istemci alanı sınırları arasındaki boşluk olan dikey boşluğu ayarlar.  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>Parametreler  
*nVertMargin*<br/>
[in] Dikey Kenar boşluğunun piksel.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Oluşturucu dikey boşluğu 4 piksel olarak ayarlar.  
  
##  <a name="showcommandmessagestring"></a>  CMFCColorBar::ShowCommandMessageString  
 Durum çubuğundaki ileti satırı güncelleştirmek için renk çubuğu denetim sahibi çerçeve penceresi ister.  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parametreler  
*uiCmdId*<br/>
[in] Komut kimliği. (Bu parametre yoksayılır.)  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, renk çubuğu denetiminin sahibine WM_SETMESSAGESTRING ileti gönderir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
