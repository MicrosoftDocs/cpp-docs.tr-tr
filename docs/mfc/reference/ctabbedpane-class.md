---
description: 'Daha fazla bilgi edinin: CTabbedPane sınıfı'
title: CTabbedPane sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: a337a68cdeadfec229b24e10a615ba49145ec1ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264485"
---
# <a name="ctabbedpane-class"></a>CTabbedPane sınıfı

Çıkarılabilir sekmeler içeren bir bölme işlevlerini uygular.

ya da daha fazla ayrıntı, Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

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
|[CTabbedPane::D Etachi bölmesi](#detachpane)|( [CBaseTabbedPane geçersiz kılar::D etachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|
|[CTabbedPane:: EnableTabAutoColor](#enabletabautocolor)|Sekmelerin otomatik renklendirmesini sunar veya devre dışı bırakır.|
|[CTabbedPane:: FloatTab](#floattab)|Bir bölmeyi, ancak yalnızca bölme şu anda çıkarılabilir bir sekmede bulunuyorsa kayar. ( [CBaseTabbedPane:: FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab)geçersiz kılar.)|
|[CTabbedPane:: GetTabArea](#gettabarea)|Sekmeli pencerenin içindeki sekme alanının boyutunu ve konumunu döndürür.|
|[CTabbedPane:: GetTabWnd](#gettabwnd)||
|[CTabbedPane:: HasAutoHideMode](#hasautohidemode)|Sekmeli bölmenin otomatik gizleme moduna geçirilip geçirilemeyeceğini belirler. ( [CBaseTabbedPane:: HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode)öğesini geçersiz kılar.)|
|[CTabbedPane:: ıstablocationbottom](#istablocationbottom)|Sekmelerin pencerenin altında olup olmadığını belirler.|
|[CTabbedPane:: Resetsekmeleri](#resettabs)|Tüm sekmeli bölmeleri varsayılan durumuna sıfırlar.|
|[CTabbedPane:: SetTabAutoColors](#settabautocolors)|Otomatik renk özelliği etkinken kullanılabilecek özel renklerin bir listesini ayarlar.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CTabbedPane:: m_bTabsAlwaysTop](#m_btabsalwaystop)|Uygulamadaki sekmelerin varsayılan konumu.|
|[CTabbedPane:: m_pTabWndRTC](#m_ptabwndrtc)|Özel türetilmiş bir nesne için çalışma zamanı sınıfı bilgileri `CMFCTabCtrl` .|

## <a name="remarks"></a>Açıklamalar

Bir Kullanıcı ikinci bölmenin açıklamalı alt yazısının üzerine gelerek bir bölmeden diğerine otomatik olarak bu sınıfın bir örneğini oluşturur. Framework tarafından oluşturulan tüm sekmeli bölmelerin KIMLIĞI-1 ' dir.

Outlook stili sekmeler yerine normal sekmeleri belirtmek için AFX_CBRS_REGULAR_TABS stilini [CDockablePane:: CreateEx](../../mfc/reference/cdockablepane-class.md#createex) metoduna geçirin.

Çıkarılabilir sekmelerle birlikte sekmeli bir bölme oluşturursanız, bölmesi çerçeve tarafından otomatik olarak yok edilebilir, bu nedenle işaretçiyi depolamamalısınız. Sekmeli bölmeye bir işaretçi almak için `CBasePane::GetParentTabbedPane` yöntemini çağırın.

## <a name="examples"></a>Örnekler

Bu örnekte bir `CTabbedPane` nesne oluşturacağız. Daha sonra, ek sekmeler eklemek için [CBaseTabbedPane:: AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) kullanıyoruz.

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

Sekmeli denetim çubuğu nesnesi oluşturmanın başka bir yolu da [CDockablePane:: AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd)kullanmaktır. `AttachToTabWnd`Yöntemi, [CDockablePane:: SetTabbedPaneRTC](../../mfc/reference/cdockablepane-class.md#settabbedpanertc)tarafından ayarlanan çalışma zamanı sınıf bilgilerini kullanarak dinamik olarak sekmeli bölme nesnesi oluşturur.

Bu örnekte, dinamik olarak sekmeli bir bölme oluşturur, iki sekme ekler ve ikinci sekmeyi kurtarılamaz hale getirir.

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

**Üstbilgi:** afxTabbedPane. h

## <a name="ctabbedpanedetachpane"></a><a name="detachpane"></a> CTabbedPane::D Etachi bölmesi

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>

'ndaki *Bhide*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpaneenabletabautocolor"></a><a name="enabletabautocolor"></a> CTabbedPane:: EnableTabAutoColor

Sekmelerin otomatik renklendirmesini sunar veya devre dışı bırakır.

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Sekmelerin otomatik renklendirmesini etkinleştirmek için TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Uygulamadaki tüm sekmeli bölmelerde sekmelerin otomatik renklendirmesini etkinleştirmek veya devre dışı bırakmak için bu statik yöntemi kullanın. Bu özellik etkinleştirildiğinde, her sekme kendi rengi ile doldurulur. [CMFCBaseTabCtrl:: GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) metodunu çağırarak sekmeleri renklendirmek için kullanılan renklerin listesini bulabilirsiniz.

[CTabbedPane:: SetTabAutoColors](#settabautocolors)çağırarak, sekmeler için kullanılacak renklerin listesini belirtebilirsiniz.

Varsayılan olarak, bu seçenek devre dışıdır.

## <a name="ctabbedpanefloattab"></a><a name="floattab"></a> CTabbedPane:: FloatTab

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>
'ndaki *Ntabıd*<br/>
'ndaki *Dockyöntemi*<br/>
'ndaki *Bhide*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpanegettabarea"></a><a name="gettabarea"></a> CTabbedPane:: GetTabArea

Sekmeli penceredeki sekme alanının boyutunu ve konumunu döndürür.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
dışı Üst sekme alanının boyutunu ve konumunu Ekran koordinatlarında içerir.

*rectTabAreaBottom*<br/>
dışı Alt sekme alanının Ekran koordinatlarındaki boyutunu ve konumunu içerir.

### <a name="remarks"></a>Açıklamalar

Framework, bir kullanıcının sürüklemekte olduğu bir bölmenin nasıl sabitlenmesi gerektiğini öğrenmek için bu yöntemi çağırır. Kullanıcı hedef bölmenin sekme alanının üzerine bir bölme sürüklediğinde, çerçeve onu hedef bölmenin yeni bir sekmesi olarak eklemeye çalışır. Aksi takdirde, bölmeyi hedef bölmenin yanına yerleştirmeyi dener, bu, iki bölmeyi ayıran bölme ayracına sahip yeni bir bölme kapsayıcısı oluşturmayı içerir.

`CTabbedPane`Bu davranışı değiştirmek için bu yöntemi, türetilmiş bir sınıfta geçersiz kılın.

## <a name="ctabbedpanegettabwnd"></a><a name="gettabwnd"></a> CTabbedPane:: GetTabWnd

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpanehasautohidemode"></a><a name="hasautohidemode"></a> CTabbedPane:: HasAutoHideMode

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpaneistablocationbottom"></a><a name="istablocationbottom"></a> CTabbedPane:: ıstablocationbottom

Sekmelerin pencerenin altında olup olmadığını belirler.

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme alanı sekmeli pencerenin alt kısmında yer alıyorsa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpanem_btabsalwaystop"></a><a name="m_btabsalwaystop"></a> CTabbedPane:: m_bTabsAlwaysTop

Uygulamadaki sekmelerin varsayılan konumu.

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>Açıklamalar

Uygulamadaki tüm sekmelerin sekmeli bölmenin en üstünde gösterilmesini zorlamak için bu statik üyeyi TRUE olarak ayarlayın.

Sekmeli bölme oluşturulmadan önce bu değeri ayarlamanız gerekir.

Varsayılan değer FALSE 'dur.

## <a name="ctabbedpanem_ptabwndrtc"></a><a name="m_ptabwndrtc"></a> CTabbedPane:: m_pTabWndRTC

Özel türetilmiş bir nesne için çalışma zamanı sınıfı bilgileri `CMFCTabCtrl` .

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>Açıklamalar

`CMFCTabCtrl`Sekmeli bölme içinde özel sekmeli pencere kullanıyorsanız, bu statik üye değişkenini bir türetilmiş nesnenin çalışma zamanı sınıfı bilgilerine bir işaretçiye ayarlayın.

## <a name="ctabbedpaneresettabs"></a><a name="resettabs"></a> CTabbedPane:: Resetsekmeleri

Tüm sekmeli bölmeleri varsayılan durumuna sıfırlar.

```
static void ResetTabs();
```

### <a name="remarks"></a>Açıklamalar

Tüm sekmeli bölmeleri varsayılan durumlarına dönüştürmek için bu yöntemi çağırın. Çağrıldığında, bu yöntem tüm sekmeli bölmelerin kenarlık boyutlarını ve otomatik renk durumunu sıfırlar.

## <a name="ctabbedpanesettabautocolors"></a><a name="settabautocolors"></a> CTabbedPane:: SetTabAutoColors

Otomatik renk özelliği etkinleştirildiğinde kullanılan özel renklerin listesini ayarlar.

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Parametreler

*Arrenkler*<br/>
'ndaki Ayarlanacak renklerin dizisini içerir.

### <a name="remarks"></a>Açıklamalar

Otomatik renk özelliği etkinken kullanılan renklerin listesini özelleştirmek için bu yöntemi kullanın. Bu statik bir işlevdir ve uygulamanızdaki tüm sekmeli bölmeleri etkiler.

Otomatik renk özelliğini etkinleştirmek veya devre dışı bırakmak için [CTabbedPane:: EnableTabAutoColor](#enabletabautocolor) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)<br/>
[CBaseTabbedPane sınıfı](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)
