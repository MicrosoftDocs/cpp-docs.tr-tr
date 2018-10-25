---
title: CMFCReBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3b91d0397b1eec53988e7acd5a5b7dce61db4ec
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059889"
---
# <a name="cmfcrebar-class"></a>CMFCReBar sınıfı

A `CMFCReBar` düzen, süreklilik ve çubuk barınağı denetimleri için durum bilgileri sağlayan denetim çubuğu nesnedir.
Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.
## <a name="syntax"></a>Sözdizimi

```
class CMFCReBar : public CPane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCReBar::AddBar](#addbar)|Bir bant için bir çubuk barınağı ekler.|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Geçersiz kılmaları [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCReBar::CanFloat](#canfloat)|(Geçersiz kılmaları [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CMFCReBar::Create](#create)|Çubuk barınağı denetimi oluşturur ve ona ekler `CMFCReBar` nesne.|
|[CMFCReBar::EnableDocking](#enabledocking)|(Geçersiz kılmaları [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Arka plandaki doğrudan erişim sağlayan [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) ortak denetimi.|
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Geçersiz kılmaları [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Geçersiz kılmaları [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Geçersiz kılmaları [CBasePane::OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Geçersiz kılmaları [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>Açıklamalar

A `CMFCReBar` nesne alt pencereleri çeşitli içerebilir. Bu, liste kutuları düzenleme kutuları ve araç çubuklarını içerir. Çubuk barınağı programlı bir şekilde boyutlandırabilirsiniz veya kullanıcı el ile çubuk barınağı kavrayıcı çubuğunu sürükleyerek yeniden boyutlandırabilirsiniz. Bir rebar nesnenin arka plan için seçtiğiniz bir bit eşlem de ayarlayabilirsiniz.

Bir rebar nesnesi bir araç çubuğu nesnesi için benzer şekilde davranır. Rebar denetimi bir veya daha fazla bant içerebilir ve her bant kavrayıcı çubuğu, bir bit eşlem, bir metin etiketi ve alt pencerenin içerebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çeşitli yöntemlerin nasıl kullanılacağını gösterir `CMFCReBar` sınıfı. Rebar denetimi oluşturma ve bir bant ekleyin örnek gösterir. Bant, iç bir araç işlev görür. Bu kod parçacığı parçasıdır [Rebar Test örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxRebar.h

##  <a name="addbar"></a>  CMFCReBar::AddBar

Bir bant için bir çubuk barınağı ekler.

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
[out içinde] Çubuk barınağı eklenecek olan alt penceresine bir işaretçi. Başvurulan nesnenin olmalıdır **WS_CHILD** pencere stili.

*pszText*<br/>
[in] Çubuk barınağı görüntülenecek metni belirtir. Metin alt pencere bir parçası değil. Bunun yerine, rebar üzerinde görüntülenir.

*pbmp*<br/>
[out içinde] Çubuk barınağı arka plan üzerinde görüntülenecek bit eşlem belirtir.

*dwStyle*<br/>
[in] Bant için uygulanacak stili içerir. Açıklaması bant stilleri tam bir listesi için bkz. `fStyle` içinde [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) yapısındaki Windows SDK Belgeleri.

*clrFore*<br/>
[in] Çubuk barınağı ön plan rengi temsil eder.

*clrBack*<br/>
[in] Çubuk barınağı arka plan rengi temsil eder.

### <a name="return-value"></a>Dönüş Değeri

Bant için çubuk barınağı başarıyla eklenmişse TRUE; Aksi takdirde FALSE.

##  <a name="create"></a>  CMFCReBar::Create

Çubuk barınağı denetimi oluşturur ve ona ekler [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) nesne.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[out içinde] Bu çubuk barınağı denetiminin üst penceresine bir işaretçi.

*dwCtrlStyle*<br/>
[in] Çubuk barınağı denetiminin stilini belirtir. Varsayılan Stil değer **RBS_BANDBORDERS**, hangi daraltmak çubuk barınağı denetimi bitişik bantları ayırmak için satır görüntüler. Geçerli stilleri bir listesi için bkz. [Rebar denetim stilleri](/windows/desktop/Controls/rebar-control-styles) Windows SDK belgelerinde.

*dwStyle*<br/>
[in] Çubuk barınağı denetiminin pencere stili. Geçerli stilleri bir listesi için bkz. [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*nID*<br/>
[in] Barınağının alt penceresi kimliği

### <a name="return-value"></a>Dönüş Değeri

Çubuk barınağı başarıyla oluşturulursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl

Doğrudan erişim sağlayan `CReBarCtrl` temel alınan bir ortak denetimi için `CMFCReBar` nesneleri.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel bir başvuru `CReBarCtrl` nesne.

### <a name="remarks"></a>Açıklamalar

Windows çubuk barınağı ortak denetim işlevlerini, çubuk barınağı özelleştirirken yararlanmak için bu yöntemi çağırın.

##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

[in] *bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="canfloat"></a>  CMFCReBar::CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parametreler

[in] *dwDockStyle*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parametreler

[in] *CPoint*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Parametreler

[in] *noktası*<br/>
[in] *PTI*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

[in] *pTarget*<br/>
[in] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Parametreler

[in] *dwAlignment*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl Sınıfı](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane Sınıfı](../../mfc/reference/cpane-class.md)
