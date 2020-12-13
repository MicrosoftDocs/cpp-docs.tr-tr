---
description: 'Daha fazla bilgi edinin: CMFCAutoHideBar sınıfı'
title: CMFCAutoHideBar sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
ms.openlocfilehash: d7cea85a71b8390520d1345e12000aa700026269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336598"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar sınıfı

`CMFCAutoHideBar`Sınıfı, otomatik gizleme özelliğini uygulayan özel bir araç çubuğu sınıfıdır.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCAutoHideBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAutoHideBar:: CMFCAutoHideBar](#cmfcautohidebar)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAutoHideBar:: Addadutohidewindow](#addautohidewindow)||
|[CMFCAutoHideBar:: Allowshowonbölmesi menüsü](#allowshowonpanemenu)|(Geçersiz kılmalar `CPane::AllowShowOnPaneMenu` .)|
|[CMFCAutoHideBar:: CalcFixedLayout](#calcfixedlayout)|( [CBasePane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).) öğesini geçersiz kılar|
|[CMFCAutoHideBar:: Create](#create)|Bir denetim çubuğu oluşturur ve bunu [CPane](../../mfc/reference/cpane-class.md) nesnesine ekler. ( [CPane:: Create](../../mfc/reference/cpane-class.md#create)geçersiz kılar.)|
|[CMFCAutoHideBar:: GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar:: GetVisibleCount](#getvisiblecount)||
|[CMFCAutoHideBar:: OnShowControlBarMenu](#onshowcontrolbarmenu)|Özel bir bölme menüsü görüntülenmek üzereyken Framework tarafından çağırılır. ( [CPane:: OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu)geçersiz kılar.)|
|[CMFCAutoHideBar:: Removeoto Hidewindow](#removeautohidewindow)||
|[CMFCAutoHideBar:: SetActiveInGroup](#setactiveingroup)|( [CPane:: SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup)geçersiz kılar.)|
|[CMFCAutoHideBar:: SetRecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar:: Showoto Hidewindow](#showautohidewindow)||
|[CMFCAutoHideBar:: ayarlayıcı bölmesi](#stretchpane)|Bir bölmeyi dikey veya yatay olarak uzatır. ( [CBasePane:: ayarlayıcı bölmesi](../../mfc/reference/cbasepane-class.md#stretchpane)geçersiz kılar.)|
|[CMFCAutoHideBar:: UnSetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar:: UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCAutoHideBar:: m_nShowAHWndDelay](#m_nshowahwnddelay)|Kullanıcının fare imlecini bir [CMFCAutoHideButton sınıfının](../../mfc/reference/cmfcautohidebutton-class.md) üzerine yerleştirdiği ve çerçevenin ilişkili pencereyi gösterdiği andaki zaman gecikmesi.|

## <a name="remarks"></a>Açıklamalar

Kullanıcı bir dock bölmesini otomatik gizleme moduna geçtiğinde, çerçeve otomatik olarak bir `CMFCAutoHideBar` nesne oluşturur. Ayrıca, gerekli [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) ve [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nesnelerini de oluşturur. Her `CAutoHideDockSite` nesne bir birele ilişkilendirilir `CMFCAutoHideButton` .

Sınıfı, bir `CMFCAutoHideBar` `CAutoHideDockSite` kullanıcının faresi bir üzerinde dolaştığında bir görünümünü uygular `CMFCAutoHideButton` . Araç çubuğu WM_MOUSEMOVE bir ileti aldığında `CMFCAutoHideBar` bir Zamanlayıcı başlatır. Zamanlayıcı tamamlandığında, araç çubuğunu bir WM_TIMER olay bildirimi gönderir. Araç çubuğu, fare işaretçisinin, süreölçer başladığında üzerine yerleştirilmiş otomatik gizleme düğmesine yerleştirilmiş olup olmadığını denetleyerek bu olayı işler. Varsa, ekli `CAutoHideDockSite` görüntülenir.

Zamanlayıcı gecikmesi uzunluğunu ayarlayarak kontrol edebilirsiniz `m_nShowAHWndDelay` . Varsayılan değer 400 MS 'dir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `CMFCAutoHideBar` ve metodunu nasıl kullanacağınızı gösterir `GetDockSiteRow` .

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxoto hidebar. h

## <a name="cmfcautohidebaraddautohidewindow"></a><a name="addautohidewindow"></a> CMFCAutoHideBar:: Addadutohidewindow

`CDockablePane`Pencereye otomatik olarak gizlemeyi sağlayan bir pencereye işlevsellik ekler.

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*pAutoHideWnd*<br/>
'ndaki Gizlemek istediğiniz pencere.

*Dwhizalaması*<br/>
'ndaki Uygulama penceresi ile otomatik gizleme düğmesinin hizalamasını belirten bir değer.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

*Dwhizalaması* parametresi, otomatik gizleme düğmesinin uygulamada nerede olduğunu gösterir. Parametresi aşağıdaki değerlerden herhangi biri olabilir:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a> CMFCAutoHideBar:: Allowshowonbölmesi menüsü

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCAutoHideBar:: CalcFixedLayout

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

## <a name="cmfcautohidebarcmfcautohidebar"></a><a name="cmfcautohidebar"></a> CMFCAutoHideBar:: CMFCAutoHideBar

CMFCAutoHideBar nesnesi oluşturur.

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarcreate"></a><a name="create"></a> CMFCAutoHideBar:: Create

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszClassName*<br/>

*dwStyle*<br/>

*Rect*<br/>

*pParentWnd*<br/>

*NID*<br/>

*dwControlBarStyle*<br/>

*pContext*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebargetfirstahwindow"></a><a name="getfirstahwindow"></a> CMFCAutoHideBar:: GetFirstAHWindow

Uygulamadaki ilk otomatik gizleme penceresine bir işaretçi döndürür.

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamadaki ilk otomatik gizleme penceresi veya bir tane yoksa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebargetvisiblecount"></a><a name="getvisiblecount"></a> CMFCAutoHideBar:: GetVisibleCount

Görünür otomatik gizleme düğmelerinin sayısını alır.

```
int GetVisibleCount();
```

### <a name="return-value"></a>Dönüş Değeri

Görünür otomatik gizleme düğmelerinin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarm_nshowahwnddelay"></a><a name="m_nshowahwnddelay"></a> CMFCAutoHideBar:: m_nShowAHWndDelay

Kullanıcının fare imlecini bir [CMFCAutoHideButton sınıfının](../../mfc/reference/cmfcautohidebutton-class.md) üzerine yerleştirdiği ve çerçevenin ilişkili pencereyi gösterdiği andaki zaman gecikmesi.

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı fare imlecini bir üzerine `CMFCAutoHideButton` yerleştirirse, çerçeve ilişkili pencereyi görüntülemeden önce küçük bir gecikme olur. Bu parametre, bu gecikmenin milisaniye cinsinden uzunluğunu belirler.

## <a name="cmfcautohidebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a> CMFCAutoHideBar:: OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parametreler

'ndaki *CPoint*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarremoveautohidewindow"></a><a name="removeautohidewindow"></a> CMFCAutoHideBar:: Removeoto Hidewindow

Otomatik gizleme penceresini kaldırır ve yok eder.

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>Parametreler

CDockablePane * *Pautohidewnd* kaldırılacak pencereyi otomatik gizle.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarsetactiveingroup"></a><a name="setactiveingroup"></a> CMFCAutoHideBar:: SetActiveInGroup

Otomatik gizleme çubuğunu etkin olarak işaretler.

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>Parametreler

'ndaki Etkin olarak ayarlamak için BOOL *bActive* true; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bkz. [CPane:: SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).

## <a name="cmfcautohidebarsetrecentvisiblestate"></a><a name="setrecentvisiblestate"></a> CMFCAutoHideBar:: SetRecentVisibleState

```cpp
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>Parametreler

*bState*<br/>
'ndaki Ayarlanacak durum.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarshowautohidewindow"></a><a name="showautohidewindow"></a> CMFCAutoHideBar:: Showoto Hidewindow

Otomatik gizleme penceresini gösterir.

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parametreler

*pAutoHideWnd*<br/>
'ndaki Gösterilecek pencere.

*bShow*<br/>
'ndaki Pencereyi göstermek için TRUE.

*bDelay*<br/>
'ndaki Bu parametre yok sayılır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarstretchpane"></a><a name="stretchpane"></a> CMFCAutoHideBar:: ayarlayıcı bölmesi

Daraltılmış durumunda otomatik gizleme çubuğunu nesneye sığacak şekilde yeniden boyutlandırır `CMFCAutoHideButton` .

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>Parametreler

*nLength*<br/>
'ndaki Değer, temel uygulamada kullanılmıyor. Türetilmiş uygulamalarda, yeniden boyutlandırılan bölmenin uzunluğunu belirtmek için bu değeri kullanın.

*bVert*<br/>
'ndaki Değer, temel uygulamada kullanılmıyor. Türetilmiş uygulamalarda, otomatik gizleme çubuğunun dikey olarak daraltılabileceği durumu işlemek için TRUE, otomatik gizleme çubuğunun yatay olarak daraltılabileceği durum için FALSE kullanın.

### <a name="return-value"></a>Dönüş Değeri

Yeniden boyutlandırılmış bölmenin elde edilen boyutu.

### <a name="remarks"></a>Açıklamalar

Türetilmiş sınıflar, davranışı özelleştirmek için bu yöntemi geçersiz kılabilir.

## <a name="cmfcautohidebarunsetautohidemode"></a><a name="unsetautohidemode"></a> CMFCAutoHideBar:: UnSetAutoHideMode

Otomatik gizleme çubuklarının bir grubu için otomatik gizleme modunu devre dışı bırakır.

```cpp
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>Parametreler

[in] Pfirstbaringroa grubundaki ilk otomatik gizleme çubuğuna bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarupdatevisiblestate"></a><a name="updatevisiblestate"></a> CMFCAutoHideBar:: UpdateVisibleState

Otomatik gizleme çubuğunun yeniden çizilmesi gerektiğinde Framework tarafından çağırılır.

```cpp
void UpdateVisibleState();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane sınıfı](../../mfc/reference/cpane-class.md)<br/>
[CAutoHideDockSite sınıfı](../../mfc/reference/cautohidedocksite-class.md)<br/>
[CMFCAutoHideButton sınıfı](../../mfc/reference/cmfcautohidebutton-class.md)
