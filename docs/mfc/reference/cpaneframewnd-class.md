---
title: CPaneFrameWnd Sınıf
ms.date: 11/04/2016
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
ms.openlocfilehash: 02eee13928979a7d220ce03f9f61c789c6320b6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364108"
---
# <a name="cpaneframewnd-class"></a>CPaneFrameWnd Sınıf

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

Bir bölme içeren bir mini çerçeve penceresi uygular. Bölme pencerenin istemci alanını doldurur.

## <a name="syntax"></a>Sözdizimi

```
class CPaneFrameWnd : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPaneFrameWnd::AddPane](#addpane)|Bölme ekler.|
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](#addremovepanefromgloballist)|Genel listeden bölme ekler veya kaldırır.|
|[CPaneFrameWnd::Düzeni Ayarla](#adjustlayout)|Mini çerçeve penceresinin düzenini ayarlar.|
|[CPaneFrameWnd::AdjustPaneFrames](#adjustpaneframes)||
|[CPaneFrameWnd::CalcBorderSize](#calcbordersize)|Mini çerçeve penceresi için kenarlıkların boyutunu hesaplar.|
|[CPaneFrameWnd::CalcExpectedDockedRect](#calcexpecteddockedrect)|Kenetlenmiş bir pencerenin beklenen dikdörtgenini hesaplayın.|
|[CPaneFrameWnd::CanBeAttached](#canbeattached)|Geçerli bölmenin başka bir bölmeye veya çerçeve penceresine sabitlenip yapıştırılamayacağını belirler.|
|[CPaneFrameWnd::CanBeDockedToPane](#canbedockedtopane)|Mini çerçeve penceresinin bölmeye sabitlenip yapıştırılamayacağını belirler.|
|[CPaneFrameWnd::CheckGripperGörünürlik](#checkgrippervisibility)||
|[CPaneFrameWnd::ConvertToTabbedBelge](#converttotabbeddocument)|Bölmeyi sekmeli bir belgeye dönüştürür.|
|[CPaneFrameWnd::Oluştur](#create)|Bir mini çerçeve penceresi oluşturur ve `CPaneFrameWnd` nesneye bağlar.|
|[CPaneFrameWnd::CreateEx](#createex)|Bir mini çerçeve penceresi oluşturur ve `CPaneFrameWnd` nesneye bağlar.|
|[CPaneFrameWnd::DockPane](#dockpane)|Bölmeyi sabitler.|
|[CPaneFrameWnd::FindFloatingPaneByID](#findfloatingpanebyid)|Kayan bölmeler genel listesinde belirtilen denetim kimliğine sahip bir bölme bulur.|
|[CPaneFrameWnd::FrameFromPoint](#framefrompoint)|Kullanıcı tarafından sağlanan bir nokta içeren mini çerçeve penceresini bulur.|
|[CPaneFrameWnd::GetCaptionHeight](#getcaptionheight)|Mini çerçeve pencere başlığının yüksekliğini döndürür.|
|[CPaneFrameWnd::GetCaptionRect](#getcaptionrect)|Mini çerçeve pencere başlığının sınırlayıcı dikdörtgenini hesaplar.|
|[CPaneFrameWnd::GetCaptionText](#getcaptiontext)|Resim yazısı metnini döndürür.|
|[CPaneFrameWnd::GetDockingManager](#getdockingmanager)||
|[CPaneFrameWnd::GetDockingMode](#getdockingmode)|Yerleştirme modunu döndürür.|
|[CPaneFrameWnd::GetFirstVisiblePane](#getfirstvisiblepane)|Mini çerçeve penceresinde bulunan ilk görünür bölmeyi döndürür.|
|[CPaneFrameWnd::GetHotPoint](#gethotpoint)||
|[CPaneFrameWnd::GetPane](#getpane)|Mini çerçeve penceresinde bulunan bir bölmeyi döndürür.|
|[CPaneFrameWnd::GetPaneCount](#getpanecount)|Mini çerçeve penceresinde bulunan bölme sayısını verir.|
|[CPaneFrameWnd::GetParent](#getparent)||
|[CPaneFrameWnd::GetPinState](#getpinstate)||
|[CPaneFrameWnd::GetRecentFloatingRect](#getrecentfloatingrect)||
|[CPaneFrameWnd::GetVisiblePaneCount](#getvisiblepanecount)|Mini çerçeve penceresinde bulunan görünür bölme sayısını döndürür.|
|[CPaneFrameWnd::HitTest](#hittest)|Belirli bir noktada mini çerçeve penceresinin hangi bölümünün olduğunu belirler.|
|[CPaneFrameWnd::Yakalanır](#iscaptured)||
|[CPaneFrameWnd::IsDelayShow](#isdelayshow)||
|[CPaneFrameWnd::IsRollDown](#isrolldown)|Mini çerçeve penceresinin aşağı yayılıp yuvarlanmaması gerektiğini belirler.|
|[CPaneFrameWnd::IsRollUp](#isrollup)|Mini çerçeve penceresinin yuvarlanıp yuvarlanmaması gerektiğini belirler.|
|[CPaneFrameWnd::KillDockingTimer](#killdockingtimer)|Yerleştirme zamanlayıcısını durdurur.|
|[CPaneFrameWnd::LoadState](#loadstate)|Bölmenin durumunu kayıt defterinden yükler.|
|[CPaneFrameWnd::OnBeforeDock](#onbeforedock)|Yerleştirmenin mümkün olup olmadığını belirler.|
|[CPaneFrameWnd::OnDockToRecentPos](#ondocktorecentpos)|Mini çerçeve penceresini en son konumunda sabitler.|
|[CPaneFrameWnd::OnKillRollUpTimer](#onkillrolluptimer)|Toplama zamanlayıcısını durdurur.|
|[CPaneFrameWnd::OnMovePane](#onmovepane)|Mini çerçeve penceresini belirli bir ofset ile taşır.|
|[CPaneFrameWnd::OnPaneRecalcLayout](#onpanerecalclayout)|İçerdiği bölmenin düzenini ayarlar.|
|[CPaneFrameWnd::OnSetRollTimer](#onsetrolluptimer)|Toplama zamanlayıcısını ayarlar.|
|[CPaneFrameWnd::OnShowPane](#onshowpane)|Mini çerçeve penceresindeki bir bölme gizlendiğinde veya görüntülendiğinde çerçeve tarafından çağrılır.|
|[CPaneFrameWnd::PaneFromPoint](#panefrompoint)|Bir mini çerçeve penceresi içinde kullanıcı tarafından sağlanan bir nokta içeriyorsa bir bölme döndürür.|
|[CPaneFrameWnd::Pin](#pin)||
|`CPaneFrameWnd::PreTranslateMessage`|[CWinApp](../../mfc/reference/cwinapp-class.md) sınıfı tarafından, pencere iletilerini [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirmek için kullanılır.|
|[CPaneFrameWnd::RedrawAll](#redrawall)|Tüm mini çerçeve pencereleri yeniden çizer.|
|[CPaneFrameWnd::RemoveNonValidPanes](#removenonvalidpanes)|Geçerli olmayan bölmeleri kaldırmak için çerçeve tarafından çağrılır.|
|[CPaneFrameWnd::RemovePane](#removepane)|Küçük çerçeve penceresinden bir bölme kaldırır.|
|[CPaneFrameWnd::ReplacePane](#replacepane)|Bir bölmeyi diğeriyle değiştirir.|
|[CPaneFrameWnd::SaveState](#savestate)|Bölmenin durumunu kayıt defterine kaydeder.|
|`CPaneFrameWnd::Serialize`|Bu nesneyi arşivden veya arşivden okur veya yazar.|
|[CPaneFrameWnd::SetCaptionButtons](#setcaptionbuttons)|Resim yazısı düğmelerini ayarlar.|
|[CPaneFrameWnd::SetDelayShow](#setdelayshow)||
|[CPaneFrameWnd::SetDockingManager](#setdockingmanager)||
|[CPaneFrameWnd::SetDockingTimer](#setdockingtimer)|Yerleştirme zamanlayıcısını ayarlar.|
|[CPaneFrameWnd::SetDockState](#setdockstate)|Kenetlenme durumunu ayarlar.|
|[CPaneFrameWnd::SetHotPoint](#sethotpoint)||
|[CPaneFrameWnd::SetPreDockState](#setpredockstate)|Predocking durumunu ayarlamak için çerçeve tarafından çağrıldı.|
|[CPaneFrameWnd::SizeToContent](#sizetocontent)|Mini çerçeve penceresinin boyutunu, içerdiği bölmeye eşdeğer olacak şekilde ayarlar.|
|[CPaneFrameWnd::StartTearOff](#starttearoff)|Menüden gözyaşları.|
|[CPaneFrameWnd::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPaneFrameWnd::OnCheckRollState](#oncheckrollstate)|Mini çerçeve penceresinin yukarı mı yoksa aşağı mı yuvarlanması gerektiğini belirler.|
|[CPaneFrameWnd::OnDrawBorder](#ondrawborder)|Mini çerçeve penceresinin kenarlıklarını çizer.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPaneFrameWnd::m_bUseSaveBits](#m_busesavebits)|Pencere sınıfının CS_SAVEBITS sınıf stiliyle kaydedilip kaydedilemeyeceğini belirtir.|

## <a name="remarks"></a>Açıklamalar

Bir bölme kenetlenmiş `CPaneFrameWnd` durumdan kayan bir duruma geçtiğinde çerçeve otomatik olarak bir nesne oluşturur.

Bir mini çerçeve penceresi içeriği görünür (hemen yerleştirme) veya sürükleme dikdörtgeni (standart yerleştirme) kullanılarak sürüklenebilir. Mini çerçevenin kapsayıcı bölmesinin takma modu, mini çerçevenin sürükleme davranışını belirler. Daha fazla bilgi için [Bkz. CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).

Mini çerçeve penceresi, alt yazı üzerindeki düğmeleri bulunan bölme stiline uygun olarak görüntüler. Bölme kapatılabilirse [(CBasePane::CanBeClosed),](../../mfc/reference/cbasepane-class.md#canbeclosed)Kapat düğmesini görüntüler. Bölmede AFX_CBRS_AUTO_ROLLUP stili varsa, bir pin görüntülenir.

Bir sınıf `CPaneFrameWnd`türederseniz, çerçeveyi nasıl oluştureceğinizi söylemeniz gerekir. [CPane::CreateDefaultMiniframe'i](../../mfc/reference/cpane-class.md#createdefaultminiframe)geçersiz kılarak sınıfı oluşturun `CPane::m_pMiniFrameRTC` veya üyeyi sınıfınız için çalışma zamanı sınıf bilgilerine işaret edin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CPaneFrameWnd`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxPaneFrameWnd.h

## <a name="cpaneframewndaddpane"></a><a name="addpane"></a>CPaneFrameWnd::AddPane

Bölme ekler.

```
virtual void AddPane(CBasePane* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Eklenecek bölme.

## <a name="cpaneframewndaddremovepanefromgloballist"></a><a name="addremovepanefromgloballist"></a>CPaneFrameWnd::AddRemovePaneFromGlobalList

Genel listeden bölme ekler veya kaldırır.

```
static BOOL __stdcall AddRemovePaneFromGlobalList(
    CBasePane* pWnd,
    BOOL bAdd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Eklenecek veya kaldırılacak bölme.

*Baran*<br/>
[içinde] Sıfır değilse, bölmeyi ekleyin. 0 ise, bölmeyi kaldırın.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa sıfırolmayan; aksi takdirde 0.

## <a name="cpaneframewndadjustlayout"></a><a name="adjustlayout"></a>CPaneFrameWnd::Düzeni Ayarla

Mini çerçeve penceresinin düzenini ayarlar.

```
virtual void AdjustLayout();
```

## <a name="cpaneframewndadjustpaneframes"></a><a name="adjustpaneframes"></a>CPaneFrameWnd::AdjustPaneFrames

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndcalcbordersize"></a><a name="calcbordersize"></a>CPaneFrameWnd::CalcBorderSize

Miniframe penceresi için kenarlıkların boyutunu hesaplar.

```
virtual void CalcBorderSize(CRect& rectBorderSize) const;
```

### <a name="parameters"></a>Parametreler

*rectBorderSize*<br/>
[çıkış] Miniframe penceresinin kenarlığı piksel boyutu içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir miniframe penceresinin kenarlığı boyutunu hesaplamak için çerçeve tarafından çağrılır. Döndürülen boyut, mini çerçeve penceresinin araç çubuğu veya [CDockablePane](../../mfc/reference/cdockablepane-class.md)içerip içermediğine bağlıdır.

## <a name="cpaneframewndcalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CPaneFrameWnd::CalcExpectedDockedRect

Kenetlenmiş bir pencerenin beklenen dikdörtgenini hesaplayın.

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
[içinde] Kenetlenme penceresine bir işaretçi.

*ptMouse*<br/>
[içinde] Fare konumu.

*rektResult*<br/>
[çıkış] Hesaplanan dikdörtgen.

*bDrawTab*<br/>
[çıkış] TRUE ise, bir sekme çizin. FALSE ise, bir sekme çizmeyin.

*ppTargetBar*<br/>
[çıkış] Hedef bölmeye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir kullanıcı pencereyi *ptMouse* tarafından belirtilen noktaya sürüklüp oraya sabitlerse, pencerenin kapalacağı dikdörtgeni hesaplar.

## <a name="cpaneframewndcanbeattached"></a><a name="canbeattached"></a>CPaneFrameWnd::CanBeAttached

Geçerli bölmenin başka bir bölmeye veya çerçeve penceresine sabitlenip yapıştırılamayacağını belirler.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölme başka bir bölme ye veya çerçeve penceresine sabitlenebilirse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cpaneframewndcanbedockedtopane"></a><a name="canbedockedtopane"></a>CPaneFrameWnd::CanBeDockedToPane

Mini çerçeve penceresinin bölmeye sabitlenip yapıştırılamayacağını belirler.

```
virtual BOOL CanBeDockedToPane(const CDockablePane* pDockingBar) const;
```

### <a name="parameters"></a>Parametreler

*pDockingBar*<br/>
[içinde] Bir bölme.

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve *pDockingBar'a*sabitlenebilirse sıfıra inmez; aksi takdirde 0.

## <a name="cpaneframewndcheckgrippervisibility"></a><a name="checkgrippervisibility"></a>CPaneFrameWnd::CheckGripperGörünürlik

```
virtual void CheckGripperVisibility();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CPaneFrameWnd::ConvertToTabbedBelge

Bölmeyi sekmeli bir belgeye dönüştürür.

```
virtual void ConvertToTabbedDocument();
```

## <a name="cpaneframewndcreate"></a><a name="create"></a>CPaneFrameWnd::Oluştur

Bir miniframe penceresi oluşturur ve [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) nesnesine bağlar.

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
[içinde] Miniframe penceresinde görüntülenecek metni belirtir.

*Dwstyle*<br/>
[içinde] Pencere stilini belirtir. Daha fazla bilgi için [Bkz. Pencere Stilleri.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*Rect*<br/>
[içinde] Miniframe penceresinin başlangıç boyutunu ve konumunu belirtir.

*pParentWnd*<br/>
[içinde, dışarı] Miniframe penceresinin ana çerçevesini belirtir. Bu değer NULL olmamalıdır.

*Pcontext*<br/>
[içinde, dışarı] Kullanıcı tanımlı bağlamı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla oluşturulduysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Mini frame penceresi iki adımda oluşturulur. İlk olarak, çerçeve `CPaneFrameWnd` bir nesne oluşturur. İkinci olarak, `Create` Windows miniframe penceresini oluşturmak ve `CPaneFrameWnd` nesneye eklemek için çağırır.

## <a name="cpaneframewndcreateex"></a><a name="createex"></a>CPaneFrameWnd::CreateEx

Bir miniframe penceresi oluşturur ve [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) nesnesine bağlar.

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
[içinde] Genişletilmiş pencere stilini belirtir. Daha fazla bilgi için [bkz.](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)

*lpszWindowName*<br/>
[içinde] Miniframe penceresinde görüntülenecek metni belirtir.

*Dwstyle*<br/>
[içinde] Pencere stilini belirtir. Daha fazla bilgi için [Bkz. Pencere Stilleri.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*Rect*<br/>
[içinde] Miniframe penceresinin başlangıç boyutunu ve konumunu belirtir.

*pParentWnd*<br/>
[içinde, dışarı] Miniframe penceresinin ana çerçevesini belirtir. Bu değer NULL olmamalıdır.

*Pcontext*<br/>
[içinde, dışarı] Kullanıcı tanımlı bağlamı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla oluşturulduysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Mini frame penceresi iki adımda oluşturulur. İlk olarak, çerçeve `CPaneFrameWnd` bir nesne oluşturur. İkinci olarak, `Create` Windows miniframe penceresini oluşturmak ve `CPaneFrameWnd` nesneye eklemek için çağırır.

## <a name="cpaneframewnddockpane"></a><a name="dockpane"></a>CPaneFrameWnd::DockPane

Bölmeyi sabitler.

```
virtual CDockablePane* DockPane(BOOL& bWasDocked);
```

### <a name="parameters"></a>Parametreler

*bWasDocked*<br/>
[çıkış] Bölme zaten kenetlenmişse DOĞRU; aksi takdirde YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olduysa, `CDockablePane` bölmenin kenetlenmiş olduğu; aksi takdirde NULL.

## <a name="cpaneframewndfindfloatingpanebyid"></a><a name="findfloatingpanebyid"></a>CPaneFrameWnd::FindFloatingPaneByID

Kayan bölmeler genel listesinde belirtilen denetim kimliğine sahip bir bölme bulur.

```
static CBasePane* FindFloatingPaneByID(UINT nID);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] Bulmak için bölmenin denetim kimliğini temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen denetim kimliğine sahip bölme; aksi takdirde, NULL, hiçbir bölme belirtilen denetim kimliği varsa.

## <a name="cpaneframewndframefrompoint"></a><a name="framefrompoint"></a>CPaneFrameWnd::FrameFromPoint

Belirtilen noktayı içeren mini çerçeve penceresini bulur.

```
static CPaneFrameWnd* __stdcall FrameFromPoint(
    CPoint pt,
    int nSensitivity,
    CPaneFrameWnd* pFrameToExclude = NULL,
    BOOL bFloatMultiOnly = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
[içinde] Nokta, ekran koordinatlarında.

*nDuyarlılık*<br/>
[içinde] Mini çerçeve penceresinin arama alanını bu boyuta göre artırın. Verilen nokta artan alana düşerse, mini çerçeve penceresi arama ölçütlerini karşılar.

*pFrameToExclude*<br/>
[içinde] Aramadan hariç tutmak için bir mini çerçeve penceresi belirtir.

*bFloatMultiOnly*<br/>
[içinde] TRUE ise, yalnızca CBRS_FLOAT_MULTI stiline sahip mini çerçeve li pencereleri arayın. FALSE ise, tüm mini çerçeve pencereleri arayın.

### <a name="return-value"></a>Dönüş Değeri

*Pt*içeren mini çerçeve penceresiiçin bir işaretçi; aksi takdirde NULL.

## <a name="cpaneframewndgetcaptionheight"></a><a name="getcaptionheight"></a>CPaneFrameWnd::GetCaptionHeight

Mini çerçeve pencere başlığının yüksekliğini döndürür.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresinin piksel yüksekliği.

### <a name="remarks"></a>Açıklamalar

Mini çerçeve penceresinin yüksekliğini belirlemek için bu yöntemi arayın. Varsayılan olarak, yükseklik SM_CYSMCAPTION olarak ayarlanır. Daha fazla bilgi için [GetSystemMetrics Fonksiyonu'na](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)bakın.

## <a name="cpaneframewndgetcaptionrect"></a><a name="getcaptionrect"></a>CPaneFrameWnd::GetCaptionRect

Mini çerçeve pencere başlığının sınırlayıcı dikdörtgenini hesaplar.

```
virtual void GetCaptionRect(CRect& rectCaption) const;
```

### <a name="parameters"></a>Parametreler

*rektCaption*<br/>
[çıkış] Ekran koordinatlarında mini çerçeve pencere başlığının boyutunu ve konumunu içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir mini çerçeve pencere başlığının sınırlayıcı dikdörtgenini hesaplamak için çerçeve tarafından çağrılır.

## <a name="cpaneframewndgetcaptiontext"></a><a name="getcaptiontext"></a>CPaneFrameWnd::GetCaptionText

Resim yazısı metnini döndürür.

```
virtual CString GetCaptionText();
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresinin resim yazısı metni.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, resim yazısı metnini görüntülediğinde çerçeve tarafından çağrılır.

## <a name="cpaneframewndgetdockingmanager"></a><a name="getdockingmanager"></a>CPaneFrameWnd::GetDockingManager

```
CDockingManager* GetDockingManager() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndgetdockingmode"></a><a name="getdockingmode"></a>CPaneFrameWnd::GetDockingMode

Yerleştirme modunu döndürür.

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme modu. Aşağıdaki değerlerden biri:

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

## <a name="cpaneframewndgetfirstvisiblepane"></a><a name="getfirstvisiblepane"></a>CPaneFrameWnd::GetFirstVisiblePane

Mini çerçeve penceresinde bulunan ilk görünür bölmeyi döndürür.

```
virtual CWnd* GetFirstVisiblePane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresindeki ilk bölme veya mini çerçeve penceresi bölme leri yoksa NULL.

## <a name="cpaneframewndgethotpoint"></a><a name="gethotpoint"></a>CPaneFrameWnd::GetHotPoint

```
CPoint GetHotPoint() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndgetpane"></a><a name="getpane"></a>CPaneFrameWnd::GetPane

Mini çerçeve penceresinde bulunan bir bölmeyi döndürür.

```
virtual CWnd* GetPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçevede bulunan bölme veya mini çerçeve penceresi bölme leri yoksa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndgetpanecount"></a><a name="getpanecount"></a>CPaneFrameWnd::GetPaneCount

Mini çerçeve penceresinde bulunan bölme sayısını verir.

```
virtual int GetPaneCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresindeki bölme sayısı. Bu değer sıfır olabilir.

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndgetparent"></a><a name="getparent"></a>CPaneFrameWnd::GetParent

```
CWnd* GetParent();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndgetpinstate"></a><a name="getpinstate"></a>CPaneFrameWnd::GetPinState

```
BOOL GetPinState() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndgetrecentfloatingrect"></a><a name="getrecentfloatingrect"></a>CPaneFrameWnd::GetRecentFloatingRect

```
CRect GetRecentFloatingRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndgetvisiblepanecount"></a><a name="getvisiblepanecount"></a>CPaneFrameWnd::GetVisiblePaneCount

Mini çerçeve penceresinde bulunan görünür bölme sayısını döndürür.

```
virtual int GetVisiblePaneCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Görünür bölmelerin sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndhittest"></a><a name="hittest"></a>CPaneFrameWnd::HitTest

Belirli bir noktada mini çerçeve penceresinin hangi bölümünün olduğunu belirler.

```
virtual LRESULT HitTest(
    CPoint point,
    BOOL bDetectCaption);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
[içinde] Test etmek için nokta.

*bDetectCaption*<br/>
[içinde] TRUE ise, başlığın karşısındaki noktayı işaretleyin. FALSE ise, başlık yoksay.

### <a name="return-value"></a>Dönüş Değeri

Aşağıdaki değerlerden biri:

|Değer|Anlamı|
|-----------|-------------|
|HTNOWHERE|Nokta mini çerçeve penceresinin dışındadır.|
|HTCLIENT|Amaç istemci alanında.|
|HTCAPTION|Önemli olan başlıkta.|
|HTTOP|Önemli olan en üstte.|
|HTTOPLEFT|Nokta sol üstte.|
|HTTOPRIGHT|Nokta sağ üstte.|
|HTLEFT|Nokta solda.|
|HTRIGHT|Önemli olan sağda.|
|HTBOTTOM|Mesele en altta.|
|HTBOTTOMLEFT|Nokta sol altta.|
|HTBOTTOMRIGHT|Nokta sağ altta.|

## <a name="cpaneframewndiscaptured"></a><a name="iscaptured"></a>CPaneFrameWnd::Yakalanır

```
BOOL IsCaptured() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndisdelayshow"></a><a name="isdelayshow"></a>CPaneFrameWnd::IsDelayShow

```
BOOL IsDelayShow() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndisrolldown"></a><a name="isrolldown"></a>CPaneFrameWnd::IsRollDown

Mini çerçeve penceresinin aşağı yayılıp yuvarlanmaması gerektiğini belirler.

```
virtual BOOL IsRollDown() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresi aşağı yuvarlanmış olmalıdır doğru; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir mini çerçeve penceresi aşağı haddelenmiş olup olmadığını belirlemek için çerçeve tarafından çağrılır. AFX_CBRS_AUTO_ROLLUP bayrağı olan en az bir bölme içeriyorsa, bir mini çerçeve penceresi için rollup/rolldown özelliği etkinleştirilir. Bölme oluşturulduğunda bu bayrak ayarlanır. Daha fazla bilgi için [Bkz. CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

Varsayılan olarak, çerçeve, pencerenin aşağı yaslanması gerekip gerekmediğini belirlemek için fare işaretçisinin mini çerçeve pencere sınırlayıcı dikdörtgeninin içinde olup olmadığını denetler. Türemiş bir sınıfta bu davranışı geçersiz kılabilirsiniz.

## <a name="cpaneframewndisrollup"></a><a name="isrollup"></a>CPaneFrameWnd::IsRollUp

Mini çerçeve penceresinin yuvarlanıp yuvarlanmaması gerektiğini belirler.

```
virtual BOOL IsRollUp() const;
```

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresi nin yuvarlanması gerekiyorsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir mini çerçeve penceresi nin yuvarlanması gerekip gerekmediğini belirlemek için çerçeve tarafından çağrılır. AFX_CBRS_AUTO_ROLLUP bayrağı olan en az bir bölme içeriyorsa, bir mini çerçeve penceresi için rollup/rolldown özelliği etkinleştirilir. Bölme oluşturulduğunda bu bayrak ayarlanır. Daha fazla bilgi için [Bkz. CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).

Varsayılan olarak, çerçeve, pencerenin yukarı yuvarlanması gerekip gerekmediğini belirlemek için fare işaretçisinin mini çerçeve pencere sınırlayıcı dikdörtgeninin içinde olup olmadığını denetler. Türemiş bir sınıfta bu davranışı geçersiz kılabilirsiniz.

## <a name="cpaneframewndkilldockingtimer"></a><a name="killdockingtimer"></a>CPaneFrameWnd::KillDockingTimer

Yerleştirme zamanlayıcısını durdurur.

```
void KillDockingTimer();
```

## <a name="cpaneframewndloadstate"></a><a name="loadstate"></a>CPaneFrameWnd::LoadState

Bölmenin durumunu kayıt defterinden yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Profil adı.

*uiID*<br/>
[içinde] Bölme kimliği.

### <a name="return-value"></a>Dönüş Değeri

Bölme durumu başarıyla yüklenmişse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cpaneframewndm_busesavebits"></a><a name="m_busesavebits"></a>CPaneFrameWnd::m_bUseSaveBits

CS_SAVEBITS sınıf stiline sahip pencere sınıfının kaydedilip kaydedilemeyeceğini belirtir.

```
AFX_IMPORT_DATA static BOOL m_bUseSaveBits;
```

### <a name="remarks"></a>Açıklamalar

Bu statik üyeyi, CS_SAVEBITS stiline sahip mini çerçeve pencere sınıfını kaydetmek için TRUE olarak ayarlayın. Bu, kullanıcı mini çerçeve penceresini sürüklediğinde titremeyi azaltmaya yardımcı olabilir.

## <a name="cpaneframewndonbeforedock"></a><a name="onbeforedock"></a>CPaneFrameWnd::OnBeforeDock

Yerleştirmenin mümkün olup olmadığını belirler.

```
virtual BOOL OnBeforeDock();
```

### <a name="return-value"></a>Dönüş Değeri

Yerleştirme mümkünse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cpaneframewndoncheckrollstate"></a><a name="oncheckrollstate"></a>CPaneFrameWnd::OnCheckRollState

Mini çerçeve penceresinin yukarı mı yoksa aşağı mı yuvarlanması gerektiğini belirler.

```
virtual void OnCheckRollState();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir mini çerçeve penceresi yukarı veya aşağı haddelenmiş olması gerektiğini belirlemek için çerçeve tarafından çağrılır.

Varsayılan olarak, çerçeve [CPaneFrameWnd çağırır::IsRollUp](#isrollup) ve [CPaneFrameWnd::IsRollDown](#isrolldown) ve sadece uzanır veya mini çerçeve penceresi geri yükler. Farklı bir görsel efekt kullanmak için türetilmiş bir sınıfta bu yöntemi geçersiz kılabilirsiniz.

## <a name="cpaneframewndondocktorecentpos"></a><a name="ondocktorecentpos"></a>CPaneFrameWnd::OnDockToRecentPos

Mini çerçeve penceresini en son konumunda sabitler.

```
virtual void OnDockToRecentPos();
```

## <a name="cpaneframewndondrawborder"></a><a name="ondrawborder"></a>CPaneFrameWnd::OnDrawBorder

Mini çerçeve penceresinin kenarlıklarını çizer.

```
virtual void OnDrawBorder(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Kenarlığı çizmek için kullanılan aygıt bağlamı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, mini çerçeve penceresinin kenarlıklarını çizmek için çerçeve tarafından çağrılır.

## <a name="cpaneframewndonkillrolluptimer"></a><a name="onkillrolluptimer"></a>CPaneFrameWnd::OnKillRollUpTimer

Toplama zamanlayıcısını durdurur.

```
virtual void OnKillRollUpTimer();
```

## <a name="cpaneframewndonmovepane"></a><a name="onmovepane"></a>CPaneFrameWnd::OnMovePane

Mini çerçeve penceresini belirli bir ofset ile taşır.

```
virtual void OnMovePane(
    CPane* pBar,
    CPoint ptOffset);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Bölmeye işaretçi (yoksayılır).

*ptOffset*<br/>
[içinde] Bölmeyi hareket ettirecek ofset.

## <a name="cpaneframewndonpanerecalclayout"></a><a name="onpanerecalclayout"></a>CPaneFrameWnd::OnPaneRecalcLayout

Mini çerçeve penceresi içindeki bölmenin düzenini ayarlar.

```
virtual void OnPaneRecalcLayout();
```

### <a name="remarks"></a>Açıklamalar

Çerçeve, mini çerçeve penceresi içindeki bölmenin düzenini ayarlaması gerektiğinde bu yöntemi çağırır.

Varsayılan olarak, bölme mini çerçeve penceresinin tam istemci alanını kapsayacak şekilde konumlandırılır.

## <a name="cpaneframewndonsetrolluptimer"></a><a name="onsetrolluptimer"></a>CPaneFrameWnd::OnSetRollTimer

Toplama zamanlayıcısını ayarlar.

```
virtual void OnSetRollUpTimer();
```

## <a name="cpaneframewndonshowpane"></a><a name="onshowpane"></a>CPaneFrameWnd::OnShowPane

Mini çerçeve penceresindeki bir bölme gizlendiğinde veya görüntülendiğinde çerçeve tarafından çağrılır.

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde] Gösterilen veya gizlenen bölme.

*bGöster*<br/>
[içinde] Bölme gösteriliyorsa DOĞRU; Bölme gizleniyorsa YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Mini çerçeve penceresindeki bir bölme gösterildiğinde veya gizlendiğinde çerçeve tarafından çağrılır. Varsayılan uygulama hiçbir şey yapmaz.

## <a name="cpaneframewndpin"></a><a name="pin"></a>CPaneFrameWnd::Pin

```
void Pin(BOOL bPin = TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde] *bPin*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndpanefrompoint"></a><a name="panefrompoint"></a>CPaneFrameWnd::PaneFromPoint

Bir mini çerçeve penceresi içinde kullanıcı tarafından sağlanan bir nokta içeriyorsa bir bölme döndürür.

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    BOOL bCheckVisibility);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
[içinde] Kullanıcının ekran koordinatlarında tıklatdığı nokta.

*nDuyarlılık*<br/>
[içinde] Bu parametre kullanılmaz.

*bCheckGörünürlük*<br/>
[içinde] Yalnızca görünür bölmelerin döndürülmesi gerektiğini belirtmek için TRUE; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcının tıklatdığı bölme veya o konumda bölme yoksa NULL.

### <a name="remarks"></a>Açıklamalar

Verilen noktayı içeren bir bölme elde etmek için bu yöntemi arayın.

## <a name="cpaneframewndredrawall"></a><a name="redrawall"></a>CPaneFrameWnd::RedrawAll

Tüm mini çerçeve pencereleri yeniden çizer.

```
static void RedrawAll();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, CWnd'yi arayarak tüm mini çerçeve pencerelerini [güncelleştirir::Her](../../mfc/reference/cwnd-class.md#redrawwindow) pencere için Yeniden Çizim Penceresi.

## <a name="cpaneframewndremovenonvalidpanes"></a><a name="removenonvalidpanes"></a>CPaneFrameWnd::RemoveNonValidPanes

Geçerli olmayan bölmeleri kaldırmak için çerçeve tarafından çağrılır.

```
virtual void RemoveNonValidPanes();
```

## <a name="cpaneframewndremovepane"></a><a name="removepane"></a>CPaneFrameWnd::RemovePane

Küçük çerçeve penceresinden bir bölme kaldırır.

```
virtual void RemovePane(
    CBasePane* pWnd,
    BOOL bDestroy = FALSE,
    BOOL bNoDelayedDestroy = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
[içinde] Kaldırmak için bölmeye bir işaretçi.

*bYok et*<br/>
[içinde] Mini çerçeve penceresine ne olacağını belirtir. *bDestroy* TRUE ise, bu yöntem mini çerçeve penceresini hemen yok eder. FALSE ise, bu yöntem belirli bir gecikmeden sonra mini çerçeve penceresini yok eder.

*bNoDelayedDestroy*<br/>
[içinde] DOĞRUise, gecikmiş imha devre dışı bırakılır. FALSE ise, gecikmiş imha etkindir.

### <a name="remarks"></a>Açıklamalar

Çerçeve, mini çerçeve pencerelerini hemen veya belirli bir gecikmeden sonra yok edebilir. Mini çerçeveli pencerelerin imhasını geciktirmek istiyorsanız, *bNoDelayedDestroy* parametresinde FALSE'u geçirin. Çerçeve AFX_WM_CHECKEMPTYMINIFRAME iletiyi işlerken gecikmeli imha oluşur.

## <a name="cpaneframewndreplacepane"></a><a name="replacepane"></a>CPaneFrameWnd::ReplacePane

Bir bölmeyi diğeriyle değiştirir.

```
virtual void ReplacePane(
    CBasePane* pBarOrg,
    CBasePane* pBarReplaceWith);
```

### <a name="parameters"></a>Parametreler

*pBarOrg*<br/>
[içinde] Özgün bölmeye işaretçi.

*pBarReplaceWith*<br/>
[içinde] Özgün bölmenin yerini alan bölmeye işaretçi.

## <a name="cpaneframewndsavestate"></a><a name="savestate"></a>CPaneFrameWnd::SaveState

Bölmenin durumunu kayıt defterine kaydeder.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Profil adı.

*uiID*<br/>
[içinde] Bölme kimliği.

### <a name="return-value"></a>Dönüş Değeri

Bölme durumu başarıyla kaydedildiyse DOĞRU; aksi takdirde YANLIŞ.

## <a name="cpaneframewndsetcaptionbuttons"></a><a name="setcaptionbuttons"></a>CPaneFrameWnd::SetCaptionButtons

Resim yazısı düğmelerini ayarlar.

```
virtual void SetCaptionButtons(DWORD dwButtons);
```

### <a name="parameters"></a>Parametreler

*dwDüğmeler*<br/>
[içinde] Aşağıdaki değerlerin Bitwise-OR kombinasyonu:

- AFX_CAPTION_BTN_CLOSE

- AFX_CAPTION_BTN_PIN

- AFX_CAPTION_BTN_MENU

- AFX_CAPTION_BTN_CUSTOMIZE

## <a name="cpaneframewndsetdelayshow"></a><a name="setdelayshow"></a>CPaneFrameWnd::SetDelayShow

```
void SetDelayShow(BOOL bDelayShow);
```

### <a name="parameters"></a>Parametreler

[içinde] *bDelayShow*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndsetdockingmanager"></a><a name="setdockingmanager"></a>CPaneFrameWnd::SetDockingManager

```
void SetDockingManager(CDockingManager* pManager);
```

### <a name="parameters"></a>Parametreler

[içinde] *pManager*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndsetdockingtimer"></a><a name="setdockingtimer"></a>CPaneFrameWnd::SetDockingTimer

Yerleştirme zamanlayıcısını ayarlar.

```
void SetDockingTimer(UINT nTimeOut);
```

### <a name="parameters"></a>Parametreler

*nTimeOut*<br/>
[içinde] Milisaniye cinsinden zaman çıkış değeri.

## <a name="cpaneframewndsetdockstate"></a><a name="setdockstate"></a>CPaneFrameWnd::SetDockState

Kenetlenme durumunu ayarlar.

```
virtual void SetDockState(CDockingManager* pDockManager);
```

### <a name="parameters"></a>Parametreler

*pDockManager*<br/>
[içinde] Yerleştirme yöneticisine bir işaretçi.

## <a name="cpaneframewndsethotpoint"></a><a name="sethotpoint"></a>CPaneFrameWnd::SetHotPoint

```
void SetHotPoint(CPoint& ptNew);
```

### <a name="parameters"></a>Parametreler

[içinde] *ptNew*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndsetpredockstate"></a><a name="setpredockstate"></a>CPaneFrameWnd::SetPreDockState

Predocking durumunu ayarlamak için çerçeve tarafından çağrıldı.

```
virtual BOOL SetPreDockState(
    AFX_PREDOCK_STATE preDockState,
    CBasePane* pBarToDock = NULL,
    AFX_DOCK_METHOD dockMethod = DM_MOUSE);
```

### <a name="parameters"></a>Parametreler

*önDockState*<br/>
[içinde] Olası değerler:

- PDS_NOTHING,

- PDS_DOCK_REGULAR,

- PDS_DOCK_TO_TAB

*pBarToDock*<br/>
[içinde] Bölmeye dock için bir işaretçi.

*dockMethod*<br/>
[içinde] Yerleştirme yöntemi. (Bu parametre yoksayılır.)

### <a name="return-value"></a>Dönüş Değeri

Mini çerçeve penceresi çözülmemişse DOĞRU; Kenetlenirse YANLIŞ.

## <a name="cpaneframewndsizetocontent"></a><a name="sizetocontent"></a>CPaneFrameWnd::SizeToContent

Mini çerçeve penceresinin boyutunu, içerdiği bölmeye eşdeğer olacak şekilde ayarlar.

```
virtual void SizeToContent();
```

### <a name="remarks"></a>Açıklamalar

Mini çerçeve penceresinin boyutunu bulunan bölmenin boyutuna ayarlamak için bu yöntemi arayın.

## <a name="cpaneframewndstarttearoff"></a><a name="starttearoff"></a>CPaneFrameWnd::StartTearOff

Menüden gözyaşları.

```
BOOL StartTearOff(CMFCPopu* pMenu);
```

### <a name="parameters"></a>Parametreler

*pMenü*<br/>
[içinde] Menüye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cpaneframewndstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CPaneFrameWnd::StoreRecentDockSiteInfo

```
virtual void StoreRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpaneframewndstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CPaneFrameWnd::StoreRecentTabRelatedInfo

```
virtual void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDockingBar*<br/>
[içinde] *pTabbedBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)
