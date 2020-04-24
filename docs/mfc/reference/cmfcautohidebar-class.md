---
title: CMFCAutoHideBar Sınıfı
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
ms.openlocfilehash: 05f77dfba442f1ce4a375c8f225908799ece1788
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751768"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar Sınıfı

Sınıf, `CMFCAutoHideBar` otomatik gizleme özelliğini uygulayan özel bir araç çubuğu sınıfıdır.

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCAutoHideBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||
|[CMFCAutoHideBar::İzinShowOnPaneMenu](#allowshowonpanemenu)|(Geçersiz `CPane::AllowShowOnPaneMenu`kılar .)|
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|[(Overrides CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCAutoHideBar::Oluştur](#create)|Bir denetim çubuğu oluşturur ve [CPane](../../mfc/reference/cpane-class.md) nesnesine bağlar. [(CPane geçersiz kılar::Oluştur](../../mfc/reference/cpane-class.md#create).)|
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar::GetVisibleSayısı](#getvisiblecount)||
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|Özel bir bölme menüsü görüntülenmek üzereyken çerçeve tarafından çağrılır. [(Overrides CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||
|[CMFCAutoHideBar::SetactiveinGroup](#setactiveingroup)|[(CPane geçersiz kılar::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|
|[CMFCAutoHideBar::SetrecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||
|[CMFCAutoHideBar::StretchPane](#stretchpane)|Bölmeyi dikey veya yatay olarak uzalar. [(Overrides CBasePane::StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane).)|
|[CMFCAutoHidebar::UnsetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|Kullanıcının fare imlecini [CMFCAutoHideButton Sınıfı'nın](../../mfc/reference/cmfcautohidebutton-class.md) üzerine yerleştirirken olduğu an ile çerçevenin ilişkili pencereyi gösterdiği an arasındaki zaman gecikmesi.|

## <a name="remarks"></a>Açıklamalar

Kullanıcı otomatik gizleme moduna bir dock bölmesini çevirdiğinde, çerçeve `CMFCAutoHideBar` otomatik olarak bir nesne oluşturur. Ayrıca gerekli [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) ve [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nesneleri oluşturur. Her `CAutoHideDockSite` nesne bir birey `CMFCAutoHideButton`ile ilişkilidir.

Sınıf, `CMFCAutoHideBar` kullanıcının faresi `CAutoHideDockSite` bir `CMFCAutoHideButton`. Araç çubuğu bir WM_MOUSEMOVE iletisi aldığında, `CMFCAutoHideBar` bir zamanlayıcı başlatır. Zamanlayıcı bittiğinde, araç çubuğuna WM_TIMER bir olay bildirimi gönderir. Araç çubuğu, fare işaretçisinin zamanlayıcı başlatıldığında üzerinde konumlandırıldığı otomatik gizleme düğmesinin üzerine yerleştirilip yerleştirilemediğini denetleyerek bu olayı işler. Eğer varsa, ekli `CAutoHideDockSite` görüntülenir.

Zamanlayıcının gecikme sinin uzunluğunu ayarlayarak `m_nShowAHWndDelay`kontrol edebilirsiniz. Varsayılan değer 400 ms'dir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCAutoHideBar` nesnenin nasıl oluşturup yöntemini nasıl kullanılacağını `GetDockSiteRow` gösterir.

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[Cmfcautohidebar](../../mfc/reference/cmfcautohidebar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxautohidebar.h

## <a name="cmfcautohidebaraddautohidewindow"></a><a name="addautohidewindow"></a>CMFCAutoHideBar::AddAutoHideWindow

Otomatik gizleme `CDockablePane` sağlayan bir pencereye işlevsellik ekler.

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

*pAutoHideWnd*<br/>
[içinde] Saklamak istediğin pencere.

*dwHizalama*<br/>
[içinde] Otomatik gizle düğmesinin uygulama penceresiyle hizalanmasını belirten bir değer.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

*dwAlignment* parametresi, otomatik gizleme düğmesinin uygulamada nerede bulunduğunu gösterir. Parametre aşağıdaki değerlerden biri olabilir:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCAutoHideBar::İzinShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCAutoHideBar::CalcFixedLayout

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

## <a name="cmfcautohidebarcmfcautohidebar"></a><a name="cmfcautohidebar"></a>CMFCAutoHideBar::CMFCAutoHideBar

CMFCAutoHideBar nesnesi oluşturuyor.

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarcreate"></a><a name="create"></a>CMFCAutoHideBar::Oluştur

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

*Dwstyle*<br/>

*Rect*<br/>

*pParentWnd*<br/>

*Nıd*<br/>

*dwControlBarStyle*<br/>

*Pcontext*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebargetfirstahwindow"></a><a name="getfirstahwindow"></a>CMFCAutoHideBar::GetFirstAHWindow

Bir işaretçiyi uygulamadaki ilk otomatik gizleme penceresine döndürür.

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Uygulamadaki ilk otomatik gizleme penceresi veya yoksa NULL.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebargetvisiblecount"></a><a name="getvisiblecount"></a>CMFCAutoHideBar::GetVisibleSayısı

Görünür otomatik gizleme düğmelerinin sayısını alır.

```
int GetVisibleCount();
```

### <a name="return-value"></a>Dönüş Değeri

Görünür otomatik gizleme düğmelerinin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarm_nshowahwnddelay"></a><a name="m_nshowahwnddelay"></a>CMFCAutoHideBar::m_nShowAHWndDelay

Kullanıcının fare imlecini [CMFCAutoHideButton Sınıfı'nın](../../mfc/reference/cmfcautohidebutton-class.md) üzerine yerleştirirken olduğu an ile çerçevenin ilişkili pencereyi gösterdiği an arasındaki zaman gecikmesi.

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>Açıklamalar

Kullanıcı fare imlecini bir `CMFCAutoHideButton`, çerçeve ilişkili pencereyi görüntülemeden önce hafif bir gecikmeye yerleştirir. Bu parametre, bu gecikmenin milisaniye cinsinden uzunluğunu belirler.

## <a name="cmfcautohidebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>CMFCAutoHideBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parametreler

[içinde] *CPoint*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarremoveautohidewindow"></a><a name="removeautohidewindow"></a>CMFCAutoHideBar::RemoveAutoHideWindow

Otomatik gizleme penceresini kaldırır ve yok eder.

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>Parametreler

CDockablePane* *pAutoHideWnd* Otomatik gizleme penceresini kaldırmak için.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarsetactiveingroup"></a><a name="setactiveingroup"></a>CMFCAutoHideBar::SetactiveinGroup

Otomatik gizleme çubuğunun etkin olduğunu işaretler.

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>Parametreler

[içinde] BOOL *bActive* TRUE aktif olarak ayarlanır; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bkz. [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).

## <a name="cmfcautohidebarsetrecentvisiblestate"></a><a name="setrecentvisiblestate"></a>CMFCAutoHideBar::SetrecentVisibleState

```cpp
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>Parametreler

*bDevlet durumu*<br/>
[içinde] Eyalet ayarlı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarshowautohidewindow"></a><a name="showautohidewindow"></a>CMFCAutoHideBar::ShowAutoHideWindow

Otomatik gizleme penceresini gösterir.

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parametreler

*pAutoHideWnd*<br/>
[içinde] Gösterme penceresi.

*bGöster*<br/>
[içinde] DOĞRU pencereyi göstermek için.

*bGecikme*<br/>
[içinde] Bu parametre yoksayılır.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarstretchpane"></a><a name="stretchpane"></a>CMFCAutoHideBar::StretchPane

`CMFCAutoHideButton` Nesneye uyacak şekilde otomatik gizleme çubuğunu daraltılmış durumunda yeniden boyutlandırıyor.

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>Parametreler

*nUzunluk*<br/>
[içinde] Değer temel uygulamada kullanılmaz. Türetilen uygulamalarda, yeniden boyutlandırılmış bölmenin uzunluğunu belirtmek için bu değeri kullanın.

*bVert*<br/>
[içinde] Değer temel uygulamada kullanılmaz. Türetilen uygulamalarda, otomatik gizleme çubuğunun dikey olarak daraltıldığı kılıfı işlemek için TRUE'yu ve otomatik gizleme çubuğunun yatay olarak daraltıldığı durum için FALSE'yi kullanın.

### <a name="return-value"></a>Dönüş Değeri

Yeniden boyutlandırılmış bölmenin ortaya çıkan boyutu.

### <a name="remarks"></a>Açıklamalar

Türetilen sınıflar davranışı özelleştirmek için bu yöntemi geçersiz kılabilir.

## <a name="cmfcautohidebarunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFCAutoHidebar::UnsetAutoHideMode

Bir grup otomatik gizleme çubukları için otomatik gizleme modunu devre dışı kılabilir.

```cpp
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>Parametreler

[in] pFirstBarInGroup Gruptaki ilk otomatik gizleme çubuğuna işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcautohidebarupdatevisiblestate"></a><a name="updatevisiblestate"></a>CMFCAutoHideBar::UpdateVisibleState

Otomatik gizleme çubuğunun yeniden çizilmesi gerektiğinde çerçeve tarafından çağrılır.

```cpp
void UpdateVisibleState();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPane Sınıfı](../../mfc/reference/cpane-class.md)<br/>
[CAutoHideDockSite Sınıfı](../../mfc/reference/cautohidedocksite-class.md)<br/>
[CMFCAutoHideButton Sınıfı](../../mfc/reference/cmfcautohidebutton-class.md)
