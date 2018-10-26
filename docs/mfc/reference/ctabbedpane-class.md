---
title: CTabbedPane sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
dev_langs:
- C++
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b01148affc70d09032d2082f4fc8756dd8c96cf
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074143"
---
# <a name="ctabbedpane-class"></a>CTabbedPane sınıfı

Çıkarılabilir sekmeler içeren bölme işlevselliğini uygular.

veya daha fazla ayrıntı içinde bulunan kaynak koduna **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

## <a name="syntax"></a>Sözdizimi

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)|(Geçersiz kılmaları [CBaseTabbedPane::DetachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|Etkinleştirir veya sekme otomatik renklendirme devre dışı bırakır.|
|[CTabbedPane::FloatTab](#floattab)|Bölmeyi şu anda çıkarılabilir bir sekmede yer alıyorsa ancak yalnızca bir bölme kaydırır. (Geçersiz kılmaları [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|
|[CTabbedPane::GetTabArea](#gettabarea)|Boyutunu ve sekmeli pencere içinde sekme alanının konumunu döndürür.|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|Sekmeli bölme autohide moduna geçiş olup olmadığını belirler. (Geçersiz kılmaları [CBaseTabbedPane::HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|Sekmeleri pencerenin alt kısmında bulunan olup olmadığını belirler.|
|[CTabbedPane::ResetTabs](#resettabs)|Tüm sekmeli bölmelerde varsayılan duruma sıfırlanır.|
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|Otomatik Renk özelliği etkinleştirilmişse kullanılabilecek özel renk listesi ayarlar.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|Uygulama sekmelerde varsayılan konumu.|
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|Özel bir çalışma zamanı sınıf bilgileri `CMFCTabCtrl`-türetilmiş bir nesneye.|

## <a name="remarks"></a>Açıklamalar

İkinci bölümde açıklamalı alt yazı işaret ederek bir kullanıcı bir bölme ekler framework otomatik olarak bu sınıfın bir örneğini oluşturur. Tüm framework tarafından oluşturulan sekmeli bölmelerde,-1 bir Kimliğe sahip.

Outlook stilinde sekmeler yerine normal sekmeleri belirtmek için AFX_CBRS_REGULAR_TABS stil geçirmek [CDockablePane::CreateEx](../../mfc/reference/cdockablepane-class.md#createex) yöntemi.

Çıkarılabilir sekmeler ile sekmeli bir bölmeye oluşturursanız, işaretçi depolanmamalıdır şekilde bölmesinde otomatik olarak çerçeve tarafından yok. Sekmeli bölme için bir işaretçi alma çağrısı `CBasePane::GetParentTabbedPane` yöntemi.

## <a name="example"></a>Örnek

Bu örnekte oluşturduğumuz bir `CTabbedPane` nesne. Ardından, [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) ek sekme eklemek için.

```cpp
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),
    TRUE,
    (UINT) -1,
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |
    WS_CLIPCHILDREN | CBRS_LEFT |
    CBRS_FLOAT_MULTI))
{
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create
}

pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```

## <a name="example"></a>Örnek

Sekmeli denetim çubuğu nesnesi oluşturmak için başka bir yolu [CDockablePane::AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd). `AttachToTabWnd` Yöntemi dinamik olarak belirlenen çalışma zamanı sınıf bilgileri kullanarak bir sekmeli bölme nesnesi [CDockablePane::SetTabbedPaneRTC](../../mfc/reference/cdockablepane-class.md#settabbedpanertc).

Bu örnekte, dinamik olarak oluştururuz sekmeli bir bölmeye iki sekme ekleme ve ikinci sekme çıkarılabilir olmayan olun.

```cpp
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CTabbedPane](../../mfc/reference/ctabbedpane-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxTabbedPane.h

##  <a name="detachpane"></a>  CTabbedPane::DetachPane

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

[in] *pBar*<br/>

[in] *bHide*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="enabletabautocolor"></a>  CTabbedPane::EnableTabAutoColor

Etkinleştirir veya sekme otomatik renklendirme devre dışı bırakır.

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Sekme otomatik renklendirme etkinleştirmek için TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Etkinleştirme veya devre dışı otomatik renklendirme, uygulamadaki tüm sekmeli bölmelerde sekmelerde statik bu yöntemi kullanın. Her sekme, bu özellik etkinleştirildiğinde, kendi renge göre doldurulur. Sekmeleri çağırarak renk için kullanılan renkleri listesini bulabilirsiniz [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) yöntemi.

Çağırarak sekmeler için kullanılacak olan renk listesi belirtebilirsiniz [CTabbedPane::SetTabAutoColors](#settabautocolors).

Varsayılan olarak, bu seçenek devre dışıdır.

##  <a name="floattab"></a>  CTabbedPane::FloatTab

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

[in] *pBar*<br/>
[in] *nTabID*<br/>
[in] *dockMethod*<br/>
[in] *bHide*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="gettabarea"></a>  CTabbedPane::GetTabArea

Sekmeli penceresinde sekme alanı konumunu ve boyutunu döndürür.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
[out] Boyut ve konum, ekran koordinatlarında üst sekme alanının içerir.

*rectTabAreaBottom*<br/>
[out] Boyut ve konum, ekran koordinatlarında alt sekme alanının içerir.

### <a name="remarks"></a>Açıklamalar

Framework, bir kullanıcı sürükleyerek bir bölme sabitlemek nasıl belirlemek için bu yöntemi çağırır. Kullanıcı hedef bölmesinin sekme alanı bir bölmeyi sürüklediğinde, çerçeve, hedef bölmesinde yeni bir sekme eklemeyi dener. Aksi takdirde iki bölmeyi ayırır bölmesinde ayırıcı ile yeni bir bölmesinde kapsayıcı oluşturmayı içerir hedef bölmesinde tarafına bölmesinde sabitlemek çalışır.

Bu yöntemin bir `CTabbedPane`-türetilmiş sınıf bu davranışı değiştirmek için.

##  <a name="gettabwnd"></a>  CTabbedPane::GetTabWnd

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="hasautohidemode"></a>  CTabbedPane::HasAutoHideMode

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="istablocationbottom"></a>  CTabbedPane::IsTabLocationBottom

Sekmeleri pencerenin alt kısmında bulunan olup olmadığını belirler.

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme alanı sekmeli penceresinin en altında yer alıyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_btabsalwaystop"></a>  CTabbedPane::m_bTabsAlwaysTop

Uygulama sekmelerde varsayılan konumu.

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>Açıklamalar

Sekmeli bölmesinin en üstünde görüntülenecek uygulamadaki tüm sekmeler zorla True Bu statik üyeye ayarlayın.

Sekmeli bir bölmeye oluşturmadan önce bu değeri ayarlamanız gerekir.

Varsayılan değer FALSE olur.

##  <a name="m_ptabwndrtc"></a>  CTabbedPane::m_pTabWndRTC

Özel bir çalışma zamanı sınıf bilgileri `CMFCTabCtrl`-türetilmiş bir nesneye.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>Açıklamalar

Bu statik üye değişkeninin çalışma zamanı sınıf bilgilerini işaretçisi ayarlama bir `CMFCTabCtrl`-özel bir sekmeli pencere sekmeli bir bölmeye içinde kullanıyorsanız, türetilmiş bir nesneye.

##  <a name="resettabs"></a>  CTabbedPane::ResetTabs

Tüm sekmeli bölmelerde varsayılan duruma sıfırlanır.

```
static void ResetTabs();
```

### <a name="remarks"></a>Açıklamalar

Tüm sekmeli bölmelerde varsayılan durumlarına geri dönmek için bu yöntemi çağırın. Bu yöntem, çağrıldığında, kenarlık boyutları ve tüm sekmeli bölmelerde otomatik renk durumunu sıfırlar.

##  <a name="settabautocolors"></a>  CTabbedPane::SetTabAutoColors

Otomatik Renk özelliği etkinleştirilmişse kullanılan özel renk listesi ayarlar.

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Parametreler

*arColors*<br/>
[in] Ayarlanacak renkleri dizisini içerir.

### <a name="remarks"></a>Açıklamalar

Listeyi otomatik renk özelliği etkinleştirilmişse kullanılan renkleri özelleştirmek için bu yöntemi kullanın. Bu statik işlev ve uygulamanızı tüm sekmeli bölmelerde etkiler.

Kullanım [CTabbedPane::EnableTabAutoColor](#enabletabautocolor) etkinleştirme veya otomatik renk özelliğini devre dışı.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)<br/>
[CBaseTabbedPane Sınıfı](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)
