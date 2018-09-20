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
ms.openlocfilehash: 34ac2ddb08b485a56274f6067871c5bbd5893f94
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434823"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd sınıfı

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

Bir bölme içeren bir mini çerçeve uygular. Bölme pencerenin istemci alanını doldurur.

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
|[CPaneFrameWnd::AdjustLayout](#adjustlayout)|Mini çerçeve düzenini ayarlar.|
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|Mini çerçeve pencere kenarlıklarını boyutunu hesaplar.|
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|Yerleşik pencere beklenen dikdörtgen hesaplayın.|
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|Başka bir bölüm ya da çerçeve penceresi geçerli bölmesini yerleştirilmiş olup olmadığını belirler.|
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|Bir bölmesine Mini çerçeve penceresinin yerleştirilmiş olup olmadığını belirler.|
|[CPaneFrameWnd::CheckGripperVisibility](#checkgrippervisibility)||
|[CPaneFrameWnd::ConvertToTabbedDocument](#converttotabbeddocument)|Bölmesinde sekmeli belgeye dönüştürür.|
|[CPaneFrameWnd::Create](#create)|Bir mini çerçeve penceresi oluşturur ve ona ekler `CPaneFrameWnd` nesne.|
|[CPaneFrameWnd::CreateEx](#createex)|Bir mini çerçeve penceresi oluşturur ve ona ekler `CPaneFrameWnd` nesne.|
|[CPaneFrameWnd::DockPane](#dockpane)|Bölmesinde docks.|
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|Belirtilen denetim kimliği içeren bölme kayan bölmeleri genel listesinde bulur.|
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|Kullanıcı tarafından sağlanan bir noktayı içeren Mini çerçeve bulur.|
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|Mini çerçeve pencere başlığı yüksekliğini döndürür.|
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|Bir mini çerçeve pencere başlığı sınırlayıcı dikdörtgenini hesaplar.|
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|Açıklamalı alt yazı metni döndürür.|
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|Yerleştirme modunu döndürür.|
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|Bir mini çerçeve penceresinde yer alan ilk görünür bölmesine döndürür.|
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||
|[CPaneFrameWnd::GetPane](#getpane)|Mini çerçeve penceresinde yer alan bir bölme döndürür.|
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|Bir mini çerçeve penceresinde bulunan bölmeleri sayısını döndürür.|
|[CPaneFrameWnd::GetParent](#getparent)||
|[CPaneFrameWnd::GetPinState](#getpinstate)||
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|Bir mini çerçeve penceresinde bulunan görünür bölmeleri sayısını döndürür.|
|[CPaneFrameWnd::HitTest](#hittest)|Belirli bir anda hangi Mini çerçevenin parçası olduğunu belirler.|
|[CPaneFrameWnd::IsCaptured](#iscaptured)||
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||
|[CPaneFrameWnd::IsRollDown](#isrolldown)|Bir mini çerçeve aşağı toplu olup olmadığını belirler.|
|[CPaneFrameWnd::IsRollUp](#isrollup)|Bir mini çerçeve toplanan olup olmadığını belirler.|
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|Yerleştirme Zamanlayıcıyı durdurur.|
|[CPaneFrameWnd::LoadState](#loadstate)|Kayıt defterinden bölmedeki durumunu yükler.|
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|Yerleştirme mümkün olup olmadığını belirler.|
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|En son konumunu Mini çerçeve penceresinin docks.|
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|Toplama Zamanlayıcıyı durdurur.|
|[CPaneFrameWnd::OnMovePane](#onmovepane)|Mini çerçeve penceresi tarafından belirtilen bir uzaklık taşır.|
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|Kapsanan bir bölme düzenini ayarlar.|
|[CPaneFrameWnd::OnSetRollUpTimer](#onsetrolluptimer)|Toplama Zamanlayıcıyı ayarlar.|
|[CPaneFrameWnd::OnShowPane](#onshowpane)|Bir mini çerçeve bölmesinde gizli veya gösterilen framework tarafından çağırılır.|
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|Bir mini çerçeve penceresi içinde bir kullanıcı tarafından sağlanan noktası içeriyorsa bir bölme döndürür.|
|[CPaneFrameWnd::Pin](#pin)||
|`CPaneFrameWnd::PreTranslateMessage`|Sınıfı tarafından kullanılan [CWinApp](../../mfc/reference/cwinapp-class.md) için dağıtılmadan önce pencere iletilerini çevrilecek [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows işlevleri.|
|[CPaneFrameWnd::RedrawAll](#redrawall)|Tüm Mini çerçeve pencereleri yeniden çizer.|
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|Geçerli olmayan bölmeleri kaldırmak için framework tarafından çağırılır.|
|[CPaneFrameWnd::RemovePane](#removepane)|Bir bölme Mini çerçeve penceresinde kaldırır.|
|[CPaneFrameWnd::ReplacePane](#replacepane)|Bir bölme birbiriyle değiştirir.|
|[CPaneFrameWnd::SaveState](#savestate)|Bölmedeki durumu kayıt defterine kaydeder.|
|`CPaneFrameWnd::Serialize`|Okur veya ya da bir arşivden bu nesneyi yazar.|
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|Kümeleri düğmeleri açıklamalı alt yazı.|
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|Yerleştirme Zamanlayıcıyı ayarlar.|
|[CPaneFrameWnd::SetDockState](#setdockstate)|Yerleştirme durumunu ayarlar.|
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|Predocking durumu ayarlamak için framework tarafından çağırılır.|
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|Bir kapsanan bölmesine boyutu eşdeğer olan bir mini çerçeve penceresinin boyutunu ayarlar.|
|[CPaneFrameWnd::StartTearOff](#starttearoff)|Bir menü tears.|
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|Bir mini çerçeve yukarı veya aşağı aylarına olup olmadığını belirler.|
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|Bir mini çerçeve pencere kenarlıklarını çizer.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|Pencere sınıfı CS_SAVEBITS sınıfı stiliyle kaydetmek belirtir.|

## <a name="remarks"></a>Açıklamalar

Framework otomatik olarak oluşturur bir `CPaneFrameWnd` bir bölme bir kayan duruma dayalı bir durumdan geçildiğinde nesne.

Bir mini çerçeve penceresinin içeriğini ile sürüklenebilir görünür (hemen yerleştirme) veya bir sürükleme dikdörtgenini (standart yerleştirme) kullanıyor. Mini çerçeve davranış sürükleyerek kullanıcının mini çerçevenin kapsayıcı bölmenin yerleştirme modu belirler. Daha fazla bilgi için [CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).

Bir mini çerçeve penceresi düğmeleri kapsanan bölmesinde stili uygun olarak açıklamalı alt yazı görüntüler. Bölme kapatılabilir, ( [CBasePane::CanBeClosed](../../mfc/reference/cbasepane-class.md#canbeclosed)), bir Kapat düğmesi görüntüler. Bölmesinde AFX_CBRS_AUTO_ROLLUP stile sahipse, PIN görüntüler.

Öğesinden bir sınıf türetirseniz `CPaneFrameWnd`, nasıl oluşturulduğu framework söylemeniz gerekir. Ya da geçersiz kılarak sınıfı oluşturmak [CPane::CreateDefaultMiniframe](../../mfc/reference/cpane-class.md#createdefaultminiframe), veya `CPane::m_pMiniFrameRTC` BT'nin sınıfınız için çalışma zamanı sınıf bilgileri işaret şekilde üyesi.

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

*pWnd*<br/>
[in] Eklemek için bölme.

##  <a name="addremovepanefromgloballist"></a>  CPaneFrameWnd::AddRemovePaneFromGlobalList

Ekler veya bir bölme Genel listeden kaldırır.

```
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,
    BOOL bAdd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in] Eklemek veya kaldırmak için bölme.

*Bekle*<br/>
[in] Sıfır olmayan, bölmesi ekleme. 0 ise, bölmesini kaldırın.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="adjustlayout"></a>  CPaneFrameWnd::AdjustLayout

Mini çerçeve düzenini ayarlar.

```
virtual void AdjustLayout();
```

##  <a name="adjustpaneframes"></a>  CPaneFrameWnd::AdjustPaneFrames


```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="calcbordersize"></a>  CPaneFrameWnd::CalcBorderSize

Bir mini çerçeve gizlenmek kenarlıklarını boyutunu hesaplar.

```
virtual void CalcBorderSize(CRect& rectBorderSize) const;
```

### <a name="parameters"></a>Parametreler

*rectBorderSize*<br/>
[out] Mini çerçeve gizlenmek kenarlığının piksel cinsinden boyutunu içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir mini çerçeve gizlenmek kenarlığını boyutunu hesaplamak için framework tarafından çağırılır. Bir mini çerçeve gizlenmek bir araç çubuğu içerip içermediğini veya döndürülen boyutuna bağlıdır [CDockablePane](../../mfc/reference/cdockablepane-class.md).

##  <a name="calcexpecteddockedrect"></a>  CPaneFrameWnd::CalcExpectedDockedRect

Yerleşik pencere beklenen dikdörtgen hesaplayın.

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Parametreler

*pWndToDock*<br/>
[in] Pencere sabitlemek için bir işaretçi.

*ptMouse*<br/>
[in] Fare konumu.

*rectResult*<br/>
[out] Hesaplanan dikdörtgen.

*bDrawTab*<br/>
[out] TRUE ise bir sekme çizin. FALSE ise bir sekme çekmek değil.

*ppTargetBar*<br/>
[out] Hedef bölmesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir kullanıcı tarafından belirtilen noktasına penceresi Sürüklediyseniz, bir pencere kaplayabilir dikdörtgen hesaplar *ptMouse* ve yerleştirilmiş vardır.

##  <a name="canbeattached"></a>  CPaneFrameWnd::CanBeAttached

Başka bir bölüm ya da çerçeve penceresi geçerli bölmesini yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başka bir bölüm ya da çerçeve penceresi bölmesi yuvalanabilir TRUE; Aksi durumda FALSE.

##  <a name="canbedockedtopane"></a>  CPaneFrameWnd::CanBeDockedToPane

Bir bölmesine Mini çerçeve penceresinin yerleştirilmiş olup olmadığını belirler.

```
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;
```

### <a name="parameters"></a>Parametreler

*pDockingBar*<br/>
[in] Bir bölme.

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve için sabitlenebilir olursa sıfır dışı *pDockingBar*; Aksi durumda 0.

##  <a name="checkgrippervisibility"></a>  CPaneFrameWnd::CheckGripperVisibility


```
virtual void CheckGripperVisibility();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="converttotabbeddocument"></a>  CPaneFrameWnd::ConvertToTabbedDocument

Bölmesinde sekmeli belgeye dönüştürür.

```
virtual void ConvertToTabbedDocument();
```

##  <a name="create"></a>  CPaneFrameWnd::Create

Bir mini çerçeve gizlenmek oluşturur ve ona ekler [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) nesne.

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszWindowName*<br/>
[in] Miniframe penceresinde görüntülenecek metni belirtir.

*dwStyle*<br/>
[in] Pencere stilini belirtir. Daha fazla bilgi için [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*Rect*<br/>
[in] Başlangıç boyutu ve Mini çerçeve gizlenmek konumunu belirtir.

[in] [out] *pParentWnd* Mini çerçeve gizlenmek üst çerçevenin belirtir. Bu değer NULL olmamalıdır.

[in] [out] *pContext* belirtir kullanıcı tanımlı bağlamı.

### <a name="return-value"></a>Dönüş Değeri

Pencerenin başarıyla oluşturulursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir mini çerçeve gizlenmek iki adımda oluşturulur. İlk olarak, çerçeve oluşturur bir `CPaneFrameWnd` nesne. İkinci olarak, çağıran `Create` Windows mini çerçeve gizlenmek oluşturup buna eklemek için `CPaneFrameWnd` nesne.

##  <a name="createex"></a>  CPaneFrameWnd::CreateEx

Bir mini çerçeve gizlenmek oluşturur ve ona ekler [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) nesne.

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

*dwStyleEx*<br/>
[in] Genişletilmiş pencere stilini belirtir. Daha fazla bilgi için [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

*lpszWindowName*<br/>
[in] Miniframe penceresinde görüntülenecek metni belirtir.

*dwStyle*<br/>
[in] Pencere stilini belirtir. Daha fazla bilgi için [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*Rect*<br/>
[in] Başlangıç boyutu ve Mini çerçeve gizlenmek konumunu belirtir.

[in] [out] *pParentWnd* Mini çerçeve gizlenmek üst çerçevenin belirtir. Bu değer NULL olmamalıdır.

[in] [out] *pContext* belirtir kullanıcı tanımlı bağlamı.

### <a name="return-value"></a>Dönüş Değeri

Pencerenin başarıyla oluşturulursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir mini çerçeve gizlenmek iki adımda oluşturulur. İlk olarak, çerçeve oluşturur bir `CPaneFrameWnd` nesne. İkinci olarak, çağıran `Create` Windows mini çerçeve gizlenmek oluşturup buna eklemek için `CPaneFrameWnd` nesne.

##  <a name="dockpane"></a>  CPaneFrameWnd::DockPane

Bölmesinde docks.

```
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```

### <a name="parameters"></a>Parametreler

*bWasDocked*<br/>
[out] Bölmesinde zaten sabitlenmiş TRUE; Aksi durumda FALSE.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa `CDockablePane` bölmenin yerleştirilmiş için; Aksi takdirde NULL.

##  <a name="findfloatingpanebyid"></a>  CPaneFrameWnd::FindFloatingPaneByID

Belirtilen denetim kimliği içeren bölme kayan bölmeleri genel listesinde bulur.

```
static CBasePane* FindFloatingPaneByID(UINT nID);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
[in] Bulunacak bölmesinde denetim Kimliğini temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen denetim kimliği bölmesiyle; hiçbir bölmesinde belirtilen denetim kimliği varsa, aksi takdirde, NULL

##  <a name="framefrompoint"></a>  CPaneFrameWnd::FrameFromPoint

Belirtilen nokta içeren bir mini çerçeve pencere bulur.

```
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,
    int nSensitivity,
    CPaneFrameWnd* pFrameToExclude = NULL,
    BOOL bFloatMultiOnly = FALSE);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
[in] Ekran koordinatları noktası.

*nSensitivity*<br/>
[in] Mini çerçeve arama alanının bu boyutunu artırabilirsiniz. Belirtilen noktasını artan alanında düşerse bir mini çerçeve arama ölçütleri karşılar.

*pFrameToExclude*<br/>
[in] Arama hariç tutmak için bir mini çerçeve penceresi belirtir.

*bFloatMultiOnly*<br/>
[in] TRUE ise yalnızca CBRS_FLOAT_MULTI stil Mini çerçeve pencereleri arayın. FALSE ise, tüm Mini çerçeve pencereleri arayın.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi içeren bir mini çerçeve pencere *pt*; Aksi takdirde NULL.

##  <a name="getcaptionheight"></a>  CPaneFrameWnd::GetCaptionHeight

Mini çerçeve pencere başlığı yüksekliğini döndürür.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresinin piksel cinsinden yüksekliği.

### <a name="remarks"></a>Açıklamalar

Bir mini çerçeve yüksekliğini belirlemek için bu yöntemi çağırın. Varsayılan olarak, yükseklik SM_CYSMCAPTION için ayarlanır. Daha fazla bilgi için [GetSystemMetrics işlevi](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics).

##  <a name="getcaptionrect"></a>  CPaneFrameWnd::GetCaptionRect

Bir mini çerçeve pencere başlığı sınırlayıcı dikdörtgenini hesaplar.

```
virtual void GetCaptionRect(CRect& rectCaption) const;
```

### <a name="parameters"></a>Parametreler

*rectCaption*<br/>
[out] Ekran koordinatları Mini çerçeve pencere başlığı konumunu ve boyutunu içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir mini çerçeve pencere başlığı sınırlayıcı dikdörtgenini hesaplamak için framework tarafından çağırılır.

##  <a name="getcaptiontext"></a>  CPaneFrameWnd::GetCaptionText

Açıklamalı alt yazı metni döndürür.

```
virtual CString GetCaptionText();
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçevenin başlık metni.

### <a name="remarks"></a>Açıklamalar

Bu yöntem açıklamalı alt yazı metni görüntüler çerçevesi tarafından çağrılır.

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

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

##  <a name="getfirstvisiblepane"></a>  CPaneFrameWnd::GetFirstVisiblePane

Bir mini çerçeve penceresinde yer alan ilk görünür bölmesine döndürür.

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>Dönüş Değeri

İlk bölme Mini çerçeve veya mini çerçevenin hiçbir bölmeleri içeriyorsa NULL.

##  <a name="gethotpoint"></a>  CPaneFrameWnd::GetHotPoint


```
CPoint GetHotPoint() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getpane"></a>  CPaneFrameWnd::GetPane

Mini çerçeve penceresinde yer alan bir bölme döndürür.

```
virtual CWnd* GetPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresi yok bölmeleri içeriyorsa, Mini çerçeve veya NULL içerdiği bölme.

### <a name="remarks"></a>Açıklamalar

##  <a name="getpanecount"></a>  CPaneFrameWnd::GetPaneCount

Bir mini çerçeve penceresinde bulunan bölmeleri sayısını döndürür.

```
virtual int GetPaneCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve pencere bölmelerinde sayısı. Bu değer sıfır olabilir.

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

Bir mini çerçeve penceresinde bulunan görünür bölmeleri sayısını döndürür.

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünür bölmeleri sayısı.

### <a name="remarks"></a>Açıklamalar

##  <a name="hittest"></a>  CPaneFrameWnd::HitTest

Belirli bir anda hangi Mini çerçevenin parçası olduğunu belirler.

```
virtual LRESULT HitTest(
    CPoint point,
    BOOL bDetectCaption);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] Test noktası.

*bDetectCaption*<br/>
[in] TRUE ise caption karşı noktası denetleyin. FALSE ise caption yoksayın.

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

|Değer|Açıklama|
|-----------|-------------|
|HTNOWHERE|Mini çerçeve penceresi dışında noktasıdır.|
|HTCLIENT|İstemci alanında noktasıdır.|
|HTCAPTION|Resim yazısını noktasıdır.|
|HTTOP|En üstünde noktasıdır.|
|HTTOPLEFT|Sol üst köşede noktasıdır.|
|HTTOPRIGHT|Sağ üst kısımdaki noktasıdır.|
|HTLEFT|Solda noktasıdır.|
|HTRIGHT|Sağ taraftaki noktasıdır.|
|HTBOTTOM|Alttaki noktasıdır.|
|HTBOTTOMLEFT|Sol alt kısmında noktasıdır.|
|HTBOTTOMRIGHT|Alt sağ noktasıdır.|

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

Bir mini çerçeve aşağı toplu olup olmadığını belirler.

```
virtual BOOL IsRollDown() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve aşağı alınması gerekiyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir mini çerçeve aşağı toplu olup olmadığını belirlemek için framework tarafından çağırılır. AFX_CBRS_AUTO_ROLLUP bayrağına sahip en az bir bölmesinde içeriyorsa, toplama/rolldown özelliği bir mini çerçeve için etkin. Bir bölme oluşturulduğunda bu bayrağı ayarlanır. Daha fazla bilgi için [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

Varsayılan olarak, çerçeve, fare işaretçisini penceresini aşağı alınması gerekip gerekmediğini belirlemek için Mini çerçeve penceresi dikdörtgen içinde olup olmadığını denetler. Türetilen bir sınıfta bu davranışı geçersiz kılabilirsiniz.

##  <a name="isrollup"></a>  CPaneFrameWnd::IsRollUp

Bir mini çerçeve toplanan olup olmadığını belirler.

```
virtual BOOL IsRollUp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve sağlık dökümü TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir mini çerçeve toplanan olup olmadığını belirlemek için framework tarafından çağırılır. AFX_CBRS_AUTO_ROLLUP bayrağına sahip en az bir bölmesinde içeriyorsa, toplama/rolldown özelliği bir mini çerçeve için etkin. Bir bölme oluşturulduğunda bu bayrağı ayarlanır. Daha fazla bilgi için [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

Varsayılan olarak, çerçeve, fare işaretçisini pencereyi geri alınması gerekip gerekmediğini belirlemek için Mini çerçeve penceresi dikdörtgen içinde olup olmadığını denetler. Türetilen bir sınıfta bu davranışı geçersiz kılabilirsiniz.

##  <a name="killdockingtimer"></a>  CPaneFrameWnd::KillDockingTimer

Yerleştirme Zamanlayıcıyı durdurur.

```
void KillDockingTimer();
```

##  <a name="loadstate"></a>  CPaneFrameWnd::LoadState

Kayıt defterinden bölmedeki durumunu yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Profil adı.

*uiID*<br/>
[in] Bölmesinde kimliği.

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde durumu başarıyla yüklendi TRUE; Aksi durumda FALSE.

##  <a name="m_busesavebits"></a>  CPaneFrameWnd::m_bUseSaveBits

CS_SAVEBITS sınıfı stilde pencere sınıfını belirtir.

```
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;
```

### <a name="remarks"></a>Açıklamalar

Bu statik üyeye CS_SAVEBITS stilde Mini çerçeve pencere sınıfı kaydı için true olarak ayarlayın. Bu, bir kullanıcı Mini çerçeve sürüklediğinde titremeyi azaltmaya yardımcı olabilir.

##  <a name="onbeforedock"></a>  CPaneFrameWnd::OnBeforeDock

Yerleştirme mümkün olup olmadığını belirler.

```
virtual BOOL OnBeforeDock();
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme mümkün ise TRUE; Aksi takdirde FALSE.

##  <a name="oncheckrollstate"></a>  CPaneFrameWnd::OnCheckRollState

Bir mini çerçeve yukarı veya aşağı aylarına olup olmadığını belirler.

```
virtual void OnCheckRollState();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir mini çerçeve yukarı veya aşağı aylarına olup olmadığını belirlemek için framework tarafından çağırılır.

Varsayılan olarak, çerçeve çağrı [CPaneFrameWnd::IsRollUp](#isrollup) ve [CPaneFrameWnd::IsRollDown](#isrolldown) yalnızca uzatır veya mini çerçevenin geri yükler. Türetilen bir sınıfta farklı bir görsel efekt kullanmak için bu yöntemi geçersiz kılabilirsiniz.

##  <a name="ondocktorecentpos"></a>  CPaneFrameWnd::OnDockToRecentPos

En son konumunu Mini çerçeve penceresinin docks.

```
virtual void OnDockToRecentPos();
```

##  <a name="ondrawborder"></a>  CPaneFrameWnd::OnDrawBorder

Bir mini çerçeve pencere kenarlıklarını çizer.

```
virtual void OnDrawBorder(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Kenarlık çizmek için kullanılan cihaz bağlamı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem Mini çerçeve penceresinin Kenarlıkları çizmek için framework tarafından çağırılır.

##  <a name="onkillrolluptimer"></a>  CPaneFrameWnd::OnKillRollUpTimer

Toplama Zamanlayıcıyı durdurur.

```
virtual void OnKillRollUpTimer();
```

##  <a name="onmovepane"></a>  CPaneFrameWnd::OnMovePane

Mini çerçeve penceresi tarafından belirtilen bir uzaklık taşır.

```
virtual void OnMovePane(
    CPane* pBar,
    CPoint ptOffset);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in] Bir bölme (yoksayıldı) için bir işaretçi.

*ptOffset*<br/>
[in] Bölmesinde taşımak, uzaklığı.

##  <a name="onpanerecalclayout"></a>  CPaneFrameWnd::OnPaneRecalcLayout

Bir mini çerçeve penceresi içinde bir bölme düzenini ayarlar.

```
virtual void OnPaneRecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

Framework bu yöntemi çağırır Mini çerçeve penceresi içinde bir bölme düzenini ayarlamanız gerekir.

Varsayılan olarak, Mini çerçeve penceresi tüm istemci alanını kaplayacak şekilde bölmesinde yer alır.

##  <a name="onsetrolluptimer"></a>  CPaneFrameWnd::OnSetRollUpTimer

Toplama Zamanlayıcıyı ayarlar.

```
virtual void OnSetRollUpTimer();
```

##  <a name="onshowpane"></a>  CPaneFrameWnd::OnShowPane

Bir mini çerçeve bölmesinde gizli veya gösterilen framework tarafından çağırılır.

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[in] Yüklenmekte olan bölmesinde gösterilen veya gizli.

*bBilgi Göster*<br/>
[in] Bölmesinde gösterilen TRUE; Bölmenin gizli değilse FALSE.

### <a name="remarks"></a>Açıklamalar

Bir mini çerçeve bölmesinde gösterilen veya gizli framework tarafından çağırılır. Varsayılan uygulama, hiçbir şey yapmaz.

##  <a name="pin"></a>  CPaneFrameWnd::Pin


```
void Pin(BOOL bPin = TRUE);
```

### <a name="parameters"></a>Parametreler

[in] *bPin*

### <a name="remarks"></a>Açıklamalar

##  <a name="panefrompoint"></a>  CPaneFrameWnd::PaneFromPoint

Bir mini çerçeve penceresi içinde bir kullanıcı tarafından sağlanan noktası içeriyorsa bir bölme döndürür.

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bCheckVisibility);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] Noktayı, kullanıcı, ekran koordinatlarında tıkladı.

*nSensitivity*<br/>
[in] Bu parametre kullanılmaz.

*bCheckVisibility*<br/>
[in] Yalnızca görünür bölmeleri döndürülmesi gerektiğini belirtmek için TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tıkladı bölmesinde veya hiçbir bölmesinde o konumda yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Belirtilen noktasını içeren bir bölme elde etmek için bu yöntemi çağırın.

##  <a name="redrawall"></a>  CPaneFrameWnd::RedrawAll

Tüm Mini çerçeve pencereleri yeniden çizer.

```
static void RedrawAll();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağırarak tüm Mini çerçeve pencereleri güncelleştirmeleri [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) her penceresi için.

##  <a name="removenonvalidpanes"></a>  CPaneFrameWnd::RemoveNonValidPanes

Geçerli olmayan bölmeleri kaldırmak için framework tarafından çağırılır.

```
virtual void RemoveNonValidPanes();
```

##  <a name="removepane"></a>  CPaneFrameWnd::RemovePane

Bir bölme Mini çerçeve penceresinde kaldırır.

```
virtual void RemovePane(
    CBasePane* pWnd,
    BOOL bDestroy = FALSE,
    BOOL bNoDelayedDestroy = FALSE);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in] Bölmesinde, kaldırmak için bir işaretçi.

*bDestroy*<br/>
[in] Mini çerçeve ne olacağını belirtir. Varsa *bDestroy* doğru ise, bu yöntem hemen Mini çerçeve penceresini yok eder. FALSE ise, bu yöntem belirli bir gecikmeden sonra Mini çerçeve penceresini yok eder.

*bNoDelayedDestroy*<br/>
[in] TRUE ise Gecikmeli yok etme devre dışı bırakıldı. FALSE ise Gecikmeli yok etme etkinleştirilir.

### <a name="remarks"></a>Açıklamalar

Framework, hemen veya belirli bir gecikmeden sonra Mini çerçeve pencerelerini yok edebilirsiniz. Mini çerçeve pencerelerini yok edilmesini geciktirmek istiyorsanız FALSE geçirin *bNoDelayedDestroy* parametresi. Gecikmeli yok etme framework AFX_WM_CHECKEMPTYMINIFRAME ileti işlediğinde oluşur.

##  <a name="replacepane"></a>  CPaneFrameWnd::ReplacePane

Bir bölme birbiriyle değiştirir.

```
virtual void ReplacePane(
    CBasePane* pBarOrg,
    CBasePane* pBarReplaceWith);
```

### <a name="parameters"></a>Parametreler

*pBarOrg*<br/>
[in] Özgün bölmesi için bir işaretçi.

*pBarReplaceWith*<br/>
[in] Özgün bölmesinde değiştirir bölmesi için bir işaretçi.

##  <a name="savestate"></a>  CPaneFrameWnd::SaveState

Bölmedeki durumu kayıt defterine kaydeder.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Profil adı.

*uiID*<br/>
[in] Bölmesinde kimliği.

### <a name="return-value"></a>Dönüş Değeri

Bölmesinde durumu başarıyla kaydedildi TRUE; Aksi durumda FALSE.

##  <a name="setcaptionbuttons"></a>  CPaneFrameWnd::SetCaptionButtons

Kümeleri düğmeleri açıklamalı alt yazı.

```
virtual void SetCaptionButtons(DWORD dwButtons);
```

### <a name="parameters"></a>Parametreler

*dwButtons*<br/>
[in] Bit düzeyinde OR birleşimi aşağıdaki değerlerden biri:

- AFX_CAPTION_BTN_CLOSE

- AFX_CAPTION_BTN_PIN

- AFX_CAPTION_BTN_MENU

- AFX_CAPTION_BTN_CUSTOMIZE

##  <a name="setdelayshow"></a>  CPaneFrameWnd::SetDelayShow


```
void SetDelayShow(BOOL bDelayShow);
```

### <a name="parameters"></a>Parametreler

[in] *bDelayShow*

### <a name="remarks"></a>Açıklamalar

##  <a name="setdockingmanager"></a>  CPaneFrameWnd::SetDockingManager


```
void SetDockingManager(CDockingManager* pManager);
```

### <a name="parameters"></a>Parametreler

[in] *pManager*

### <a name="remarks"></a>Açıklamalar

##  <a name="setdockingtimer"></a>  CPaneFrameWnd::SetDockingTimer

Yerleştirme Zamanlayıcıyı ayarlar.

```
void SetDockingTimer(UINT nTimeOut);
```

### <a name="parameters"></a>Parametreler

*nTimeOut*<br/>
[in] Zaman aşımı değerini milisaniye cinsinden.

##  <a name="setdockstate"></a>  CPaneFrameWnd::SetDockState

Yerleştirme durumunu ayarlar.

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>Parametreler

*pDockManager*<br/>
[in] Yerleştirme Yöneticisi için bir işaretçi.

##  <a name="sethotpoint"></a>  CPaneFrameWnd::SetHotPoint


```
void SetHotPoint(CPoint& ptNew);
```

### <a name="parameters"></a>Parametreler

[in] *ptNew*

### <a name="remarks"></a>Açıklamalar

##  <a name="setpredockstate"></a>  CPaneFrameWnd::SetPreDockState

Predocking durumu ayarlamak için framework tarafından çağırılır.

```
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,
    CBasePane* pBarToDock = NULL,
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```

### <a name="parameters"></a>Parametreler

*preDockState*<br/>
[in] Olası değerler:

- PDS_NOTHING,

- PDS_DOCK_REGULAR,

- PDS_DOCK_TO_TAB

*pBarToDock*<br/>
[in] Yerleştirme bölmesine bir işaretçi.

*dockMethod*<br/>
[in] Yerleştirme yöntemi. (Bu parametre yoksayılır.)

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresi yerleştirilmemiş ise TRUE; Sabitlenmişken FALSE.

##  <a name="sizetocontent"></a>  CPaneFrameWnd::SizeToContent

Kapsanan bölmesine eşdeğer olan bir mini çerçeve penceresinin boyutunu ayarlar.

```
virtual void SizeToContent();
```

### <a name="remarks"></a>Açıklamalar

Bir mini çerçeve penceresinin içerdiği bir bölme boyutunu boyutunu ayarlamak için bu yöntemi çağırın.

##  <a name="starttearoff"></a>  CPaneFrameWnd::StartTearOff

Bir menü tears.

```
BOOL StartTearOff(CMFCPopu* pMenu);
```

### <a name="parameters"></a>Parametreler

*pMenu*<br/>
[in] Bir menü işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa TRUE; Aksi takdirde FALSE.

##  <a name="storerecentdocksiteinfo"></a>  CPaneFrameWnd::StoreRecentDockSiteInfo


```
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>Parametreler

[in] *pBar*

### <a name="remarks"></a>Açıklamalar

##  <a name="storerecenttabrelatedinfo"></a>  CPaneFrameWnd::StoreRecentTabRelatedInfo


```
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>Parametreler

*pDockingBar*<br/>
[in] [in] *pTabbedBar*

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
