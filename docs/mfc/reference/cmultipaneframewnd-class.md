---
title: "CMultiPaneFrameWnd sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiPaneFrameWnd
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::AddPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::AddRecentPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::AdjustLayout
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::AdjustPaneFrames
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CalcExpectedDockedRect
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CanBeAttached
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CanBeDockedToPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CheckGripperVisibility
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::CloseMiniFrame
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::ConvertToTabbedDocument
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::DockFrame
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::DockPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::DockRecentPaneToMainFrame
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetCaptionText
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetPaneContainerManager
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetFirstVisiblePane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetPaneCount
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::GetVisiblePaneCount
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::InsertPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::LoadState
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnDockToRecentPos
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnKillRollUpTimer
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnPaneRecalcLayout
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnSetRollUpTimer
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::OnShowPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::PaneFromPoint
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::RemoveNonValidPanes
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::RemovePane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::ReplacePane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::SaveState
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::Serialize
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::SetDockState
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::SetLastFocusedPane
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::SetPreDockState
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::StoreRecentDockSiteInfo
- AFXMULTIPANEFRAMEWND/CMultiPaneFrameWnd::StoreRecentTabRelatedInfo
dev_langs:
- C++
helpviewer_keywords:
- CMultiPaneFrameWnd [MFC], AddPane
- CMultiPaneFrameWnd [MFC], AddRecentPane
- CMultiPaneFrameWnd [MFC], AdjustLayout
- CMultiPaneFrameWnd [MFC], AdjustPaneFrames
- CMultiPaneFrameWnd [MFC], CalcExpectedDockedRect
- CMultiPaneFrameWnd [MFC], CanBeAttached
- CMultiPaneFrameWnd [MFC], CanBeDockedToPane
- CMultiPaneFrameWnd [MFC], CheckGripperVisibility
- CMultiPaneFrameWnd [MFC], CloseMiniFrame
- CMultiPaneFrameWnd [MFC], ConvertToTabbedDocument
- CMultiPaneFrameWnd [MFC], DockFrame
- CMultiPaneFrameWnd [MFC], DockPane
- CMultiPaneFrameWnd [MFC], DockRecentPaneToMainFrame
- CMultiPaneFrameWnd [MFC], GetCaptionText
- CMultiPaneFrameWnd [MFC], GetPaneContainerManager
- CMultiPaneFrameWnd [MFC], GetFirstVisiblePane
- CMultiPaneFrameWnd [MFC], GetPane
- CMultiPaneFrameWnd [MFC], GetPaneCount
- CMultiPaneFrameWnd [MFC], GetVisiblePaneCount
- CMultiPaneFrameWnd [MFC], InsertPane
- CMultiPaneFrameWnd [MFC], LoadState
- CMultiPaneFrameWnd [MFC], OnDockToRecentPos
- CMultiPaneFrameWnd [MFC], OnKillRollUpTimer
- CMultiPaneFrameWnd [MFC], OnPaneRecalcLayout
- CMultiPaneFrameWnd [MFC], OnSetRollUpTimer
- CMultiPaneFrameWnd [MFC], OnShowPane
- CMultiPaneFrameWnd [MFC], PaneFromPoint
- CMultiPaneFrameWnd [MFC], RemoveNonValidPanes
- CMultiPaneFrameWnd [MFC], RemovePane
- CMultiPaneFrameWnd [MFC], ReplacePane
- CMultiPaneFrameWnd [MFC], SaveState
- CMultiPaneFrameWnd [MFC], Serialize
- CMultiPaneFrameWnd [MFC], SetDockState
- CMultiPaneFrameWnd [MFC], SetLastFocusedPane
- CMultiPaneFrameWnd [MFC], SetPreDockState
- CMultiPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CMultiPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
ms.assetid: 989a548e-0d70-46b7-a513-8cf740e1be3e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed8ccb584b9bf750e1f17da9ce3e0bf71058abbc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmultipaneframewnd-class"></a>CMultiPaneFrameWnd sınıfı
`CMultiPaneFrameWnd` Sınıfını genişleten [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md). Birden çok bölme destekleyebilir. Denetim çubuğu için tek bir katıştırılmış tanıtıcı yerine `CMultiPaneFrameWnd` içeren bir [CPaneContainerManager sınıfı](../../mfc/reference/cpanecontainermanager-class.md) bir sabitlemek kullanıcının sağlayan nesne `CMultiPaneFrameWnd` diğerine ve dinamik olarak birden fazla kayan oluşturmak, sekmeli Windows.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMultiPaneFrameWnd : public CPaneFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMultiPaneFrameWnd::AddPane](#addpane)|Bir bölme ekler. (Geçersiz kılmaları [CPaneFrameWnd::AddPane](../../mfc/reference/cpaneframewnd-class.md#addpane).)|  
|[CMultiPaneFrameWnd::AddRecentPane](#addrecentpane)||  
|[CMultiPaneFrameWnd::AdjustLayout](#adjustlayout)|Kısa çerçeve pencere düzenini ayarlar. (Geçersiz kılmaları [CPaneFrameWnd::AdjustLayout](../../mfc/reference/cpaneframewnd-class.md#adjustlayout).)|  
|[CMultiPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)|(Geçersiz kılmaları [CPaneFrameWnd::AdjustPaneFrames](../../mfc/reference/cpaneframewnd-class.md#adjustpaneframes).)|  
|[CMultiPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|Yerleşik pencerenin beklenen dikdörtgen hesaplar. (Geçersiz kılmaları [CPaneFrameWnd::CalcExpectedDockedRect](../../mfc/reference/cpaneframewnd-class.md#calcexpecteddockedrect).)|  
|[CMultiPaneFrameWnd::CanBeAttached](#canbeattached)|Geçerli bölmesini başka bir bölme veya çerçeveye pencereye sabitleyebilirsiniz olup olmadığını belirler. (Geçersiz kılmaları [CPaneFrameWnd::CanBeAttached](../../mfc/reference/cpaneframewnd-class.md#canbeattached).)|  
|[CMultiPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|Kısa çerçeve penceresi bir bölmesine yerleştirme olup olmadığını belirler. (Geçersiz kılmaları [CPaneFrameWnd::CanBeDockedToPane](../../mfc/reference/cpaneframewnd-class.md#canbedockedtopane).)|  
|[CMultiPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)|(Geçersiz kılmaları [CPaneFrameWnd::CheckGripperVisibility](../../mfc/reference/cpaneframewnd-class.md#checkgrippervisibility).)|  
|[CMultiPaneFrameWnd::CloseMiniFrame](#closeminiframe)|(Geçersiz kılmaları `CPaneFrameWnd::CloseMiniFrame`.)|  
|[CMultiPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|Bölmesinde bir sekmeli belge dönüştürür. (Geçersiz kılmaları [CPaneFrameWnd::ConvertToTabbedDocument](../../mfc/reference/cpaneframewnd-class.md#converttotabbeddocument).)|  
|[CMultiPaneFrameWnd::DockFrame](#dockframe)||  
|[CMultiPaneFrameWnd::DockPane](#dockpane)|Bölmesinde docks. (Geçersiz kılmaları [CPaneFrameWnd::DockPane](../../mfc/reference/cpaneframewnd-class.md#dockpane).)|  
|[CMultiPaneFrameWnd::DockRecentPaneToMainFrame](#dockrecentpanetomainframe)||  
|[CMultiPaneFrameWnd::GetCaptionText](#getcaptiontext)|Başlık metni döndürür. (Geçersiz kılmaları [CPaneFrameWnd::GetCaptionText](../../mfc/reference/cpaneframewnd-class.md#getcaptiontext).)|  
|[CMultiPaneFrameWnd::GetPaneContainerManager](#getpanecontainermanager)|İç kapsayıcı Yöneticisi nesnesine bir başvuru döndürür.|  
|[CMultiPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|Bir kısa çerçeve penceresinde bulunan ilk görünür bölmesine döndürür. (Geçersiz kılmaları [CPaneFrameWnd::GetFirstVisiblePane](../../mfc/reference/cpaneframewnd-class.md#getfirstvisiblepane).)|  
|[CMultiPaneFrameWnd::GetPane](#getpane)|Kısa çerçeve penceresinde bulunan bir bölme döndürür. (Geçersiz kılmaları [CPaneFrameWnd::GetPane](../../mfc/reference/cpaneframewnd-class.md#getpane).)|  
|[CMultiPaneFrameWnd::GetPaneCount](#getpanecount)|Bir kısa çerçeve penceresinde bulunan bölmeleri sayısını döndürür. (Geçersiz kılmaları [CPaneFrameWnd::GetPaneCount](../../mfc/reference/cpaneframewnd-class.md#getpanecount).)|  
|[CMultiPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|Bir kısa çerçeve penceresinde bulunan görünür bölmeleri sayısını döndürür. (Geçersiz kılmaları [CPaneFrameWnd::GetVisiblePaneCount](../../mfc/reference/cpaneframewnd-class.md#getvisiblepanecount).)|  
|[CMultiPaneFrameWnd::InsertPane](#insertpane)||  
|[CMultiPaneFrameWnd::LoadState](#loadstate)|Kayıt defterinden Bölmesi'nin durumu yükler. (Geçersiz kılmaları [CPaneFrameWnd::LoadState](../../mfc/reference/cpaneframewnd-class.md#loadstate).)|  
|[CMultiPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|Kısa çerçeve penceresi, en son konumundaki docks. (Geçersiz kılmaları [CPaneFrameWnd::OnDockToRecentPos](../../mfc/reference/cpaneframewnd-class.md#ondocktorecentpos).)|  
|[CMultiPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|Toplama süreölçerini durdurur. (Geçersiz kılmaları [CPaneFrameWnd::OnKillRollUpTimer](../../mfc/reference/cpaneframewnd-class.md#onkillrolluptimer).)|  
|[CMultiPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|Bir bölme bir kısa çerçeve penceresi içinde düzenini ayarlar. (Geçersiz kılmaları [CPaneFrameWnd::OnPaneRecalcLayout](../../mfc/reference/cpaneframewnd-class.md#onpanerecalclayout).)|  
|[CMultiPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|Toplama süreölçerini ayarlar. (Geçersiz kılmaları [CPaneFrameWnd::OnSetRollUpTimer](../../mfc/reference/cpaneframewnd-class.md#onsetrolluptimer).)|  
|[CMultiPaneFrameWnd::OnShowPane](#onshowpane)|Kısa çerçeve penceresi bölmesinde gizli ya da görüntülenen çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CPaneFrameWnd::OnShowPane](../../mfc/reference/cpaneframewnd-class.md#onshowpane).)|  
|[CMultiPaneFrameWnd::PaneFromPoint](#panefrompoint)|Bir kullanıcı tarafından sağlanan noktası bir kısa çerçeve penceresi içinde içeriyorsa, bir bölme döndürür. (Geçersiz kılmaları [CPaneFrameWnd::PaneFromPoint](../../mfc/reference/cpaneframewnd-class.md#panefrompoint).)|  
|[CMultiPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|Geçerli olmayan bölmeleri kaldırmak için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CPaneFrameWnd::RemoveNonValidPanes](../../mfc/reference/cpaneframewnd-class.md#removenonvalidpanes).)|  
|[CMultiPaneFrameWnd::RemovePane](#removepane)|Bir bölme kısa çerçeve penceresinden kaldırır. (Geçersiz kılmaları [CPaneFrameWnd::RemovePane](../../mfc/reference/cpaneframewnd-class.md#removepane).)|  
|[CMultiPaneFrameWnd::ReplacePane](#replacepane)|Bir bölme birbiriyle değiştirir. (Geçersiz kılmaları [CPaneFrameWnd::ReplacePane](../../mfc/reference/cpaneframewnd-class.md#replacepane).)|  
|[CMultiPaneFrameWnd::SaveState](#savestate)|Kayıt defterine Bölmesi'nin durumunu kaydeder. (Geçersiz kılmaları [CPaneFrameWnd::SaveState](../../mfc/reference/cpaneframewnd-class.md#savestate).)|  
|[CMultiPaneFrameWnd::Serialize](#serialize)|(Geçersiz kılmaları `CPaneFrameWnd::Serialize`.)|  
|[CMultiPaneFrameWnd::SetDockState](#setdockstate)|Takma durumunu ayarlar. (Geçersiz kılmaları [CPaneFrameWnd::SetDockState](../../mfc/reference/cpaneframewnd-class.md#setdockstate).)|  
|[CMultiPaneFrameWnd::SetLastFocusedPane](#setlastfocusedpane)||  
|[CMultiPaneFrameWnd::SetPreDockState](#setpredockstate)|Predocking durumunu ayarlar. (Geçersiz kılmaları [CPaneFrameWnd::SetPreDockState](../../mfc/reference/cpaneframewnd-class.md#setpredockstate).)|  
|[CMultiPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)|(Geçersiz kılmaları [CPaneFrameWnd::StoreRecentDockSiteInfo](../../mfc/reference/cpaneframewnd-class.md#storerecentdocksiteinfo).)|  
|[CMultiPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)|(Geçersiz kılmaları [CPaneFrameWnd::StoreRecentTabRelatedInfo](../../mfc/reference/cpaneframewnd-class.md#storerecenttabrelatedinfo).)|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıftaki yöntemlerin çoğunu yöntemleri geçersiz kılmak [CPaneFrameWnd sınıfı](../../mfc/reference/cpaneframewnd-class.md) sınıfı.  
  
 Bir bölme kullanıyorsa `AFX_CBRS_AUTO_ROLLUP` stili ve kullanıcı çok bölmesi çerçeve pencere bölmeye docks, kullanıcı bir yerleşik bölmeler stil ayarlarını bağımsız olarak penceresini geri alabilirsiniz.  
  
 Framework otomatik olarak oluşturur bir `CMultiPaneFrameWnd` kullanan bir bölme kullanıcı gezinen zaman nesne `CBRS_FLOAT_MULTI` stili.  
  
 Öğesinden bir sınıf türetme hakkında bilgi için `CPaneFrameWnd` sınıfı ve dinamik olarak oluşturma, [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir işaretçi almak nasıl gösteren bir `CMultiPaneFrameWnd` nesnesi. Bu kod parçacığını parçası olan [bölmesinin boyutunu Ayarla örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#4](../../mfc/reference/codesnippet/cpp/cmultipaneframewnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
 [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxMultiPaneFrameWnd.h  
  
##  <a name="addpane"></a>CMultiPaneFrameWnd::AddPane  

  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWnd`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addrecentpane"></a>CMultiPaneFrameWnd::AddRecentPane  

  
```  
virtual BOOL AddRecentPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="adjustlayout"></a>CMultiPaneFrameWnd::AdjustLayout  

  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="adjustpaneframes"></a>CMultiPaneFrameWnd::AdjustPaneFrames  

  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcexpecteddockedrect"></a>CMultiPaneFrameWnd::CalcExpectedDockedRect  

  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pWndToDock`  
 [in]`ptMouse`  
 [in]`rectResult`  
 [in]`bDrawTab`  
 [in]`ppTargetBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="canbeattached"></a>CMultiPaneFrameWnd::CanBeAttached  

  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="canbedockedtopane"></a>CMultiPaneFrameWnd::CanBeDockedToPane  

  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDockingBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="checkgrippervisibility"></a>CMultiPaneFrameWnd::CheckGripperVisibility  

  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="closeminiframe"></a>CMultiPaneFrameWnd::CloseMiniFrame  

  
```  
virtual void CloseMiniFrame();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="converttotabbeddocument"></a>CMultiPaneFrameWnd::ConvertToTabbedDocument  

  
```  
virtual void ConvertToTabbedDocument();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dockframe"></a>CMultiPaneFrameWnd::DockFrame  

  
```  
virtual BOOL DockFrame(
    CPaneFrameWnd* pDockedFrame,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDockedFrame`  
 [in]`dockMethod`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dockpane"></a>CMultiPaneFrameWnd::DockPane  

  
```  
virtual BOOL DockPane(CDockablePane* pDockedBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDockedBar`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="dockrecentpanetomainframe"></a>CMultiPaneFrameWnd::DockRecentPaneToMainFrame  

  
```  
virtual void DockRecentPaneToMainFrame(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getcaptiontext"></a>CMultiPaneFrameWnd::GetCaptionText  

  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfirstvisiblepane"></a>CMultiPaneFrameWnd::GetFirstVisiblePane  

  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpane"></a>CMultiPaneFrameWnd::GetPane  

  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanecontainermanager"></a>CMultiPaneFrameWnd::GetPaneContainerManager  
 İç kapsayıcı Yöneticisi nesnesine bir başvuru döndürür.  
  
```  
CPaneContainerManager& GetPaneContainerManager();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İç kapsayıcı Yöneticisi nesnesi referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem iç erişmek için kullanılan [CPaneContainerManager sınıfı](../../mfc/reference/cpanecontainermanager-class.md) nesnesi.  
  
##  <a name="getpanecount"></a>CMultiPaneFrameWnd::GetPaneCount  

  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvisiblepanecount"></a>CMultiPaneFrameWnd::GetVisiblePaneCount  

  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="insertpane"></a>CMultiPaneFrameWnd::InsertPane  

  
```  
virtual BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pControlBar`  
 [in]`pTarget`  
 [in]`bAfter`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="loadstate"></a>CMultiPaneFrameWnd::LoadState  

  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszProfileName`  
 [in]`uiID`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondocktorecentpos"></a>CMultiPaneFrameWnd::OnDockToRecentPos  

  
```  
virtual void OnDockToRecentPos();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onkillrolluptimer"></a>CMultiPaneFrameWnd::OnKillRollUpTimer  

  
```  
virtual void OnKillRollUpTimer();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onpanerecalclayout"></a>CMultiPaneFrameWnd::OnPaneRecalcLayout  

  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onsetrolluptimer"></a>CMultiPaneFrameWnd::OnSetRollUpTimer  

  
```  
virtual void OnSetRollUpTimer();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshowpane"></a>CMultiPaneFrameWnd::OnShowPane  

  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`bShow`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="panefrompoint"></a>CMultiPaneFrameWnd::PaneFromPoint  

  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bCheckVisibility);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`point`  
 [in]`nSensitivity`  
 [in]`bCheckVisibility`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removenonvalidpanes"></a>CMultiPaneFrameWnd::RemoveNonValidPanes  

  
```  
virtual void RemoveNonValidPanes();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removepane"></a>CMultiPaneFrameWnd::RemovePane  

  
```  
virtual void RemovePane(
    CBasePane* pBar,  
    BOOL bDestroy = FALSE,  
    BOOL bNoDelayedDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
 [in]`bDestroy`  
 [in]`bNoDelayedDestroy`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="replacepane"></a>CMultiPaneFrameWnd::ReplacePane  

  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBarOrg`  
 [in]`pBarReplaceWith`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="savestate"></a>CMultiPaneFrameWnd::SaveState  

  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszProfileName`  
 [in]`uiID`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="serialize"></a>CMultiPaneFrameWnd::Serialize  

  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`ar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdockstate"></a>CMultiPaneFrameWnd::SetDockState  

  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDockManager`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setlastfocusedpane"></a>CMultiPaneFrameWnd::SetLastFocusedPane  

  
```  
void SetLastFocusedPane(HWND hwnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hwnd`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpredockstate"></a>CMultiPaneFrameWnd::SetPreDockState  

  
```  
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,  
    CBasePane* pBarToDock = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`preDockState`  
 [in]`pBarToDock`  
 [in]`dockMethod`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="storerecentdocksiteinfo"></a>CMultiPaneFrameWnd::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="storerecenttabrelatedinfo"></a>CMultiPaneFrameWnd::StoreRecentTabRelatedInfo  

  
```  
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDockingBar`  
 [in]`pTabbedBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd Sınıfı](../../mfc/reference/cpaneframewnd-class.md)
