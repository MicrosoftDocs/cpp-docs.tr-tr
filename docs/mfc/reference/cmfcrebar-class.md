---
title: CMFCReBar sınıfı
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
ms.openlocfilehash: d348cf7aac57ce213e4d3f602501d12cee8e20d8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505436"
---
# <a name="cmfcrebar-class"></a>CMFCReBar sınıfı

Bir `CMFCReBar` nesne, Rebar denetimleri için düzen, kalıcılık ve durum bilgilerini sağlayan bir denetim çubuğudur.
Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC\\atlmfc\\\\src MFC** klasöründe bulunan kaynak koduna bakın.
## <a name="syntax"></a>Sözdizimi

```
class CMFCReBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCReBar:: AddBar](#addbar)|Bir yeniden çubuğa bir bant ekler.|
|[CMFCReBar:: CalcFixedLayout](#calcfixedlayout)|( [CBasePane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).) öğesini geçersiz kılar|
|[CMFCReBar:: CanFloat](#canfloat)|( [CBasePane:: CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)) geçersiz kılar.|
|[CMFCReBar:: Create](#create)|Yeniden çubuk denetimini oluşturur ve `CMFCReBar` nesneye ekler.|
|[CMFCReBar:: EnableDocking](#enabledocking)|( [CBasePane:: Enabletakmayı](../../mfc/reference/cbasepane-class.md#enabledocking)geçersiz kılar.)|
|[CMFCReBar:: GetReBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar:: GetReBarCtrl](#getrebarctrl)|Temel alınan [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) ortak denetimine doğrudan erişim sağlar.|
|[CMFCReBar:: OnShowControlBarMenu](#onshowcontrolbarmenu)|( [CPane:: OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu)geçersiz kılar.)|
|[CMFCReBar:: OnToolHitTest](#ontoolhittest)|( [CWnd:: OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest)geçersiz kılar.)|
|[CMFCReBar:: OnUpdateCmdUI](#onupdatecmdui)|( [CBasePane:: OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar:: Setbölmesi hizalaması](#setpanealignment)|( [CBasePane:: Setbölmesi hizalamasını](../../mfc/reference/cbasepane-class.md#setpanealignment)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

Bir `CMFCReBar` nesne, çeşitli alt pencereler içerebilir. Bu, düzenleme kutularını, araç çubuklarını ve liste kutularını içerir. Yeniden çubuğu programlama yoluyla yeniden boyutlandırabilir veya Kullanıcı, kavrayıcı çubuğunu sürükleyerek yeniden boyutlandırabilir. Bir Rebar nesnesinin arka planını tercih ettiğiniz bir bit eşlemine de ayarlayabilirsiniz.

Bir çubuk nesnesi, bir araç çubuğu nesnesine benzer şekilde davranır. Bir Rebar denetimi bir veya daha fazla bant içerebilir ve her bant bir kavrayıcı çubuğu, bir bit eşlem, metin etiketi ve alt pencere içerebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCReBar` sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir. Örnek, bir Rebar denetiminin nasıl oluşturulduğunu ve bu denetimin nasıl bir bant ekleneceğini gösterir. Bant, dahili bir araç çubuğu olarak çalışır. Bu kod parçacığı, [Rebar test örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrebar. h

##  <a name="addbar"></a>CMFCReBar:: AddBar

Bir yeniden çubuğa bir bant ekler.

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
[in, out] Yeniden çubuğuna eklenecek alt pencereye yönelik bir işaretçi. Başvurulan nesne **WS_CHILD** pencere stiline sahip olmalıdır.

*pszText*<br/>
'ndaki Yeniden çubukta görüntülenecek metni belirtir. Metin, alt pencerenin bir parçası değil. Bunun yerine, yeniden çubuk üzerinde görüntülenir.

*PBMP*<br/>
[in, out] Yeniden çubuk arka planında görüntülenecek bit eşlemi belirtir.

*dwStyle*<br/>
'ndaki Bantta uygulanacak stili içerir. Bant stillerinin tüm listesi için, Windows SDK belgelerindeki `fStyle` [rebarbanınfo](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) yapısında Açıklama bölümüne bakın.

*Clrön*<br/>
'ndaki Yeniden çubuğun ön plan rengini temsil eder.

*clrBack*<br/>
'ndaki Yeniden çubuğun arka plan rengini temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Bant yeniden çubuğa başarıyla eklendiyse doğru; Aksi takdirde, FALSE.

##  <a name="create"></a>CMFCReBar:: Create

Rebar denetimini oluşturur ve [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) nesnesine iliştirir.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[in, out] Bu yeniden çubuk denetiminin üst penceresine yönelik bir işaretçi.

*dwCtrlStyle*<br/>
'ndaki Rebar denetiminin stilini belirtir. Varsayılan stil değeri, Rebar denetimindeki bitişik bantları ayırmak için dar çizgiler görüntüleyen **rbs_bandborders**' dir. Geçerli stillerin bir listesi için, Windows SDK belgelerindeki [Rebar Control Styles](/windows/win32/Controls/rebar-control-styles) bölümüne bakın.

*dwStyle*<br/>
'ndaki Rebar denetiminin pencere stili. Geçerli stillerin bir listesi için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*NID*<br/>
'ndaki Rebar 'in alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Yeniden çubuk başarıyla oluşturulduysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="getrebarctrl"></a>CMFCReBar:: GetReBarCtrl

Nesneler için `CReBarCtrl` `CMFCReBar` temeldeki ortak denetime doğrudan erişim sağlar.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan `CReBarCtrl` nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yeniden çubuğunuzu özelleştirirken, Windows Rebar ortak denetim işlevselliğinden faydalanmak için bu yöntemi çağırın.

##  <a name="calcfixedlayout"></a>CMFCReBar:: CalcFixedLayout

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

##  <a name="canfloat"></a>CMFCReBar:: CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="enabledocking"></a>CMFCReBar:: EnableDocking

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

'ndaki *dwDockStyle*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="getrebarbandinfosize"></a>CMFCReBar:: GetReBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onshowcontrolbarmenu"></a>CMFCReBar:: OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parametreler

'ndaki *CPoint*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="ontoolhittest"></a>CMFCReBar:: OnToolHitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Parametreler

'ndaki *nokta*<br/>
'ndaki *PTI*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onupdatecmdui"></a>CMFCReBar:: OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

'ndaki *pTarget*<br/>
'ndaki *Bdisableifnohndler*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="setpanealignment"></a>CMFCReBar:: Setbölmesi hizalaması

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

'ndaki *Dwhizalaması*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl Sınıfı](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane Sınıfı](../../mfc/reference/cpane-class.md)
