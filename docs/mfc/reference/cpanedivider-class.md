---
description: 'Daha fazla bilgi edinin: CPaneDivider sınıfı'
title: CPaneDivider sınıfı
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
ms.openlocfilehash: f2541483f7881ab0b303750e69af776c2c3bc7a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301522"
---
# <a name="cpanedivider-class"></a>CPaneDivider sınıfı

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

`CPaneDivider`Sınıfı iki bölmeyi böler, iki bölme grubunu böler veya bir bölmeler grubunu ana çerçeve penceresinin istemci alanından ayırır.

## <a name="syntax"></a>Syntax

```
class CPaneDivider : public CBasePane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CPaneDivider:: CPaneDivider](#cpanedivider)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPaneDivider:: Addbölmesi kapsayıcısı](#addpanecontainer)||
|[CPaneDivider:: AddPane](#addpane)||
|[CPaneDivider:: AddRecentPane](#addrecentpane)||
|[CPaneDivider:: CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CPaneDivider:: CalcFixedLayout](#calcfixedlayout)|( [CBasePane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).) öğesini geçersiz kılar|
|[CPaneDivider:: CheckVisibility](#checkvisibility)||
|[CPaneDivider:: CreateEx](#createex)|( [CBasePane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex)geçersiz kılar.)|
|[CPaneDivider::D Oesallowdynınsertbefore](#doesallowdyninsertbefore)|( [CBasePane::D Oesallowdynınsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)geçersiz kılar.)|
|[CPaneDivider::D oesContainFloatingPane](#doescontainfloatingpane)||
|[CPaneDivider:: Findbölmesi kapsayıcısı](#findpanecontainer)||
|[CPaneDivider:: FindTabbedPane](#findtabbedpane)||
|[CPaneDivider:: GetDefaultWidth](#getdefaultwidth)||
|[CPaneDivider:: GetFirstPane](#getfirstpane)||
|[CPaneDivider:: GetPaneDividerStyle](#getpanedividerstyle)||
|[CPaneDivider:: GetRootContainerRect](#getrootcontainerrect)||
|[CPaneDivider:: GetWidth](#getwidth)||
|[CPaneDivider:: Init](#init)||
|[CPaneDivider:: InsertPane](#insertpane)||
|[CPaneDivider:: ısoto Hidemode](#isautohidemode)|( [CBasePane:: ısautosize modunu](../../mfc/reference/cbasepane-class.md#isautohidemode)geçersiz kılar.)|
|[CPaneDivider:: IsDefault](#isdefault)||
|[CPaneDivider:: ısyatay](#ishorizontal)|( [CBasePane:: ısyatay](../../mfc/reference/cbasepane-class.md#ishorizontal)geçersiz kılar.)|
|[CPaneDivider:: Move](#move)||
|[CPaneDivider:: Notifyai yayını](#notifyaboutrelease)||
|[CPaneDivider:: OnShowPane](#onshowpane)||
|[CPaneDivider:: ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||
|[CPaneDivider:: RemovePane](#removepane)||
|[CPaneDivider:: ReplacePane](#replacepane)||
|[CPaneDivider:: Depotionbölmeler](#repositionpanes)||
|[CPaneDivider:: serileştirme](#serialize)|(Geçersiz kılmalar `CBasePane::Serialize` .)|
|[CPaneDivider:: SetAutoHideMode](#setautohidemode)||
|[CPaneDivider:: Setbölmesi Containermanager](#setpanecontainermanager)||
|[CPaneDivider:: ShowWindow](#showwindow)||
|[CPaneDivider:: StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||
|[CPaneDivider:: Storerecenttabrelateınfo](#storerecenttabrelatedinfo)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPaneDivider:: Getbölmeler](#getpanes)|[Cbölmesi kapsayıcı sınıfında](../../mfc/reference/cpanecontainer-class.md)bulunan bölmeler listesini döndürür. Bu yöntem yalnızca varsayılan bölme bölücüleri için çağrılmalıdır.|
|[CPaneDivider:: GetPaneDividers](#getpanedividers)|[CPane kapsayıcı sınıfında](../../mfc/reference/cpanecontainer-class.md)bulunan bölme bölücülerin listesini döndürür. Bu yöntem yalnızca varsayılan bölme bölücüleri için çağrılmalıdır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CPaneDivider:: m_nDefaultWidth](#m_ndefaultwidth)|Uygulamadaki tüm bölme ayırıcıdaki piksel cinsinden varsayılan genişliği belirtir.|
|[CPaneDivider:: m_pSliderRTC](#m_psliderrtc)|, İle türetilmiş bir nesne hakkında çalışma zamanı sınıfı bilgileri için bir işaretçi tutar `CPaneDivider` .|

## <a name="remarks"></a>Açıklamalar

Çerçeve, `CPaneDivider` bir bölme yerleştirildiğinde nesneleri otomatik olarak oluşturur.

İki tür bölme bölücüleri vardır:

- bir bölme grubu, ana çerçeve penceresinin bir tarafına yerleştirildiğinde varsayılan bölme ayırıcıyı oluşturulur. Varsayılan bölme bölücü, [CPane Containermanager sınıfına](../../mfc/reference/cpanecontainermanager-class.md) yönelik bir işaretçi tutar ve bölmeler grubuna (bir bölmeyi yeniden boyutlandırma veya başka bir bölme ya da kapsayıcı yerleştirme gibi) kapsayıcı yöneticisine yeniden yönlendirir. Her takma bölmesi, varsayılan bölme ayraca bir işaretçi tutar.

- Normal bölme bölücü yalnızca bir kapsayıcıdaki iki bölmeyi böler. Daha fazla bilgi için bkz. [Cbölmesi kapsayıcı sınıfı](../../mfc/reference/cpanecontainer-class.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, nesnesinden bir nesnenin nasıl alınacağını gösterir `CPaneDivider` `CWorkspaceBar` . Bu kod parçacığı, [MDI sekmeleri tanıtım örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)\
└ &nbsp; [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CPaneDivider](../../mfc/reference/cpanedivider-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxPaneDivider. h

## <a name="cpanedividersetautohidemode"></a><a name="setautohidemode"></a> CPaneDivider:: SetAutoHideMode

```cpp
void SetAutoHideMode(BOOL bMode);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bmode*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividersetpanecontainermanager"></a><a name="setpanecontainermanager"></a> CPaneDivider:: Setbölmesi Containermanager

```cpp
void SetPaneContainerManager(CPaneContainerManager* p);
```

### <a name="parameters"></a>Parametreler

'ndaki *p*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedivideraddpane"></a><a name="addpane"></a> CPaneDivider:: AddPane

```
virtual void AddPane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedivideraddpanecontainer"></a><a name="addpanecontainer"></a> CPaneDivider:: Addbölmesi kapsayıcısı

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

'ndaki *Barcontainermanager*<br/>
'ndaki *Bukenar*<br/>
'ndaki *pTargetBar*<br/>
'ndaki *Dwhizalaması*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedivideraddrecentpane"></a><a name="addrecentpane"></a> CPaneDivider:: AddRecentPane

```
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a> CPaneDivider:: CalcExpectedDockedRect

```
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pwndtodock*<br/>
'ndaki *ptMouse*<br/>
'ndaki *rectResult*<br/>
'ndaki *bDrawTab*<br/>
'ndaki *ppTargetBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercalcfixedlayout"></a><a name="calcfixedlayout"></a> CPaneDivider:: CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

'ndaki *Besnetme*<br/>
'ndaki *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercheckvisibility"></a><a name="checkvisibility"></a> CPaneDivider:: CheckVisibility

```
virtual BOOL CheckVisibility();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercpanedivider"></a><a name="cpanedivider"></a> CPaneDivider:: CPaneDivider

```
CPaneDivider();

CPaneDivider(
    BOOL bDefaultSlider,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bdefaultslider*<br/>
'ndaki *pParent*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividercreateex"></a><a name="createex"></a> CPaneDivider:: CreateEx

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

'ndaki *dwStyleEx*<br/>
'ndaki *dwStyle*<br/>
'ndaki *Rect*<br/>
'ndaki *pParentWnd*<br/>
'ndaki *NID*<br/>
'ndaki *pContext*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerdoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CPaneDivider::D Oesallowdynınsertbefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerdoescontainfloatingpane"></a><a name="doescontainfloatingpane"></a> CPaneDivider::D oesContainFloatingPane

```
virtual BOOL DoesContainFloatingPane();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerfindpanecontainer"></a><a name="findpanecontainer"></a> CPaneDivider:: Findbölmesi kapsayıcısı

```
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,
    BOOL& bLeftBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>
'ndaki *Bleftbar*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerfindtabbedpane"></a><a name="findtabbedpane"></a> CPaneDivider:: FindTabbedPane

```
CDockablePane* FindTabbedPane(UINT nID);
```

### <a name="parameters"></a>Parametreler

'ndaki *NID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetdefaultwidth"></a><a name="getdefaultwidth"></a> CPaneDivider:: GetDefaultWidth

```
static int __stdcall GetDefaultWidth();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetfirstpane"></a><a name="getfirstpane"></a> CPaneDivider:: GetFirstPane

```
const CBasePane* GetFirstPane() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetpanedividers"></a><a name="getpanedividers"></a> CPaneDivider:: GetPaneDividers

[CPane kapsayıcı sınıfında](../../mfc/reference/cpanecontainer-class.md)bulunan bölme bölücülerin listesini döndürür. Bu yöntem yalnızca varsayılan bölme bölücüleri için çağrılmalıdır.

```cpp
void GetPaneDividers(CObList& lstSliders);
```

### <a name="parameters"></a>Parametreler

*Lstsürgüler*<br/>
dışı Bölme kapsayıcısında bulunan bölme bölücülerin listesini içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca varsayılan bölme bölücüleri için çağrılmalıdır. Varsayılan bölme ayırıcı, tüm bölme kapsayıcısını yeniden boyutlandıran bir bölümesdir.

## <a name="cpanedividergetpanedividerstyle"></a><a name="getpanedividerstyle"></a> CPaneDivider:: GetPaneDividerStyle

```
DWORD GetPaneDividerStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetpanes"></a><a name="getpanes"></a> CPaneDivider:: Getbölmeler

[Cbölmesi kapsayıcı sınıfında](../../mfc/reference/cpanecontainer-class.md)bulunan bölmeler listesini döndürür. Bu yöntem yalnızca varsayılan bölme bölücüleri almak için çağrılmalıdır.

```cpp
void GetPanes(CObList& lstBars);
```

### <a name="parameters"></a>Parametreler

*Lstbar çubukları*<br/>
dışı Bölme kapsayıcısında bulunan bölmelerin listesini içerir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca varsayılan bölme bölücüleri için çağrılmalıdır. Varsayılan bölme ayırıcı, tüm bölme kapsayıcısını yeniden boyutlandıran bir bölümesdir.

## <a name="cpanedividergetrootcontainerrect"></a><a name="getrootcontainerrect"></a> CPaneDivider:: GetRootContainerRect

```
CRect GetRootContainerRect();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividergetwidth"></a><a name="getwidth"></a> CPaneDivider:: GetWidth

```
int GetWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerinit"></a><a name="init"></a> CPaneDivider:: Init

```cpp
void Init(
    BOOL bDefaultSlider = FALSE,
    CWnd* pParent = NULL);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bdefaultslider*<br/>
'ndaki *pParent*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerinsertpane"></a><a name="insertpane"></a> CPaneDivider:: InsertPane

```
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,
    CDockablePane* pTargetBar,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pbartoınsert*<br/>
'ndaki *pTargetBar*<br/>
'ndaki *Dwhizalaması*<br/>
'ndaki *lpRect*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerisautohidemode"></a><a name="isautohidemode"></a> CPaneDivider:: ısoto Hidemode

```
BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerisdefault"></a><a name="isdefault"></a> CPaneDivider:: IsDefault

```
BOOL IsDefault() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerishorizontal"></a><a name="ishorizontal"></a> CPaneDivider:: ısyatay

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerm_ndefaultwidth"></a><a name="m_ndefaultwidth"></a> CPaneDivider:: m_nDefaultWidth

Uygulamadaki tüm bölme ayırıcıdaki varsayılan genişliği piksel cinsinden belirtir.

```
AFX_IMPORT_DATA static int m_nDefaultWidth;
```

## <a name="cpanedividermove"></a><a name="move"></a> CPaneDivider:: Move

```
virtual void Move(
    CPoint& ptOffset,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Parametreler

'ndaki *ptOffset*<br/>
'ndaki *Roztlayout*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerm_psliderrtc"></a><a name="m_psliderrtc"></a> CPaneDivider:: m_pSliderRTC

İle türetilmiş bir nesne hakkında çalışma zamanı sınıfı bilgilerine yönelik bir işaretçi tutar `CPaneDivider` .

```
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;
```

### <a name="remarks"></a>Açıklamalar

Özel bir bölme etiketi oluşturursanız bu üye değişkenini ayarlayın. Bu, bölme çizildiğinde çerçevenin bölme ayracın oluşturulmasını sağlar.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, üye değişkeninin nasıl ayarlanacağı gösterilmektedir `m_pSliderRTC` :

```
class CMySplitter : public CPaneDivider
{
...
};

CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```

## <a name="cpanedividernotifyaboutrelease"></a><a name="notifyaboutrelease"></a> CPaneDivider:: Notifyai yayını

```
virtual void NotifyAboutRelease();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedivideronshowpane"></a><a name="onshowpane"></a> CPaneDivider:: OnShowPane

```
virtual void OnShowPane(
    CDockablePane* pBar,
    BOOL bShow);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>
'ndaki *bShow*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a> CPaneDivider:: ReleaseEmptyPaneContainers

```cpp
void ReleaseEmptyPaneContainers();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerremovepane"></a><a name="removepane"></a> CPaneDivider:: RemovePane

```
virtual void RemovePane(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerreplacepane"></a><a name="replacepane"></a> CPaneDivider:: ReplacePane

```
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,
    CDockablePane* pBarToReplaceWith);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pbartoreplace*<br/>
'ndaki *Pbartoreplacewith*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerrepositionpanes"></a><a name="repositionpanes"></a> CPaneDivider:: Depotionbölmeler

```
virtual void RepositionPanes(
    CRect& rectNew,
    HDWP& hdwp);
```

### <a name="parameters"></a>Parametreler

'ndaki *Rectyeni*<br/>
'ndaki *hdwp*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerserialize"></a><a name="serialize"></a> CPaneDivider:: serileştirme

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

'ndaki *ar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividershowwindow"></a><a name="showwindow"></a> CPaneDivider:: ShowWindow

```cpp
void ShowWindow(int nCmdShow);
```

### <a name="parameters"></a>Parametreler

'ndaki *nCmdShow*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerstorerecentdocksiteinfo"></a><a name="storerecentdocksiteinfo"></a> CPaneDivider:: StoreRecentDockSiteInfo

```cpp
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cpanedividerstorerecenttabrelatedinfo"></a><a name="storerecenttabrelatedinfo"></a> CPaneDivider:: Storerecenttabrelateınfo

```cpp
void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,
    CDockablePane* pTabbedBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pDockingBar*<br/>
'ndaki *Ptabbedbar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Cbölmesi Containermanager sınıfı](../../mfc/reference/cpanecontainermanager-class.md)<br/>
[Cbölmesi kapsayıcı sınıfı](../../mfc/reference/cpanecontainer-class.md)<br/>
[CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md)<br/>
[CBasePane sınıfı](../../mfc/reference/cbasepane-class.md)
