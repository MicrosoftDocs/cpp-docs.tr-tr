---
title: CPaneFrameWnd sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd
- AFXPANEFRAMEWND/CPaneFrameWnd::AddPane
- AFXPANEFRAMEWND/CPaneFrameWnd::AddRemovePaneFromGlobalList
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::AdjustPaneFrames
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcBorderSize
- AFXPANEFRAMEWND/CPaneFrameWnd::CalcExpectedDockedRect
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeAttached
- AFXPANEFRAMEWND/CPaneFrameWnd::CanBeDockedToPane
- AFXPANEFRAMEWND/CPaneFrameWnd::CheckGripperVisibility
- AFXPANEFRAMEWND/CPaneFrameWnd::ConvertToTabbedDocument
- AFXPANEFRAMEWND/CPaneFrameWnd::Create
- AFXPANEFRAMEWND/CPaneFrameWnd::CreateEx
- AFXPANEFRAMEWND/CPaneFrameWnd::DockPane
- AFXPANEFRAMEWND/CPaneFrameWnd::FindFloatingPaneByID
- AFXPANEFRAMEWND/CPaneFrameWnd::FrameFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionHeight
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetCaptionText
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::GetDockingMode
- AFXPANEFRAMEWND/CPaneFrameWnd::GetFirstVisiblePane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPane
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::GetParent
- AFXPANEFRAMEWND/CPaneFrameWnd::GetPinState
- AFXPANEFRAMEWND/CPaneFrameWnd::GetRecentFloatingRect
- AFXPANEFRAMEWND/CPaneFrameWnd::GetVisiblePaneCount
- AFXPANEFRAMEWND/CPaneFrameWnd::HitTest
- AFXPANEFRAMEWND/CPaneFrameWnd::IsCaptured
- AFXPANEFRAMEWND/CPaneFrameWnd::IsDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollDown
- AFXPANEFRAMEWND/CPaneFrameWnd::IsRollUp
- AFXPANEFRAMEWND/CPaneFrameWnd::KillDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::LoadState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnBeforeDock
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDockToRecentPos
- AFXPANEFRAMEWND/CPaneFrameWnd::OnKillRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnMovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::OnPaneRecalcLayout
- AFXPANEFRAMEWND/CPaneFrameWnd::OnSetRollUpTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::OnShowPane
- AFXPANEFRAMEWND/CPaneFrameWnd::PaneFromPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::Pin
- AFXPANEFRAMEWND/CPaneFrameWnd::RedrawAll
- AFXPANEFRAMEWND/CPaneFrameWnd::RemoveNonValidPanes
- AFXPANEFRAMEWND/CPaneFrameWnd::RemovePane
- AFXPANEFRAMEWND/CPaneFrameWnd::ReplacePane
- AFXPANEFRAMEWND/CPaneFrameWnd::SaveState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetCaptionButtons
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDelayShow
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingManager
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockingTimer
- AFXPANEFRAMEWND/CPaneFrameWnd::SetDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SetHotPoint
- AFXPANEFRAMEWND/CPaneFrameWnd::SetPreDockState
- AFXPANEFRAMEWND/CPaneFrameWnd::SizeToContent
- AFXPANEFRAMEWND/CPaneFrameWnd::StartTearOff
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentDockSiteInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::StoreRecentTabRelatedInfo
- AFXPANEFRAMEWND/CPaneFrameWnd::OnCheckRollState
- AFXPANEFRAMEWND/CPaneFrameWnd::OnDrawBorder
- AFXPANEFRAMEWND/CPaneFrameWnd::m_bUseSaveBits
dev_langs:
- C++
helpviewer_keywords:
- CPaneFrameWnd [MFC], AddPane
- CPaneFrameWnd [MFC], AddRemovePaneFromGlobalList
- CPaneFrameWnd [MFC], AdjustLayout
- CPaneFrameWnd [MFC], AdjustPaneFrames
- CPaneFrameWnd [MFC], CalcBorderSize
- CPaneFrameWnd [MFC], CalcExpectedDockedRect
- CPaneFrameWnd [MFC], CanBeAttached
- CPaneFrameWnd [MFC], CanBeDockedToPane
- CPaneFrameWnd [MFC], CheckGripperVisibility
- CPaneFrameWnd [MFC], ConvertToTabbedDocument
- CPaneFrameWnd [MFC], Create
- CPaneFrameWnd [MFC], CreateEx
- CPaneFrameWnd [MFC], DockPane
- CPaneFrameWnd [MFC], FindFloatingPaneByID
- CPaneFrameWnd [MFC], FrameFromPoint
- CPaneFrameWnd [MFC], GetCaptionHeight
- CPaneFrameWnd [MFC], GetCaptionRect
- CPaneFrameWnd [MFC], GetCaptionText
- CPaneFrameWnd [MFC], GetDockingManager
- CPaneFrameWnd [MFC], GetDockingMode
- CPaneFrameWnd [MFC], GetFirstVisiblePane
- CPaneFrameWnd [MFC], GetHotPoint
- CPaneFrameWnd [MFC], GetPane
- CPaneFrameWnd [MFC], GetPaneCount
- CPaneFrameWnd [MFC], GetParent
- CPaneFrameWnd [MFC], GetPinState
- CPaneFrameWnd [MFC], GetRecentFloatingRect
- CPaneFrameWnd [MFC], GetVisiblePaneCount
- CPaneFrameWnd [MFC], HitTest
- CPaneFrameWnd [MFC], IsCaptured
- CPaneFrameWnd [MFC], IsDelayShow
- CPaneFrameWnd [MFC], IsRollDown
- CPaneFrameWnd [MFC], IsRollUp
- CPaneFrameWnd [MFC], KillDockingTimer
- CPaneFrameWnd [MFC], LoadState
- CPaneFrameWnd [MFC], OnBeforeDock
- CPaneFrameWnd [MFC], OnDockToRecentPos
- CPaneFrameWnd [MFC], OnKillRollUpTimer
- CPaneFrameWnd [MFC], OnMovePane
- CPaneFrameWnd [MFC], OnPaneRecalcLayout
- CPaneFrameWnd [MFC], OnSetRollUpTimer
- CPaneFrameWnd [MFC], OnShowPane
- CPaneFrameWnd [MFC], PaneFromPoint
- CPaneFrameWnd [MFC], Pin
- CPaneFrameWnd [MFC], RedrawAll
- CPaneFrameWnd [MFC], RemoveNonValidPanes
- CPaneFrameWnd [MFC], RemovePane
- CPaneFrameWnd [MFC], ReplacePane
- CPaneFrameWnd [MFC], SaveState
- CPaneFrameWnd [MFC], SetCaptionButtons
- CPaneFrameWnd [MFC], SetDelayShow
- CPaneFrameWnd [MFC], SetDockingManager
- CPaneFrameWnd [MFC], SetDockingTimer
- CPaneFrameWnd [MFC], SetDockState
- CPaneFrameWnd [MFC], SetHotPoint
- CPaneFrameWnd [MFC], SetPreDockState
- CPaneFrameWnd [MFC], SizeToContent
- CPaneFrameWnd [MFC], StartTearOff
- CPaneFrameWnd [MFC], StoreRecentDockSiteInfo
- CPaneFrameWnd [MFC], StoreRecentTabRelatedInfo
- CPaneFrameWnd [MFC], OnCheckRollState
- CPaneFrameWnd [MFC], OnDrawBorder
- CPaneFrameWnd [MFC], m_bUseSaveBits
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6846f50b0e89193992a42ea50e785009f31e6d19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378793"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd sınıfı
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Bir bölme içeren bir kısa çerçeve penceresi uygular. Bölmesinde penceresinin istemci alanını doldurur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneFrameWnd::AddPane](#addpane)|Bir bölme ekler.|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|Ekler veya bir bölme Genel listeden kaldırır.|  
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|Kısa çerçeve pencere düzenini ayarlar.|  
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||  
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|Kenarlıklar bir kısa çerçeve penceresi boyutunu hesaplar.|  
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|Yerleşik pencerenin beklenen dikdörtgen hesaplayın.|  
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|Başka bir bölme veya çerçeveye penceresine geçerli bölmesini yerleştirilmiş olup olmadığını belirler.|  
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|Kısa çerçeve penceresi bir bölmesine yerleştirilmiş olup olmadığını belirler.|  
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|Bölmesinde bir sekmeli belge dönüştürür.|  
|[CPaneFrameWnd::Create](#create)|Bir kısa çerçeve penceresi oluşturur ve ona ekler `CPaneFrameWnd` nesnesi.|  
|[CPaneFrameWnd::CreateEx](#createex)|Bir kısa çerçeve penceresi oluşturur ve ona ekler `CPaneFrameWnd` nesnesi.|  
|[CPaneFrameWnd::DockPane](#dockpane)|Bölmesinde docks.|  
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|Belirtilen denetim kimliği bölmesiyle kayan bölmeleri genel listede bulur.|  
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|Bir kullanıcı tarafından sağlanan noktası içeren kısa çerçeve penceresi bulur.|  
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|Kısa çerçeve penceresi yazısı yüksekliğini döndürür.|  
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|Bir kısa çerçeve penceresi başlığı sınırlayıcı dikdörtgenini hesaplar.|  
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|Başlık metni döndürür.|  
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||  
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|Yerleştirme modunu döndürür.|  
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|Bir kısa çerçeve penceresinde bulunan ilk görünür bölmesine döndürür.|  
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||  
|[CPaneFrameWnd::GetPane](#getpane)|Kısa çerçeve penceresinde bulunan bir bölme döndürür.|  
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|Bir kısa çerçeve penceresinde bulunan bölmeleri sayısını döndürür.|  
|[CPaneFrameWnd::GetParent](#getparent)||  
|[CPaneFrameWnd::GetPinState](#getpinstate)||  
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||  
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|Bir kısa çerçeve penceresinde bulunan görünür bölmeleri sayısını döndürür.|  
|[CPaneFrameWnd::HitTest](#hittest)|Belirli bir anda bir kısa çerçeve penceresi hangi kısmının olduğunu belirler.|  
|[CPaneFrameWnd::IsCaptured](#iscaptured)||  
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||  
|[CPaneFrameWnd::IsRollDown](#isrolldown)|Bir kısa çerçeve penceresi aşağı alındı olup olmadığını belirler.|  
|[CPaneFrameWnd::IsRollUp](#isrollup)|Bir kısa çerçeve penceresi toplanan olup olmadığını belirler.|  
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|Yerleştirme Zamanlayıcı durdurur.|  
|[CPaneFrameWnd::LoadState](#loadstate)|Kayıt defterinden Bölmesi'nin durumu yükler.|  
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|Yerleştirme mümkün olup olmadığını belirler.|  
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|Kısa çerçeve penceresi, en son konumundaki docks.|  
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|Toplama süreölçerini durdurur.|  
|[CPaneFrameWnd::OnMovePane](#onmovepane)|Kısa çerçeve penceresi tarafından belirtilen kayma taşır.|  
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|Kapsanan bölmesinde düzenini ayarlar.|  
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|Toplama süreölçerini ayarlar.|  
|[CPaneFrameWnd::OnShowPane](#onshowpane)|Kısa çerçeve penceresi bölmesinde gizli ya da görüntülenen çerçevesi tarafından çağrılır.|  
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|Bir kullanıcı tarafından sağlanan noktası bir kısa çerçeve penceresi içinde içeriyorsa, bir bölme döndürür.|  
|[CPaneFrameWnd::Pin](#pin)||  
|`CPaneFrameWnd::PreTranslateMessage`|Sınıfı tarafından kullanılan [CWinApp](../../mfc/reference/cwinapp-class.md) için gönderilen önce pencere iletileri çevirmek için [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır.|  
|[CPaneFrameWnd::RedrawAll](#redrawall)|Tüm kısa çerçeve pencereleri yeniden çizer.|  
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|Geçerli olmayan bölmeleri kaldırmak için çerçevesi tarafından çağrılır.|  
|[CPaneFrameWnd::RemovePane](#removepane)|Bir bölme kısa çerçeve penceresinden kaldırır.|  
|[CPaneFrameWnd::ReplacePane](#replacepane)|Bir bölme birbiriyle değiştirir.|  
|[CPaneFrameWnd::SaveState](#savestate)|Kayıt defterine Bölmesi'nin durumunu kaydeder.|  
|`CPaneFrameWnd::Serialize`|Okur veya bir arşiv değiştirilmesine veya bu nesneyi yazar.|  
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|Ayarlar düğmeleri resim yazısı.|  
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||  
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||  
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|Yerleştirme Zamanlayıcı ayarlar.|  
|[CPaneFrameWnd::SetDockState](#setdockstate)|Takma durumunu ayarlar.|  
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||  
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|Predocking durumunu ayarlamaya çerçevesi tarafından çağrılır.|  
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|Böylece bir kapsanan bölmesine boyutu eşdeğer bir kısa çerçeve pencere boyutunu ayarlar.|  
|[CPaneFrameWnd::StartTearOff](#starttearoff)|Tears menü kapalı.|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|Bir kısa çerçeve penceresi yukarı veya aşağı alınması olup olmadığını belirler.|  
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|Bir kısa çerçeve penceresi Kenarlıklar çizer.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|Pencere sınıfı ile kaydetmek belirtir `CS_SAVEBITS` sınıf stili.|  
  
## <a name="remarks"></a>Açıklamalar  
 Framework otomatik olarak oluşturur bir `CPaneFrameWnd` bir bölme bir kayan durumuna dayalı bir durumdan geçildiğinde nesne.  
  
 Bir kısa çerçeve penceresi birlikte içeriğiyle sürüklenebilir görünür (hemen yerleştirme) ya da sürükle dikdörtgene (standart yerleştirme) kullanarak. Mini çerçeve kapsayıcı bölmenin yerleştirme modu mini çerçeve davranışı sürükleyerek kullanıcının belirler. Daha fazla bilgi için bkz: [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
 Bir kısa çerçeve penceresi düğmeleri resim yazısı kapsanan bölmesinde stili göre görüntüler. Bölme kapatılabilir, ( [CBasePane::CanBeClosed](../../mfc/reference/cbasepane-class.md#canbeclosed)), Kapat düğmesini görüntüler. Bölmesinde varsa `AFX_CBRS_AUTO_ROLLUP` stili, PIN görüntüler.  
  
 Öğesinden bir sınıf türetirseniz `CPaneFrameWnd`, oluşturmak nasıl framework bildirmeniz gerekir. Ya da geçersiz kılarak sınıfı oluşturmak [CPane::CreateDefaultMiniframe](../../mfc/reference/cpane-class.md#createdefaultminiframe), veya `CPane::m_pMiniFrameRTC` sınıfınız için çalışma zamanı sınıf bilgileri onun işaret için üye.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPaneFrameWnd`   
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxPaneFrameWnd.h  
  
##  <a name="addpane"></a>  CPaneFrameWnd::AddPane  
 Bir bölme ekler.  
  
```  
virtual void AddPane(CBasePane* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWnd`  
 Eklemek için bölme.  
  
##  <a name="addremovepanefromgloballist"></a>  CPaneFrameWnd::AddRemovePaneFromGlobalList  
 Ekler veya bir bölme Genel listeden kaldırır.  
  
```  
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,  
    BOOL bAdd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWnd`  
 Eklemek veya kaldırmak için bölme.  
  
 [in] `bAdd`  
 Sıfır olmayan bölmesi ekleyin. 0 ise bölmesini kaldırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="adjustlayout"></a>  CPaneFrameWnd::AdjustLayout  
 Kısa çerçeve pencere düzenini ayarlar.  
  
```  
virtual void AdjustLayout();
```  
  
##  <a name="adjustpaneframes"></a>  CPaneFrameWnd::AdjustPaneFrames  

  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcbordersize"></a>  CPaneFrameWnd::CalcBorderSize  
 Kenarlıklar miniframe penceresi boyutunu hesaplar.  
  
```  
virtual void CalcBorderSize(CRect& rectBorderSize) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `rectBorderSize`  
 Miniframe penceresinin kenarlığının piksel cinsinden boyutu içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir miniframe pencere kenarlık boyutunu hesaplamak için çerçevesi tarafından çağrılır. Araç çubuğu miniframe penceresi içerip içermediğini veya döndürülen boyutu bağlıdır [CDockablePane](../../mfc/reference/cdockablepane-class.md).  
  
##  <a name="calcexpecteddockedrect"></a>  CPaneFrameWnd::CalcExpectedDockedRect  
 Yerleşik pencerenin beklenen dikdörtgen hesaplayın.  
  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWndToDock`  
 Pencere sabitlemek için bir işaretçi.  
  
 [in] `ptMouse`  
 Fare konumu.  
  
 [out] `rectResult`  
 Hesaplanan dikdörtgen.  
  
 [out] `bDrawTab`  
 Varsa `TRUE`, sekme çizin. Varsa `FALSE`, sekme çekmek değil.  
  
 [out] `ppTargetBar`  
 Hedef bölmesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir kullanıcı tarafından belirtilen noktasına penceresi Sürüklediyseniz, bir pencere kaplar dikdörtgen hesaplar `ptMouse` ve var. yerleştirildi.  
  
##  <a name="canbeattached"></a>  CPaneFrameWnd::CanBeAttached  
 Başka bir bölme veya çerçeveye penceresine geçerli bölmesini yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde başka bir bölme veya çerçeveye penceresine; yerleşik, Aksi takdirde `FALSE`.  
  
##  <a name="canbedockedtopane"></a>  CPaneFrameWnd::CanBeDockedToPane  
 Kısa çerçeve penceresi bir bölmesine yerleştirilmiş olup olmadığını belirler.  
  
```  
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDockingBar`  
 Bir bölme.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısa çerçeve yerleştirilmiş, sıfır olmayan `pDockingBar`; Aksi halde 0.  
  
##  <a name="checkgrippervisibility"></a>  CPaneFrameWnd::CheckGripperVisibility  

  
```  
virtual void CheckGripperVisibility();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="converttotabbeddocument"></a>  CPaneFrameWnd::ConvertToTabbedDocument  
 Bölmesinde bir sekmeli belge dönüştürür.  
  
```  
virtual void ConvertToTabbedDocument();
```  
  
##  <a name="create"></a>  CPaneFrameWnd::Create  
 Miniframe pencere oluşturur ve ona ekler [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) nesnesi.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszWindowName`  
 Miniframe penceresinde görüntülenecek metni belirtir.  
  
 [in] `dwStyle`  
 Pencere stili belirtir. Daha fazla bilgi için bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `rect`  
 İlk boyutunu ve konumunu miniframe penceresinin belirtir.  
  
 [in] [out] `pParentWnd`  
 Miniframe penceresinin üst çerçeve belirtir. Bu değer olmamalıdır `NULL`.  
  
 [in] [out] `pContext`  
 Kullanıcı tanımlı içerik belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` pencerenin başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir miniframe penceresi iki adımda oluşturulur. İlk olarak, framework oluşturur bir `CPaneFrameWnd` nesnesi. İkinci olarak, çağıran `Create` Windows miniframe penceresi oluşturmak ve ona eklemek için `CPaneFrameWnd` nesnesi.  
  
##  <a name="createex"></a>  CPaneFrameWnd::CreateEx  
 Miniframe pencere oluşturur ve ona ekler [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `dwStyleEx`  
 Genişletilmiş pencere stilini belirtir. Daha fazla bilgi için bkz: [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)  
  
 [in] `lpszWindowName`  
 Miniframe penceresinde görüntülenecek metni belirtir.  
  
 [in] `dwStyle`  
 Pencere stili belirtir. Daha fazla bilgi için bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `rect`  
 İlk boyutunu ve konumunu miniframe penceresinin belirtir.  
  
 [in] [out] `pParentWnd`  
 Miniframe penceresinin üst çerçeve belirtir. Bu değer olmamalıdır `NULL`.  
  
 [in] [out] `pContext`  
 Kullanıcı tanımlı içerik belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` pencerenin başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir miniframe penceresi iki adımda oluşturulur. İlk olarak, framework oluşturur bir `CPaneFrameWnd` nesnesi. İkinci olarak, çağıran `Create` Windows miniframe penceresi oluşturmak ve ona eklemek için `CPaneFrameWnd` nesnesi.  
  
##  <a name="dockpane"></a>  CPaneFrameWnd::DockPane  
 Bölmesinde docks.  
  
```  
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `bWasDocked`  
 `TRUE` bölmesinde zaten sabitlenmiş; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa `CDockablePane` bölmesi yuvalanmış olduğunu; tersi durumda `NULL`.  
  
##  <a name="findfloatingpanebyid"></a>  CPaneFrameWnd::FindFloatingPaneByID  
 Belirtilen denetim kimliği bölmesiyle kayan bölmeleri genel listede bulur.  
  
```  
static CBasePane* FindFloatingPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nID`  
 Bulunacak bölmesinde denetim Kimliğini temsil eder.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen denetim kimliği bölmesiyle; Aksi takdirde, `NULL`, hiçbir bölmesinde belirtilen denetim kimliği.  
  
##  <a name="framefrompoint"></a>  CPaneFrameWnd::FrameFromPoint  
 Belirtilen noktası içeren bir kısa çerçeve pencere bulur.  
  
```  
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,  
    int nSensitivity,  
    CPaneFrameWnd* pFrameToExclude = NULL,  
    BOOL bFloatMultiOnly = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pt`  
 Ekran koordinatları noktası.  
  
 [in] `nSensitivity`  
 Kısa çerçeve penceresi arama alanı bu boyutunu artırabilirsiniz. Belirtilen noktasını artan alanında düşerse bir kısa çerçeve pencere arama ölçütleri karşılar.  
  
 [in] `pFrameToExclude`  
 Arama dışlamak için bir kısa çerçeve penceresi belirtir.  
  
 [in] `bFloatMultiOnly`  
 Varsa `TRUE`, yalnızca sahip kısa çerçeve pencereleri arama `CBRS_FLOAT_MULTI` stili. Varsa `FALSE`, tüm kısa çerçeve pencereleri arayın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi içeren bir kısa çerçeve pencere `pt`; Aksi halde `NULL`.  
  
##  <a name="getcaptionheight"></a>  CPaneFrameWnd::GetCaptionHeight  
 Kısa çerçeve penceresi yazısı yüksekliğini döndürür.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısa çerçeve penceresi piksel cinsinden yüksekliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kısa çerçeve penceresi yüksekliğini belirlemek için bu yöntemi çağırın. Varsayılan olarak, yükseklik ayarlamak `SM_CYSMCAPTION`. Daha fazla bilgi için bkz: [GetSystemMetrics işlevi](http://msdn.microsoft.com/library/windows/desktop/ms724385).  
  
##  <a name="getcaptionrect"></a>  CPaneFrameWnd::GetCaptionRect  
 Bir kısa çerçeve penceresi başlığı sınırlayıcı dikdörtgenini hesaplar.  
  
```  
virtual void GetCaptionRect(CRect& rectCaption) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `rectCaption`  
 Ekran koordinatları kısa çerçeve pencere başlığında, konumu ve boyutu içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir kısa çerçeve penceresi başlığı sınırlayıcı dikdörtgenini hesaplamak için çerçevesi tarafından çağrılır.  
  
##  <a name="getcaptiontext"></a>  CPaneFrameWnd::GetCaptionText  
 Başlık metni döndürür.  
  
```  
virtual CString GetCaptionText();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısa çerçeve penceresi başlık metni.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlık metni görüntülediğinde, bu yöntem çerçevesi tarafından çağrılır.  
  
##  <a name="getdockingmanager"></a>  CPaneFrameWnd::GetDockingManager  

  
```  
CDockingManager* GetDockingManager() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdockingmode"></a>  CPaneFrameWnd::GetDockingMode  
 Yerleştirme modunu döndürür.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerleştirme modu. Aşağıdaki değerlerden biri:  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
##  <a name="getfirstvisiblepane"></a>  CPaneFrameWnd::GetFirstVisiblePane  
 Bir kısa çerçeve penceresinde bulunan ilk görünür bölmesine döndürür.  
  
```  
virtual CWnd* GetFirstVisiblePane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısa çerçeve penceresi ilk bölmesinde veya `NULL` kısa çerçeve penceresi yok bölmeleri içeriyorsa.  
  
##  <a name="gethotpoint"></a>  CPaneFrameWnd::GetHotPoint  

  
```  
CPoint GetHotPoint() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpane"></a>  CPaneFrameWnd::GetPane  
 Kısa çerçeve penceresinde bulunan bir bölme döndürür.  
  
```  
virtual CWnd* GetPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Mini çerçevenin içerdiği bölmesinde veya `NULL` kısa çerçeve penceresi yok bölmeleri içeriyorsa.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanecount"></a>  CPaneFrameWnd::GetPaneCount  
 Bir kısa çerçeve penceresinde bulunan bölmeleri sayısını döndürür.  
  
```  
virtual int GetPaneCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kısa çerçeve penceresi bölmelerinde sayısı. Bu değer sıfır olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getparent"></a>  CPaneFrameWnd::GetParent  

  
```  
CWnd* GetParent();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpinstate"></a>  CPaneFrameWnd::GetPinState  

  
```  
BOOL GetPinState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrecentfloatingrect"></a>  CPaneFrameWnd::GetRecentFloatingRect  

  
```  
CRect GetRecentFloatingRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getvisiblepanecount"></a>  CPaneFrameWnd::GetVisiblePaneCount  
 Bir kısa çerçeve penceresinde bulunan görünür bölmeleri sayısını döndürür.  
  
```  
virtual int GetVisiblePaneCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünür bölmeleri sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="hittest"></a>  CPaneFrameWnd::HitTest  
 Belirli bir anda bir kısa çerçeve penceresi hangi kısmının olduğunu belirler.  
  
```  
virtual LRESULT HitTest(
    CPoint point,  
    BOOL bDetectCaption);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `point`  
 Test noktası.  
  
 [in] `bDetectCaption`  
 Varsa `TRUE`, resim yazısını karşı noktası denetleyin. Varsa `FALSE`, resim yazısını yoksay.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden biri:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|`HTNOWHERE`|Kısa çerçeve penceresi dışında noktasıdır.|  
|`HTCLIENT`|İstemci alanında noktasıdır.|  
|`HTCAPTION`|Resim yazısını noktasıdır.|  
|`HTTOP`|En üstte noktasıdır.|  
|`HTTOPLEFT`|Sol üst kısmında noktasıdır.|  
|`HTTOPRIGHT`|Sağ üst kısmında noktasıdır.|  
|`HTLEFT`|Solda noktasıdır.|  
|`HTRIGHT`|Sağ taraftaki noktasıdır.|  
|`HTBOTTOM`|Pencerenin alt noktasıdır.|  
|`HTBOTTOMLEFT`|Sol alt kısmındaki noktasıdır.|  
|`HTBOTTOMRIGHT`|Pencerenin sağ alt noktasıdır.|  
  
##  <a name="iscaptured"></a>  CPaneFrameWnd::IsCaptured  

  
```  
BOOL IsCaptured() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isdelayshow"></a>  CPaneFrameWnd::IsDelayShow  

  
```  
BOOL IsDelayShow() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isrolldown"></a>  CPaneFrameWnd::IsRollDown  
 Bir kısa çerçeve penceresi aşağı alındı olup olmadığını belirler.  
  
```  
virtual BOOL IsRollDown() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` kısa çerçeve penceresi aşağı geri alınması gerekir Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir kısa çerçeve penceresi aşağı alındı olup olmadığını belirlemek için çerçevesi tarafından çağrılır. Sahip en az bir bölmesinde içeriyorsa toplaması/rolldown özelliği için bir kısa çerçeve penceresi etkinleştirilmişse `AFX_CBRS_AUTO_ROLLUP` bayrağı. Bir bölme oluşturduğunuzda bu bayrağı ayarlanır. Daha fazla bilgi için bkz: [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 Varsayılan olarak, framework fare işaretçisini penceresini aşağı geri alınması olup olmadığını belirlemek için kısa çerçeve penceresi sınırlayıcı dikdörtgenini içinde olup olmadığını denetler. Bir türetilmiş sınıfta bu davranışı geçersiz kılabilirsiniz.  
  
##  <a name="isrollup"></a>  CPaneFrameWnd::IsRollUp  
 Bir kısa çerçeve penceresi toplanan olup olmadığını belirler.  
  
```  
virtual BOOL IsRollUp() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` kısa çerçeve penceresi döküm sunulur Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir kısa çerçeve penceresi toplanan olup olmadığını belirlemek için çerçevesi tarafından çağrılır. Sahip en az bir bölmesinde içeriyorsa toplaması/rolldown özelliği için bir kısa çerçeve penceresi etkinleştirilmişse `AFX_CBRS_AUTO_ROLLUP` bayrağı. Bir bölme oluşturduğunuzda bu bayrağı ayarlanır. Daha fazla bilgi için bkz: [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).  
  
 Varsayılan olarak, framework fare işaretçisini penceresi geri alınması olup olmadığını belirlemek için kısa çerçeve penceresi sınırlayıcı dikdörtgenini içinde olup olmadığını denetler. Bir türetilmiş sınıfta bu davranışı geçersiz kılabilirsiniz.  
  
##  <a name="killdockingtimer"></a>  CPaneFrameWnd::KillDockingTimer  
 Yerleştirme Zamanlayıcı durdurur.  
  
```  
void KillDockingTimer();
```  
  
##  <a name="loadstate"></a>  CPaneFrameWnd::LoadState  
 Kayıt defterinden Bölmesi'nin durumu yükler.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszProfileName`  
 Profil adı.  
  
 [in] `uiID`  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde durumu başarıyla yüklendiyse; Aksi takdirde `FALSE`.  
  
##  <a name="m_busesavebits"></a>  CPaneFrameWnd::m_bUseSaveBits  
 Sahip pencere sınıfı kaydı belirtir `CS_SAVEBITS` sınıf stili.  
  
```  
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu statik üye kümesine `TRUE` sahip kısa çerçeve penceresi sınıfını `CS_SAVEBITS` stili. Bu, bir kullanıcının kısa çerçeve penceresi sürüklendiğinde titremeyi azaltmaya yardımcı.  
  
##  <a name="onbeforedock"></a>  CPaneFrameWnd::OnBeforeDock  
 Yerleştirme mümkün olup olmadığını belirler.  
  
```  
virtual BOOL OnBeforeDock();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yerleştirme mümkünse; Aksi takdirde `FALSE`.  
  
##  <a name="oncheckrollstate"></a>  CPaneFrameWnd::OnCheckRollState  
 Bir kısa çerçeve penceresi yukarı veya aşağı alınması olup olmadığını belirler.  
  
```  
virtual void OnCheckRollState();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir kısa çerçeve penceresi yukarı veya aşağı alınması olup olmadığını belirlemek için çerçevesi tarafından çağrılır.  
  
 Varsayılan olarak, framework çağırması [CPaneFrameWnd::IsRollUp](#isrollup) ve [CPaneFrameWnd::IsRollDown](#isrolldown) ve yalnızca uzatır veya kısa çerçeve penceresi geri yükler. Farklı bir görsel efekti kullanmak için bir türetilmiş sınıfta bu yöntemin üzerine yazabilir.  
  
##  <a name="ondocktorecentpos"></a>  CPaneFrameWnd::OnDockToRecentPos  
 Kısa çerçeve penceresi, en son konumundaki docks.  
  
```  
virtual void OnDockToRecentPos();
```  
  
##  <a name="ondrawborder"></a>  CPaneFrameWnd::OnDrawBorder  
 Bir kısa çerçeve penceresi Kenarlıklar çizer.  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Kenarlık çizmek için kullanılan cihaz bağlamı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem kısa çerçeve penceresi Kenarlıkları çizmek için çerçevesi tarafından çağrılır.  
  
##  <a name="onkillrolluptimer"></a>  CPaneFrameWnd::OnKillRollUpTimer  
 Toplama süreölçerini durdurur.  
  
```  
virtual void OnKillRollUpTimer();
```  
  
##  <a name="onmovepane"></a>  CPaneFrameWnd::OnMovePane  
 Kısa çerçeve penceresi tarafından belirtilen kayma taşır.  
  
```  
virtual void OnMovePane(
    CPane* pBar,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pBar`  
 Bir bölme (göz ardı) için bir işaretçi.  
  
 [in] `ptOffset`  
 Bölmesinde taşımak üzere uzaklığı.  
  
##  <a name="onpanerecalclayout"></a>  CPaneFrameWnd::OnPaneRecalcLayout  
 Bir bölme bir kısa çerçeve penceresi içinde düzenini ayarlar.  
  
```  
virtual void OnPaneRecalcLayout();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Framework bölmesindeki Mini çerçeve penceresi içinde düzenini ayarlamanız gerekir, bu yöntemi çağırır.  
  
 Varsayılan olarak, kısa çerçeve penceresi tam istemci alanını kaplamak için bölmesinde konumlandırıldı.  
  
##  <a name="onsetrolluptimer"></a>  CPaneFrameWnd::OnSetRollUpTimer  
 Toplama süreölçerini ayarlar.  
  
```  
virtual void OnSetRollUpTimer();
```  
  
##  <a name="onshowpane"></a>  CPaneFrameWnd::OnShowPane  
 Kısa çerçeve penceresi bölmesinde gizli ya da görüntülenen çerçevesi tarafından çağrılır.  
  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pBar`  
 Yüklenmekte olan bölmesinde gösterilen veya gizli.  
  
 [in] `bShow`  
 `TRUE` bölmesinde gösterilir `FALSE` bölmesinde gizli değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Kısa çerçeve penceresi bölmesinde gösterileceğini veya gizleneceğini çerçevesi tarafından çağrılır. Varsayılan uygulama hiçbir şey yapmaz.  
  
##  <a name="pin"></a>  CPaneFrameWnd::Pin  

  
```  
void Pin(BOOL bPin = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bPin`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="panefrompoint"></a>  CPaneFrameWnd::PaneFromPoint  
 Bir kullanıcı tarafından sağlanan noktası bir kısa çerçeve penceresi içinde içeriyorsa, bir bölme döndürür.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    BOOL bCheckVisibility);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `point`  
 Noktayı, kullanıcı, ekran koordinatları olarak tıklattınız.  
  
 [in] `nSensitivity`  
 Bu parametre kullanılmaz.  
  
 [in] `bCheckVisibility`  
 `TRUE` Yalnızca görünür bölmeleri döndürülmesi gerektiğini belirtmek için; Aksi takdirde `FALSE`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı tıklandığında, bölme veya `NULL` hiçbir bölmesinde o konumda varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen noktasını içeren bir bölme elde etmek için bu yöntemi çağırın.  
  
##  <a name="redrawall"></a>  CPaneFrameWnd::RedrawAll  
 Tüm kısa çerçeve pencereleri yeniden çizer.  
  
```  
static void RedrawAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem çağırarak tüm kısa çerçeve pencereleri güncelleştirmeleri [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) her penceresi.  
  
##  <a name="removenonvalidpanes"></a>  CPaneFrameWnd::RemoveNonValidPanes  
 Geçerli olmayan bölmeleri kaldırmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void RemoveNonValidPanes();
```  
  
##  <a name="removepane"></a>  CPaneFrameWnd::RemovePane  
 Bir bölme kısa çerçeve penceresinden kaldırır.  
  
```  
virtual void RemovePane(
    CBasePane* pWnd,  
    BOOL bDestroy = FALSE,  
    BOOL bNoDelayedDestroy = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWnd`  
 Bir işaretçi bölmesine kaldırmak için.  
  
 [in] `bDestroy`  
 Kısa çerçeve penceresi ne olacağını belirtir. Varsa `bDestroy` olan `TRUE`, hemen Mini çerçeve penceresi bu yöntemi yok eder. Eğer öyleyse `FALSE`, bu yöntem, belirli bir gecikmeden sonra kısa çerçeve penceresi yok eder.  
  
 [in] `bNoDelayedDestroy`  
 Varsa `TRUE`, Gecikmeli yok etme devre dışıdır. Varsa `FALSE`, Gecikmeli yok etme etkindir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework hemen veya belirli bir gecikmeden sonra kısa çerçeve pencerelerini yok edebilir. Kısa çerçeve pencerelerini yok etme gecikme istiyorsanız, geçirmek `FALSE` içinde `bNoDelayedDestroy` parametresi. Gecikmeli yok etme oluşur framework işlerken `AFX_WM_CHECKEMPTYMINIFRAME` ileti.  
  
##  <a name="replacepane"></a>  CPaneFrameWnd::ReplacePane  
 Bir bölme birbiriyle değiştirir.  
  
```  
virtual void ReplacePane(
    CBasePane* pBarOrg,  
    CBasePane* pBarReplaceWith);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pBarOrg`  
 Özgün bölmesi için bir işaretçi.  
  
 [in] `pBarReplaceWith`  
 Bir işaretçi bölmesine özgün bölmesinde yerini alır.  
  
##  <a name="savestate"></a>  CPaneFrameWnd::SaveState  
 Kayıt defterine Bölmesi'nin durumunu kaydeder.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszProfileName`  
 Profil adı.  
  
 [in] `uiID`  
 Bölmesinde kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bölmesinde durumu başarıyla kaydedildi Aksi takdirde `FALSE`.  
  
##  <a name="setcaptionbuttons"></a>  CPaneFrameWnd::SetCaptionButtons  
 Ayarlar düğmeleri resim yazısı.  
  
```  
virtual void SetCaptionButtons(DWORD dwButtons);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `dwButtons`  
 Aşağıdaki değerlerin Bitsel veya birleşimi:  
  
- `AFX_CAPTION_BTN_CLOSE`  
  
- `AFX_CAPTION_BTN_PIN`  
  
- `AFX_CAPTION_BTN_MENU`  
  
- `AFX_CAPTION_BTN_CUSTOMIZE`  
  
##  <a name="setdelayshow"></a>  CPaneFrameWnd::SetDelayShow  

  
```  
void SetDelayShow(BOOL bDelayShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bDelayShow`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdockingmanager"></a>  CPaneFrameWnd::SetDockingManager  

  
```  
void SetDockingManager(CDockingManager* pManager);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pManager`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdockingtimer"></a>  CPaneFrameWnd::SetDockingTimer  
 Yerleştirme Zamanlayıcı ayarlar.  
  
```  
void SetDockingTimer(UINT nTimeOut);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nTimeOut`  
 Zaman aşımı değerini milisaniye cinsinden.  
  
##  <a name="setdockstate"></a>  CPaneFrameWnd::SetDockState  
 Takma durumunu ayarlar.  
  
```  
virtual void SetDockState(CDockingManager* pDockManager);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDockManager`  
 Yerleştirme Yöneticisi için bir işaretçi.  
  
##  <a name="sethotpoint"></a>  CPaneFrameWnd::SetHotPoint  

  
```  
void SetHotPoint(CPoint& ptNew);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `ptNew`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpredockstate"></a>  CPaneFrameWnd::SetPreDockState  
 Predocking durumunu ayarlamaya çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,  
    CBasePane* pBarToDock = NULL,  
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `preDockState`  
 Olası değerler:  
  
- `PDS_NOTHING`,  
  
- `PDS_DOCK_REGULAR`,  
  
- `PDS_DOCK_TO_TAB`  
  
 [in] `pBarToDock`  
 Yerleştirme için bölmesinde bir işaretçi.  
  
 [in] `dockMethod`  
 Yerleştirme yöntemi. (Bu parametre yoksayılır.)  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` kısa çerçeve penceresi kilitli ise; `FALSE` yerleştirilmiş olup olmadığını.  
  
##  <a name="sizetocontent"></a>  CPaneFrameWnd::SizeToContent  
 Böylece bir kapsanan bölmesine eşdeğer bir kısa çerçeve pencere boyutunu ayarlar.  
  
```  
virtual void SizeToContent();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kapsanan bölmesinin boyutunu kısa çerçeve pencere boyutunu ayarlamak için bu yöntemi çağırın.  
  
##  <a name="starttearoff"></a>  CPaneFrameWnd::StartTearOff  
 Tears menü kapalı.  
  
```  
BOOL StartTearOff(CMFCPopu* pMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pMenu`  
 Bir menüye işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa; Aksi takdirde `FALSE`.  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneFrameWnd::StoreRecentDockSiteInfo  

  
```  
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="storerecenttabrelatedinfo"></a>  CPaneFrameWnd::StoreRecentTabRelatedInfo  

  
```  
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDockingBar`  
 [in] `pTabbedBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
