---
title: "CMFCVisualManagerVS2005 sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetDockingTabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetMDITabsBordersSize
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetPropertyGridGroupColor
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::GetTabFrameColors
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawCaptionButton
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawPaneCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawSeparator
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawTab
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnDrawToolBoxFrame
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnEraseTabsArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillHighlightedArea
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnFillMiniFrameCaption
- AFXVISUALMANAGERVS2005/CMFCVisualManagerVS2005::OnUpdateSystemColors
dev_langs: C++
helpviewer_keywords:
- CMFCVisualManagerVS2005 [MFC], GetDockingTabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetMDITabsBordersSize
- CMFCVisualManagerVS2005 [MFC], GetPropertyGridGroupColor
- CMFCVisualManagerVS2005 [MFC], GetTabFrameColors
- CMFCVisualManagerVS2005 [MFC], HasOverlappedAutoHideButtons
- CMFCVisualManagerVS2005 [MFC], OnDrawAutoHideButtonBorder
- CMFCVisualManagerVS2005 [MFC], OnDrawCaptionButton
- CMFCVisualManagerVS2005 [MFC], OnDrawPaneCaption
- CMFCVisualManagerVS2005 [MFC], OnDrawSeparator
- CMFCVisualManagerVS2005 [MFC], OnDrawTab
- CMFCVisualManagerVS2005 [MFC], OnDrawToolBoxFrame
- CMFCVisualManagerVS2005 [MFC], OnEraseTabsArea
- CMFCVisualManagerVS2005 [MFC], OnFillAutoHideButtonBackground
- CMFCVisualManagerVS2005 [MFC], OnFillHighlightedArea
- CMFCVisualManagerVS2005 [MFC], OnFillMiniFrameCaption
- CMFCVisualManagerVS2005 [MFC], OnUpdateSystemColors
ms.assetid: ea39b9ae-327e-4a51-bce7-dc84c78f005b
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9678ef4472f2bcb44a04d3484988033542aae243
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcvisualmanagervs2005-class"></a>CMFCVisualManagerVS2005 sınıfı
`CMFCVisualManagerVS2005`bir uygulama Microsoft Visual Studio 2005 çalışmasıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCVisualManagerVS2005 : public CMFCVisualManagerOffice2003  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCVisualManagerVS2005::GetDockingTabsBordersSize](#getdockingtabsborderssize)|Yerleşik ve sekmeli bölme çizer zaman çerçevesi bu yöntemi çağırır. (Geçersiz kılmaları [CMFCVisualManager::GetDockingTabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getdockingtabsborderssize).)|  
|[CMFCVisualManagerVS2005::GetMDITabsBordersSize](#getmditabsborderssize)|Çerçeve penceresi çizer önce MDITabs penceresinin kenarlık boyutunu belirlemek için bu yöntemi çağırır. (Geçersiz kılmaları [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize).)|  
|[CMFCVisualManagerVS2005::GetPropertyGridGroupColor](#getpropertygridgroupcolor)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#getpropertygridgroupcolor).)|  
|[CMFCVisualManagerVS2005::GetTabFrameColors](#gettabframecolors)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::GetTabFrameColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#gettabframecolors).)|  
|[CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons](#hasoverlappedautohidebuttons)|Otomatik olarak gizle düğmeleri geçerli visual Yöneticisi'nde geçersiz kılıp kılmadığını döndürür. (Geçersiz kılmaları [CMFCVisualManager::HasOverlappedAutoHideButtons](../../mfc/reference/cmfcvisualmanager-class.md#hasoverlappedautohidebuttons).)|  
|[CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder](#ondrawautohidebuttonborder)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawautohidebuttonborder).)|  
|[CMFCVisualManagerVS2005::OnDrawCaptionButton](#ondrawcaptionbutton)|(Geçersiz kılmaları `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`.)|  
|[CMFCVisualManagerVS2005::OnDrawPaneCaption](#ondrawpanecaption)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::OnDrawPaneCaption](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawpanecaption).)|  
|[CMFCVisualManagerVS2005::OnDrawSeparator](#ondrawseparator)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::OnDrawSeparator](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawseparator).)|  
|[CMFCVisualManagerVS2005::OnDrawTab](#ondrawtab)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::OnDrawTab](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#ondrawtab).)|  
|[CMFCVisualManagerVS2005::OnDrawToolBoxFrame](#ondrawtoolboxframe)|(Geçersiz kılmaları [CMFCVisualManager::OnDrawToolBoxFrame](../../mfc/reference/cmfcvisualmanager-class.md#ondrawtoolboxframe).)|  
|[CMFCVisualManagerVS2005::OnEraseTabsArea](#onerasetabsarea)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::OnEraseTabsArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onerasetabsarea).)|  
|[CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground](#onfillautohidebuttonbackground)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillautohidebuttonbackground).)|  
|[CMFCVisualManagerVS2005::OnFillHighlightedArea](#onfillhighlightedarea)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::OnFillHighlightedArea](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onfillhighlightedarea).)|  
|[CMFCVisualManagerVS2005::OnFillMiniFrameCaption](#onfillminiframecaption)|(Geçersiz kılmaları `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`.)|  
|[CMFCVisualManagerVS2005::OnUpdateSystemColors](#onupdatesystemcolors)|(Geçersiz kılmaları [CMFCVisualManagerOffice2003::OnUpdateSystemColors](../../mfc/reference/cmfcvisualmanageroffice2003-class.md#onupdatesystemcolors).)|  
  
## <a name="remarks"></a>Açıklamalar  
 CMFCVisualManagerVS2005 sınıfı, benzeyecek şekilde uygulamanızı görsel görünümünü değiştirmek için kullandığınız [!INCLUDE[vsprvsext](../../mfc/reference/includes/vsprvsext_md.md)].  
  
 Bu sınıf üyeleri bu sınıfın üst türetilen sanal işlevler tümü [CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek visual Yöneticisi VS 2005 kullanımı gösterilmiştir. Bu kod parçacığını parçası olan [Masaüstü uyarı demosu örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#9](../../mfc/reference/codesnippet/cpp/cmfcvisualmanagervs2005-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)  
  
 [CMFCVisualManagerVS2005](../../mfc/reference/cmfcvisualmanagervs2005-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxvisualmanagervs2005.h  
  
##  <a name="getdockingtabsborderssize"></a>CMFCVisualManagerVS2005::GetDockingTabsBordersSize  

  
```  
virtual int GetDockingTabsBordersSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getmditabsborderssize"></a>CMFCVisualManagerVS2005::GetMDITabsBordersSize  

  
```  
virtual int GetMDITabsBordersSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpropertygridgroupcolor"></a>CMFCVisualManagerVS2005::GetPropertyGridGroupColor  

  
```  
virtual COLORREF GetPropertyGridGroupColor(CMFCPropertyGridCtrl* pPropList);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pPropList`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gettabframecolors"></a>CMFCVisualManagerVS2005::GetTabFrameColors  

  
```  
virtual void GetTabFrameColors(
    const CMFCBaseTabCtrl* pTabWnd,  
    COLORREF& clrDark,  
    COLORREF& clrBlack,  
    COLORREF& clrHighlight,  
    COLORREF& clrFace,  
    COLORREF& clrDarkShadow,  
    COLORREF& clrLight,  
    CBrush*& pbrFace,  
    CBrush*& pbrBlack);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pTabWnd`  
 [in]`clrDark`  
 [in]`clrBlack`  
 [in]`clrHighlight`  
 [in]`clrFace`  
 [in]`clrDarkShadow`  
 [in]`clrLight`  
 [in]`pbrFace`  
 [in]`pbrBlack`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hasoverlappedautohidebuttons"></a>CMFCVisualManagerVS2005::HasOverlappedAutoHideButtons  

  
```  
virtual BOOL HasOverlappedAutoHideButtons() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawautohidebuttonborder"></a>CMFCVisualManagerVS2005::OnDrawAutoHideButtonBorder  

  
```  
virtual void OnDrawAutoHideButtonBorder(
    CDC* pDC,  
    CRect rectBounds,  
    CRect rectBorderSize,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`rectBounds`  
 [in]`rectBorderSize`  
 [in]`pButton`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawcaptionbutton"></a>CMFCVisualManagerVS2005::OnDrawCaptionButton  

  
```  
virtual void OnDrawCaptionButton(
    CDC* pDC,  
    CMFCCaptionButton* pButton,  
    BOOL bActive,  
    BOOL bHorz,  
    BOOL bMaximized,  
    BOOL bDisabled,  
    int nImageID = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`pButton`  
 [in]`bActive`  
 [in]`bHorz`  
 [in]`bMaximized`  
 [in]`bDisabled`  
 [in]`nImageID`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawpanecaption"></a>CMFCVisualManagerVS2005::OnDrawPaneCaption  

  
```  
virtual COLORREF OnDrawPaneCaption(
    CDC* pDC,  
    CDockablePane* pBar,  
    BOOL bActive,  
    CRect rectCaption,  
    CRect rectButtons);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`pBar`  
 [in]`bActive`  
 [in]`rectCaption`  
 [in]`rectButtons`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawseparator"></a>CMFCVisualManagerVS2005::OnDrawSeparator  

  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    CBasePane* pBar,  
    CRect rect,  
    BOOL bIsHoriz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`pBar`  
 [in]`rect`  
 [in]`bIsHoriz`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawtab"></a>CMFCVisualManagerVS2005::OnDrawTab  

  
```  
virtual void OnDrawTab(
    CDC* pDC,  
    CRect rectTab,  
    int iTab,  
    BOOL bIsActive,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`rectTab`  
 [in]`iTab`  
 [in]`bIsActive`  
 [in]`pTabWnd`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawtoolboxframe"></a>CMFCVisualManagerVS2005::OnDrawToolBoxFrame  

  
```  
virtual void OnDrawToolBoxFrame(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`rect`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onerasetabsarea"></a>CMFCVisualManagerVS2005::OnEraseTabsArea  

  
```  
virtual void OnEraseTabsArea(
    CDC* pDC,  
    CRect rect,  
    const CMFCBaseTabCtrl* pTabWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`rect`  
 [in]`pTabWnd`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onfillautohidebuttonbackground"></a>CMFCVisualManagerVS2005::OnFillAutoHideButtonBackground  

  
```  
virtual void OnFillAutoHideButtonBackground(
    CDC* pDC,  
    CRect rect,  
    CMFCAutoHideButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`rect`  
 [in]`pButton`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onfillhighlightedarea"></a>CMFCVisualManagerVS2005::OnFillHighlightedArea  

  
```  
virtual void OnFillHighlightedArea(
    CDC* pDC,  
    CRect rect,  
    CBrush* pBrush,  
    CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`rect`  
 [in]`pBrush`  
 [in]`pButton`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onfillminiframecaption"></a>CMFCVisualManagerVS2005::OnFillMiniFrameCaption  

  
```  
virtual COLORREF OnFillMiniFrameCaption(
    CDC* pDC,  
    CRect rectCaption,  
    CPaneFrameWnd* pFrameWnd,  
    BOOL bActive);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 [in]`rectCaption`  
 [in]`pFrameWnd`  
 [in]`bActive`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdatesystemcolors"></a>CMFCVisualManagerVS2005::OnUpdateSystemColors  

  
```  
virtual void OnUpdateSystemColors();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP sınıfı](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManagerWindows sınıfı](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManagerOffice2003 Sınıfı](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)