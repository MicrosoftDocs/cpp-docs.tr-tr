---
title: CMFCReBar Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
ms.openlocfilehash: 409c97aba64c97ecf0443d14a70848cc298a44ba
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749992"
---
# <a name="cmfcrebar-class"></a>CMFCReBar Sınıfı

Nesne, `CMFCReBar` rebar denetimleri için düzen, kalıcılık ve durum bilgisi sağlayan bir denetim çubuğudur.
Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCReBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCReBar::Addbar](#addbar)|Bir çubuk için bir bant ekler.|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|[(Overrides CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCReBar::Canfloat](#canfloat)|[(Overrides CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CMFCReBar::Oluştur](#create)|Demir çubuğu denetimini oluşturur ve `CMFCReBar` nesneye bağlar.|
|[CMFCReBar::Etkinleştirme Docking](#enabledocking)|[(CBasePane geçersiz kılar::Etkinleştirdocking.)](../../mfc/reference/cbasepane-class.md#enabledocking)|
|[CMFCReBar::GetreBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Temel [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) ortak denetimine doğrudan erişim sağlar.|
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|[(Overrides CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCReBar::OnToolhitTest](#ontoolhittest)|[(Overrides CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|[(Overrides CBasePane::OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Geçersiz Kılar [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>Açıklamalar

Bir `CMFCReBar` nesne çeşitli alt pencereler içerebilir. Buna kutuları, araç çubuklarını ve liste kutularını düzenleme dahildir. Rebar'ı programlı olarak yeniden boyutlandırabilirsiniz veya kullanıcı tutucu çubuğunu sürükleyerek çubuğu el ile yeniden boyutlandırabilir. Ayrıca, bir demir çubuğu nesnesinin arka planını seçtiğiniz bir bit haritasına ayarlayabilirsiniz.

Bir çubuk nesnesi araç çubuğu nesnesine benzer şekilde tepki ritmiş olur. Bir çubuk denetimi bir veya daha fazla bant içerebilir ve her bant bir kavrayıcı çubuğu, bir biteş, metin etiketi ve bir alt pencere içerebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCReBar` nasıl kullanılacağını göstermektedir. Örnek, nasıl bir demir çubuğu denetimi oluşturulup bir bant ekleyeceğini gösterir. Bant dahili araç çubuğu işlevi görür. Bu kod [parçacığı, Demir Testi örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)\
•&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•&nbsp;[CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRebar.h

## <a name="cmfcrebaraddbar"></a><a name="addbar"></a>CMFCReBar::Addbar

Bir çubuk için bir bant ekler.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Parametreler

*pBar*<br/>
[içinde, dışarı] Çubuk'a eklenecek alt pencereiçin bir işaretçi. Başvurulan **nesne, WS_CHILD** pencere stiline sahip olmalıdır.

*Psztext*<br/>
[içinde] Metni demir çubuğunda görünecek şekilde belirtir. Metin alt pencerenin bir parçası değildir. Bunun yerine, demir çubuğunun kendisinde görüntülenir.

*pbmp*<br/>
[içinde, dışarı] Demir çubuğu arka planında görüntülenecek bit eşlemi belirtir.

*Dwstyle*<br/>
[içinde] Gruba uygulanacak stili içerir. Bant stillerinin tam listesi için, `fStyle` Windows SDK belgelerindeki [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) yapısındaki açıklamaya bakın.

*clrFore*<br/>
[içinde] Demir çubuğunun ön plan rengini temsil eder.

*clrGeri*<br/>
[içinde] Demir çubuğunun arka plan rengini temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer grup başarıyla çubuk eklendi; aksi takdirde, YANLIŞ.

## <a name="cmfcrebarcreate"></a><a name="create"></a>CMFCReBar::Oluştur

Demir çubuğu denetimini oluşturur ve [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) nesnesine bağlar.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[içinde, dışarı] Bu çubuk denetiminin ana penceresine bir işaretçi.

*dwCtrlStyle*<br/>
[içinde] Demir çubuğu denetiminin stilini belirtir. Varsayılan stil değeri, çubuk denetiminde bitişik bantları ayırmak için dar çizgiler görüntüleyen **RBS_BANDBORDERS.** Geçerli stillerin listesi için Windows SDK belgelerinde [Rebar Denetim Stilleri'ne](/windows/win32/Controls/rebar-control-styles) bakın.

*Dwstyle*<br/>
[içinde] Demir çubuğu denetiminin pencere stili. Geçerli stillerin listesi için [Bkz. Pencere Stilleri.](../../mfc/reference/styles-used-by-mfc.md#window-styles)

*Nıd*<br/>
[içinde] Demirçubuğun çocuk penceresi kimliği.

### <a name="return-value"></a>Dönüş Değeri

Rebar başarıyla oluşturulduysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebargetrebarctrl"></a><a name="getrebarctrl"></a>CMFCReBar::GetReBarCtrl

Nesneler için `CMFCReBar` `CReBarCtrl` temel ortak denetime doğrudan erişim sağlar.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Altta yatan `CReBarCtrl` nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Demir çubuğunuzu özelleştirirken Windows rebar ortak denetim işlevinden yararlanmak için bu yöntemi arayın.

## <a name="cmfcrebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCReBar::CalcFixedLayout

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

## <a name="cmfcrebarcanfloat"></a><a name="canfloat"></a>CMFCReBar::Canfloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebarenabledocking"></a><a name="enabledocking"></a>CMFCReBar::Etkinleştirme Docking

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

[içinde] *dwDockStyle*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebargetrebarbandinfosize"></a><a name="getrebarbandinfosize"></a>CMFCReBar::GetreBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>CMFCReBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parametreler

[içinde] *CPoint*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebarontoolhittest"></a><a name="ontoolhittest"></a>CMFCReBar::OnToolhitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nokta*<br/>
[içinde] *pTI*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCReBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

[içinde] *pTarget*<br/>
[içinde] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebarsetpanealignment"></a><a name="setpanealignment"></a>CMFCReBar::SetPaneAlignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

[içinde] *dwHizalama*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl Sınıfı](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane Sınıfı](../../mfc/reference/cpane-class.md)
