---
title: CTabbedPane Sınıfı
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
ms.openlocfilehash: 17351eaed585ec34117a2ef825964fd51bd0d86b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365944"
---
# <a name="ctabbedpane-class"></a>CTabbedPane Sınıfı

Çıkarılabilir sekmelerle bir bölmenin işlevselliğini uygular.

veya daha fazla ayrıntı Visual Studio yüklemenizin **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|Varsayılan oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)|(Geçersiz kılar [CBaseTabbedPane::DetachPane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|Sekmelerin otomatik boyamasını etkinleştirir veya devre dışı kılabilir.|
|[CTabbedPane::FloatTab](#floattab)|Bölmeyi yüzdürür, ancak bölme şu anda çıkarılabilir bir sekmede bulunursa. (Geçersiz Kılar [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|
|[CTabbedPane::GetTabArea](#gettabarea)|Sekmeli penceredeki sekme alanının boyutunu ve konumunu döndürür.|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|Sekmeli bölmenin otomatik hide moduna geçirilip geçirilmeyeceğini belirler. (Geçersiz kılar [CBaseTabbedPane::HasAutoHideMode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|Sekmelerin pencerenin alt kısmında bulunup bulunmadığını belirler.|
|[CTabbedPane::ResetTabs](#resettabs)|Sekmeli tüm bölmeleri varsayılan duruma sıfırlar.|
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|Otomatik renk özelliği etkinleştirildiğinde kullanılabilecek özel renklerin listesini ayarlar.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|Uygulamadaki sekmeler için varsayılan konum.|
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|Özel `CMFCTabCtrl`türetilmiş bir nesne için çalışma zamanı sınıf bilgileri.|

## <a name="remarks"></a>Açıklamalar

Bir kullanıcı ikinci bölmenin alt yazısını işaret ederek bir bölmeyi diğerine iliştirdiğinde çerçeve otomatik olarak bu sınıfın bir örneğini oluşturur. Çerçeve tarafından oluşturulan sekmeli bölmelerin tümünün -1 kimliği vardır.

Outlook stili sekmeleri yerine normal sekmeleri belirtmek için, AFX_CBRS_REGULAR_TABS [stilini CDockablePane::CreateEx](../../mfc/reference/cdockablepane-class.md#createex) yöntemine geçirin.

Çıkarılabilir sekmeler içeren sekmeli bir bölme oluşturursanız, bölme çerçeve tarafından otomatik olarak yok edilebilir, bu nedenle işaretçiyi depolamamalısınız. Sekmeli bölmeye işaretçi almak için `CBasePane::GetParentTabbedPane` yöntemi arayın.

## <a name="example"></a>Örnek

Bu örnekte bir `CTabbedPane` nesne oluştururuz. Ardından, ek sekmeler eklemek için [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) kullanın.

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

Sekmeli denetim çubuğu nesnesi oluşturmanın başka bir yolu [cdockablePane kullanmaktır::AttachToTabWnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd). Yöntem `AttachToTabWnd` dinamik cDockablePane tarafından belirlenen runtime sınıf bilgilerini kullanarak sekmeli bölme nesnesi [oluşturur::SetTabbedPaneRTC](../../mfc/reference/cdockablepane-class.md#settabbedpanertc).

Bu örnekte, dinamik olarak sekmeli bir bölme oluşturur, iki sekme ekleyip ikinci sekmeyi çıkarılamaz hale getirmeye devam ediyoruz.

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

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[Cdockablepane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CTabbedPane](../../mfc/reference/ctabbedpane-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxTabbedPane.h

## <a name="ctabbedpanedetachpane"></a><a name="detachpane"></a>CTabbedPane::DetachPane

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>

[içinde] *bHide*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpaneenabletabautocolor"></a><a name="enabletabautocolor"></a>CTabbedPane::EnableTabAutoColor

Sekmelerin otomatik boyamasını etkinleştirir veya devre dışı kılabilir.

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] SEKmelerin otomatik renklendirmesini etkinleştirmek için TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Uygulamadaki tüm sekmeli bölmelerde sekmelerin otomatik renklendirmesini etkinleştirmek veya devre dışı katmak için bu statik yöntemi kullanın. Bu özellik etkinleştirildiğinde, her sekme kendi rengiyle doldurulur. [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) yöntemini arayarak sekmeleri renklendirmek için kullanılan renklerin listesini bulabilirsiniz.

[CTabbedPane:SetTabAutoColors](#settabautocolors)numaralı telefonu arayarak sekmeler için kullanılacak renklerin listesini belirtebilirsiniz.

Varsayılan olarak, bu seçenek devre dışı bırakılır.

## <a name="ctabbedpanefloattab"></a><a name="floattab"></a>CTabbedPane::FloatTab

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

[içinde] *pBar*<br/>
[içinde] *nTabID*<br/>
[içinde] *dockMethod*<br/>
[içinde] *bHide*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpanegettabarea"></a><a name="gettabarea"></a>CTabbedPane::GetTabArea

Sekmeli penceredeki sekme alanının boyutunu ve konumunu döndürür.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parametreler

*rectTabAreaTop*<br/>
[çıkış] Üst sekme alanının ekran koordinatlarında boyut ve konumunu içerir.

*rectTabAreaBottom*<br/>
[çıkış] Alt sekme alanının ekran koordinatlarında boyut ve konumunu içerir.

### <a name="remarks"></a>Açıklamalar

Çerçeve, bir kullanıcının sürüklediği bölmeyi nasıl sabitleyeceklerini belirlemek için bu yöntemi çağırır. Kullanıcı bir bölmeyi hedef bölmenin sekme alanı nın üzerine sürüklediğinde, çerçeve bunu hedef bölmenin yeni bir sekmesi olarak eklemeye çalışır. Aksi takdirde, bölmeyi hedef bölmenin yan tarafına yerleştirmeye çalışır ve bu da iki bölmeyi ayıran bölme bölücülü yeni bir bölme kapsayıcısı oluşturmayı içerir.

Bu davranışı değiştirmek `CTabbedPane`için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="ctabbedpanegettabwnd"></a><a name="gettabwnd"></a>CTabbedPane::GetTabWnd

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>CTabbedPane::HasAutoHideMode

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpaneistablocationbottom"></a><a name="istablocationbottom"></a>CTabbedPane::IsTabLocationBottom

Sekmelerin pencerenin alt kısmında bulunup bulunmadığını belirler.

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sekme alanı sekme penceresinin alt kısmında bulunuyorsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="ctabbedpanem_btabsalwaystop"></a><a name="m_btabsalwaystop"></a>CTabbedPane::m_bTabsAlwaysTop

Uygulamadaki sekmeler için varsayılan konum.

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>Açıklamalar

Bu statik üyeyi, uygulamadaki tüm sekmeleri sekmeli bölmenin üst kısmında görüntülenmeye zorlamak için TRUE olarak ayarlayın.

Sekmeli bölme oluşturulmadan önce bu değeri ayarlamanız gerekir.

Varsayılan değer FALSE'dur.

## <a name="ctabbedpanem_ptabwndrtc"></a><a name="m_ptabwndrtc"></a>CTabbedPane::m_pTabWndRTC

Özel `CMFCTabCtrl`türetilmiş bir nesne için çalışma zamanı sınıf bilgileri.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>Açıklamalar

Sekmeli bölmenin içinde özel sekmeli pencere kullanıyorsanız, bu statik üye değişkeni türetilmiş nesnenin `CMFCTabCtrl`çalışma zamanı sınıf bilgilerine işaretçi olarak ayarlayın.

## <a name="ctabbedpaneresettabs"></a><a name="resettabs"></a>CTabbedPane::ResetTabs

Sekmeli tüm bölmeleri varsayılan duruma sıfırlar.

```
static void ResetTabs();
```

### <a name="remarks"></a>Açıklamalar

Sekmeli tüm bölmeleri varsayılan durumlarına geri getirmek için bu yöntemi çağırın. Çağrıldığında, bu yöntem, sekmeli tüm bölmelerin kenarlık boyutlarını ve otomatik renk durumunu sıfırlar.

## <a name="ctabbedpanesettabautocolors"></a><a name="settabautocolors"></a>CTabbedPane::SetTabAutoColors

Otomatik renk özelliği etkinleştirildiğinde kullanılan özel renklerin listesini ayarlar.

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Parametreler

*arColors*<br/>
[içinde] Ayarlanacak renk dizisini içerir.

### <a name="remarks"></a>Açıklamalar

Otomatik renk özelliği etkinleştirildiğinde kullanılan renk listesini özelleştirmek için bu yöntemi kullanın. Bu statik bir işlevdir ve uygulamanızdaki tüm sekmeli bölmeleri etkiler.

Otomatik renk özelliğini etkinleştirmek veya devre dışı katmak için [CTabbedPane::EnableTabAutoColor'u](#enabletabautocolor) kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)<br/>
[CBaseTabbedPane Sınıfı](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBar Sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)
