---
title: CPaneDivider Sınıf
ms.date: 11/04/2016
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
helpviewer_keywords:
- CPaneDivider [MFC], CPaneDivider
- CPaneDivider [MFC], AddPaneContainer
- CPaneDivider [MFC], AddPane
- CPaneDivider [MFC], AddRecentPane
- CPaneDivider [MFC], CalcExpectedDockedRect
- CPaneDivider [MFC], CalcFixedLayout
- CPaneDivider [MFC], CheckVisibility
- CPaneDivider [MFC], CreateEx
- CPaneDivider [MFC], DoesAllowDynInsertBefore
- CPaneDivider [MFC], DoesContainFloatingPane
- CPaneDivider [MFC], FindPaneContainer
- CPaneDivider [MFC], FindTabbedPane
- CPaneDivider [MFC], GetDefaultWidth
- CPaneDivider [MFC], GetFirstPane
- CPaneDivider [MFC], GetPaneDividerStyle
- CPaneDivider [MFC], GetRootContainerRect
- CPaneDivider [MFC], GetWidth
- CPaneDivider [MFC], Init
- CPaneDivider [MFC], InsertPane
- CPaneDivider [MFC], IsAutoHideMode
- CPaneDivider [MFC], IsDefault
- CPaneDivider [MFC], IsHorizontal
- CPaneDivider [MFC], Move
- CPaneDivider [MFC], NotifyAboutRelease
- CPaneDivider [MFC], OnShowPane
- CPaneDivider [MFC], ReleaseEmptyPaneContainers
- CPaneDivider [MFC], RemovePane
- CPaneDivider [MFC], ReplacePane
- CPaneDivider [MFC], RepositionPanes
- CPaneDivider [MFC], Serialize
- CPaneDivider [MFC], SetAutoHideMode
- CPaneDivider [MFC], SetPaneContainerManager
- CPaneDivider [MFC], ShowWindow
- CPaneDivider [MFC], StoreRecentDockSiteInfo
- CPaneDivider [MFC], StoreRecentTabRelatedInfo
- CPaneDivider [MFC], GetPanes
- CPaneDivider [MFC], GetPaneDividers
- CPaneDivider [MFC], m_nDefaultWidth
- CPaneDivider [MFC], m_pSliderRTC
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
ms.openlocfilehash: 41fa3204712749a3b1123a20d31b01ba8b5fbaa4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364114"
---
# <a name="cpanedivider-class"></a>CPaneDivider Sınıf

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

Sınıf `CPaneDivider` iki bölmeyi böler, iki bölme grubunu böler veya bir bölme grubunu ana çerçeve penceresinin istemci alanından ayırır.

## <a name="syntax"></a>Sözdizimi

```
class CPaneDivider : public CBasePane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CPaneDivider::CPaneBölücü](#cpanedivider)||

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||
|[CPaneDivider::AddPane](#addpane)||
|[CPaneDivider::AddRecentPane](#addrecentpane)||
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|[(Overrides CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CPaneDivider::CheckVisibility](#checkvisibility)||
|[CPaneDivider::CreateEx](#createex)|[(CBasePane geçersiz kılar::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|[(Overrides CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||
|[CPaneDivider::GetFirstPane](#getfirstpane)||
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||
|[CPaneDivider::GetWidth](#getwidth)||
|[CPaneDivider::Init](#init)||
|[CPaneDivider::InsertPane](#insertpane)||
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(Geçersiz kılar [CBasePane::IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode).)|
|[CPaneDivider::Varsayılan](#isdefault)||
|[CPaneDivider::Yatay](#ishorizontal)|(Geçersiz Kılar [CBasePane::IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal).)|
|[CPaneDivider::Taşı](#move)||
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||
|[CPaneDivider::OnShowPane](#onshowpane)||
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||
|[CPaneDivider::RemovePane](#removepane)||
|[CPaneDivider::ReplacePane](#replacepane)||
|[CPaneDivider::RepositionPanes](#repositionpanes)||
|[CPaneDivider::Serialize](#serialize)|(Geçersiz `CBasePane::Serialize`kılar .)|
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||
|[CPaneDivider::ShowWindow](#showwindow)||
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPaneDivider::GetPanes](#getpanes)|[CPaneContainer Sınıfında](../../mfc/reference/cpanecontainer-class.md)bulunan bölmelerin listesini verir. Bu yöntem yalnızca varsayılan bölme bölücüler için çağrılmalıdır.|
|[CPaneDivider::GetPaneBölücüler](#getpanedividers)|[CPaneContainer Sınıfında](../../mfc/reference/cpanecontainer-class.md)bulunan bölme bölücülerinin listesini verir. Bu yöntem yalnızca varsayılan bölme bölücüler için çağrılmalıdır.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPaneBölücü::m_nDefaultWidth](#m_ndefaultwidth)|Uygulamadaki tüm bölme bölücülerinin piksellerinde varsayılan genişliği belirtir.|
|[CPaneBölücü::m_pSliderRTC](#m_psliderrtc)|Türetilmiş bir nesne hakkında çalışma `CPaneDivider`zamanı sınıf bilgileriiçin bir işaretçi tutar.|

## <a name="remarks"></a>Açıklamalar

Çerçeve, bölme `CPaneDivider` sabitlendiğinde nesneleri otomatik olarak oluşturur.

Bölme bölücüleri iki türü vardır:

- bir bölme grubu ana çerçeve penceresinin bir tarafına sabitlendiğinde varsayılan bölme bölücü oluşturulur. Varsayılan bölme [bölücücpanContainerManager Sınıfı](../../mfc/reference/cpanecontainermanager-class.md) için bir işaretçi tutar ve bölmeleri grubunda (bölmeyeniden boyutlandırma veya başka bir bölme veya kapsayıcı yerleştirme gibi) çoğu işlemleri terslime gibi kapsayıcı yöneticisine yönlendirir. Her yerleştirme bölmesi varsayılan bölme bölücü için bir işaretçi tutar.

- Normal bir bölme bölücü sadece bir kapta iki bölmeleri böler. Daha fazla bilgi için [CPaneContainer Class'a](../../mfc/reference/cpanecontainer-class.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CPaneDivider` nesnenin bir `CWorkspaceBar` nesneden nasıl alınabildiğini gösterir. Bu kod snippet [MDI Sekmeler Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)\
•&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CPaneDivider](../../mfc/reference/cpanedivider-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxPaneDivider.h

## <a name="cpanedividersetautohidemode"></a><a name="setautohidemode"></a>CPaneDivider::SetAutoHideMode

```
void SetAutoHideMode(BOOL bMode);
```

### <a name="parameters"></a>Parametreler

[içinde] *bMode*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividersetpanecontainermanager"></a><a name="setpanecontainermanager"></a>CPaneDivider::SetPaneContainerManager

```
void SetPaneContainerManager(CPaneContainerManager* p);
```

### <a name="parameters"></a>Parametreler

[içinde] *p*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedivideraddpane"></a><a name="addpane"></a>CPaneDivider::AddPane

```
virtual void AddPane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedivideraddpanecontainer"></a><a name="addpanecontainer"></a>CPaneDivider::AddPaneContainer

```
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,
    BOOL bOuterEdge);

virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,
    CPaneContainerManager& barContainerManager,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

[içinde] *barContainerManager*<br/>
[içinde] *bOuterEdge*<br/>
[içinde] *pTargetBar*<br/>
[içinde] *dwHizalama*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedivideraddrecentpane"></a><a name="addrecentpane"></a>CPaneDivider::AddRecentPane

```
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CPaneDivider::CalcExpectedDockedRect

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pWndToDock*<br/>
[içinde] *ptMouse*<br/>
[içinde] *rektResult*<br/>
[içinde] *bDrawTab*<br/>
[içinde] *ppTargetBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercalcfixedlayout"></a><a name="calcfixedlayout"></a>CPaneDivider::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

[içinde] *bStretch*<br/>
[içinde] *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercheckvisibility"></a><a name="checkvisibility"></a>CPaneDivider::CheckVisibility

```
virtual BOOL CheckVisibility();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercpanedivider"></a><a name="cpanedivider"></a>CPaneDivider::CPaneBölücü

```
CPaneDivider();

CPaneDivider(
    BOOL bDefaultSlider,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>Parametreler

[içinde] *bDefaultSlider*<br/>
[içinde] *pParent*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercreateex"></a><a name="createex"></a>CPaneDivider::CreateEx

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Parametreler

[içinde] *dwStyleEx*<br/>
[içinde] *dwStyle*<br/>
[içinde] *rekt*<br/>
[içinde] *pParentWnd*<br/>
[içinde] *nID*<br/>
[içinde] *pContext*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerdoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CPaneDivider::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerdoescontainfloatingpane"></a><a name="doescontainfloatingpane"></a>CPaneDivider::DoesContainFloatingPane

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerfindpanecontainer"></a><a name="findpanecontainer"></a>CPaneDivider::FindPaneContainer

```
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>
[içinde] *bLeftBar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerfindtabbedpane"></a><a name="findtabbedpane"></a>CPaneDivider::FindTabbedPane

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>Parametreler

[içinde] *nID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetdefaultwidth"></a><a name="getdefaultwidth"></a>CPaneDivider::GetDefaultWidth

```
static int __stdcall GetDefaultWidth();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetfirstpane"></a><a name="getfirstpane"></a>CPaneDivider::GetFirstPane

```
const CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetpanedividers"></a><a name="getpanedividers"></a>CPaneDivider::GetPaneBölücüler

[CPaneContainer Sınıfında](../../mfc/reference/cpanecontainer-class.md)bulunan bölme bölücülerinin listesini verir. Bu yöntem yalnızca varsayılan bölme bölücüler için çağrılmalıdır.

```
void GetPaneDividers(CObList& lstSliders);
```

### <a name="parameters"></a>Parametreler

*lstSliders*<br/>
[çıkış] Bölme kapsayıcısında bulunan bölme bölücülerinin listesini içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca varsayılan bölme bölücüleri için çağrılmalıdır. Varsayılan bölme bölücü, bölme kapsayıcısının tamamını yeniden boyutlandıran bir bölücüdür.

## <a name="cpanedividergetpanedividerstyle"></a><a name="getpanedividerstyle"></a>CPaneDivider::GetPaneDividerStyle

```
DWORD GetPaneDividerStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetpanes"></a><a name="getpanes"></a>CPaneDivider::GetPanes

[CPaneContainer Sınıfında](../../mfc/reference/cpanecontainer-class.md)bulunan bölmelerin listesini verir. Bu yöntem yalnızca varsayılan bölme bölücüleri almak için çağrılmalıdır.

```
void GetPanes(CObList& lstBars);
```

### <a name="parameters"></a>Parametreler

*lstBars*<br/>
[çıkış] Bölme kapsayıcısında bulunan bölmelerin listesini içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca varsayılan bölme bölücüleri için çağrılmalıdır. Varsayılan bölme bölücü, bölme kapsayıcısının tamamını yeniden boyutlandıran bir bölücüdür.

## <a name="cpanedividergetrootcontainerrect"></a><a name="getrootcontainerrect"></a>CPaneDivider::GetRootContainerRect

```
CRect GetRootContainerRect();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetwidth"></a><a name="getwidth"></a>CPaneDivider::GetWidth

```
int GetWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerinit"></a><a name="init"></a>CPaneDivider::Init

```
void Init(
    BOOL bDefaultSlider = FALSE,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>Parametreler

[içinde] *bDefaultSlider*<br/>
[içinde] *pParent*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerinsertpane"></a><a name="insertpane"></a>CPaneDivider::InsertPane

```
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,
    CDockablePane* pTargetBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBarToInsert*<br/>
[içinde] *pTargetBar*<br/>
[içinde] *dwHizalama*<br/>
[içinde] *lpRect*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerisautohidemode"></a><a name="isautohidemode"></a>CPaneDivider::IsAutoHideMode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerisdefault"></a><a name="isdefault"></a>CPaneDivider::Varsayılan

```
BOOL IsDefault() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerishorizontal"></a><a name="ishorizontal"></a>CPaneDivider::Yatay

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerm_ndefaultwidth"></a><a name="m_ndefaultwidth"></a>CPaneBölücü::m_nDefaultWidth

Uygulamadaki tüm bölme bölücülerinin pikselolarak varsayılan genişliğini belirtir.

```
AFX_IMPORT_DATA static int m_nDefaultWidth;
```

## <a name="cpanedividermove"></a><a name="move"></a>CPaneDivider::Taşı

```
virtual void Move(
    CPoint& ptOffset,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Parametreler

[içinde] *ptOffset*<br/>
[içinde] *bAdjustLayout*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerm_psliderrtc"></a><a name="m_psliderrtc"></a>CPaneBölücü::m_pSliderRTC

Türetilmiş bir nesne hakkında `CPaneDivider`çalışma zamanı sınıf bilgilerini çalıştırmak için bir işaretçi tutar.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;
```

### <a name="remarks"></a>Açıklamalar

Özel bir bölme bölücü sağlık ettiyseniz bu üye değişkenini ayarlayın. Bu, bölme çizildiğinde bölme bölücünüzü oluşturmayı sağlar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, üye değişkenin `m_pSliderRTC` nasıl ayarlandığını gösterir:

```
class CMySplitter : public CPaneDivider
{
...
};

CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```

## <a name="cpanedividernotifyaboutrelease"></a><a name="notifyaboutrelease"></a>CPaneDivider::NotifyAboutRelease

```
virtual void NotifyAboutRelease();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedivideronshowpane"></a><a name="onshowpane"></a>CPaneDivider::OnShowPane

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>
[içinde] *bGöster*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CPaneDivider::ReleaseEmptyPaneContainers

```
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerremovepane"></a><a name="removepane"></a>CPaneDivider::RemovePane

```
virtual void RemovePane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerreplacepane"></a><a name="replacepane"></a>CPaneDivider::ReplacePane

```
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,
    CDockablePane* pBarToReplaceWith);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBarToReplace*<br/>
[içinde] *pBarToReplaceWith*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerrepositionpanes"></a><a name="repositionpanes"></a>CPaneDivider::RepositionPanes

```
virtual void RepositionPanes(
    CRect& rectNew,
    HDWP& hdwp);
```

### <a name="parameters"></a>Parametreler

[içinde] *rectYeni*<br/>
[içinde] *hdwp*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerserialize"></a><a name="serialize"></a>CPaneDivider::Serialize

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

[içinde] *ar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividershowwindow"></a><a name="showwindow"></a>CPaneDivider::ShowWindow

```
void ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Parametreler

[içinde] *nCmdShow*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a>CPaneDivider::StoreRecentDockSiteInfo

```
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a>CPaneDivider::StoreRecentTabRelatedInfo

```
void StoreRecentTabRelatedInfo(
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
[CPaneContainerManager Sınıfı](../../mfc/reference/cpanecontainermanager-class.md)<br/>
[CPaneContainer Sınıfı](../../mfc/reference/cpanecontainer-class.md)<br/>
[CDockingManager Sınıfı](../../mfc/reference/cdockingmanager-class.md)<br/>
[CBasePane Sınıfı](../../mfc/reference/cbasepane-class.md)
