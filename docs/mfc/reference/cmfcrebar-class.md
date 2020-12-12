---
description: 'Daha fazla bilgi edinin: CMFCReBar sınıfı'
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
ms.openlocfilehash: fcfad39ddb9c5f3bdacc5a06ebb65d22bc8c7a4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289835"
---
# <a name="cmfcrebar-class"></a>CMFCReBar sınıfı

Bir `CMFCReBar` nesne, Rebar denetimleri için düzen, kalıcılık ve durum bilgilerini sağlayan bir denetim çubuğudur.
Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

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

Aşağıdaki örnek, sınıfında çeşitli yöntemlerin nasıl kullanıldığını gösterir `CMFCReBar` . Örnek, bir Rebar denetiminin nasıl oluşturulduğunu ve bu denetimin nasıl bir bant ekleneceğini gösterir. Bant, dahili bir araç çubuğu olarak çalışır. Bu kod parçacığı, [Rebar test örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)\
└ &nbsp; [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrebar. h

## <a name="cmfcrebaraddbar"></a><a name="addbar"></a> CMFCReBar:: AddBar

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
[in, out] Yeniden çubuğuna eklenecek alt pencereye yönelik bir işaretçi. Başvurulan nesnenin **WS_CHILD** pencere stili olmalıdır.

*pszText*<br/>
'ndaki Yeniden çubukta görüntülenecek metni belirtir. Metin, alt pencerenin bir parçası değil. Bunun yerine, yeniden çubuk üzerinde görüntülenir.

*PBMP*<br/>
[in, out] Yeniden çubuk arka planında görüntülenecek bit eşlemi belirtir.

*dwStyle*<br/>
'ndaki Bantta uygulanacak stili içerir. Bant stillerinin tüm listesi için, `fStyle` Windows SDK belgelerindeki [Rebarbanınfo](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) yapısında Açıklama bölümüne bakın.

*Clrön*<br/>
'ndaki Yeniden çubuğun ön plan rengini temsil eder.

*clrBack*<br/>
'ndaki Yeniden çubuğun arka plan rengini temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Bant yeniden çubuğa başarıyla eklendiyse doğru; Aksi takdirde, FALSE.

## <a name="cmfcrebarcreate"></a><a name="create"></a> CMFCReBar:: Create

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
'ndaki Rebar denetiminin stilini belirtir. Varsayılan stil değeri, Rebar denetiminde bitişik bantların ayrılması için dar çizgileri görüntüleyen **rbs_bandborders**. Geçerli stillerin bir listesi için, Windows SDK belgelerindeki [Rebar Control Styles](/windows/win32/Controls/rebar-control-styles) bölümüne bakın.

*dwStyle*<br/>
'ndaki Rebar denetiminin pencere stili. Geçerli stillerin bir listesi için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*NID*<br/>
'ndaki Rebar 'in alt pencere KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Yeniden çubuk başarıyla oluşturulduysa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebargetrebarctrl"></a><a name="getrebarctrl"></a> CMFCReBar:: GetReBarCtrl

`CReBarCtrl`Nesneler için temeldeki ortak denetime doğrudan erişim sağlar `CMFCReBar` .

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan nesneye bir başvuru `CReBarCtrl` .

### <a name="remarks"></a>Açıklamalar

Yeniden çubuğunuzu özelleştirirken, Windows Rebar ortak denetim işlevselliğinden faydalanmak için bu yöntemi çağırın.

## <a name="cmfcrebarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCReBar:: CalcFixedLayout

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

## <a name="cmfcrebarcanfloat"></a><a name="canfloat"></a> CMFCReBar:: CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebarenabledocking"></a><a name="enabledocking"></a> CMFCReBar:: EnableDocking

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

'ndaki *dwDockStyle*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebargetrebarbandinfosize"></a><a name="getrebarbandinfosize"></a> CMFCReBar:: GetReBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a> CMFCReBar:: OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parametreler

'ndaki *CPoint*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebarontoolhittest"></a><a name="ontoolhittest"></a> CMFCReBar:: OnToolHitTest

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

## <a name="cmfcrebaronupdatecmdui"></a><a name="onupdatecmdui"></a> CMFCReBar:: OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

'ndaki *pTarget*<br/>
'ndaki *Bdisableifnohndler*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcrebarsetpanealignment"></a><a name="setpanealignment"></a> CMFCReBar:: Setbölmesi hizalaması

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

'ndaki *Dwhizalaması*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl sınıfı](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane sınıfı](../../mfc/reference/cpane-class.md)
