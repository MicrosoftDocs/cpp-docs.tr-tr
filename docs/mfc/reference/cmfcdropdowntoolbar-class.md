---
title: CMFCDropDownToolBar sınıfı
ms.date: 11/19/2018
f1_keywords:
- CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::AllowShowOnPaneMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadBitmap
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::LoadToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnLButtonUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnMouseMove
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnSendCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolBar::OnUpdateCmdUI
helpviewer_keywords:
- CMFCDropDownToolBar [MFC], AllowShowOnPaneMenu
- CMFCDropDownToolBar [MFC], LoadBitmap
- CMFCDropDownToolBar [MFC], LoadToolBar
- CMFCDropDownToolBar [MFC], OnLButtonUp
- CMFCDropDownToolBar [MFC], OnMouseMove
- CMFCDropDownToolBar [MFC], OnSendCommand
- CMFCDropDownToolBar [MFC], OnUpdateCmdUI
ms.assetid: 78818ec5-83ce-42fa-a0d4-2d9d5ecc8770
ms.openlocfilehash: f2c4135d2a27928dbde4299fa1f8eda42237d893
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776797"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar sınıfı

Kullanıcı bir üst düzey araç çubuğu düğmesini basılı tuttuğunda görünen bir araç çubuğu.

   Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.
## <a name="syntax"></a>Sözdizimi

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDropDownToolBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Geçersiz kılmaları `CPane::AllowShowOnPaneMenu`.)|
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|(Geçersiz kılmaları [CMFCToolBar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|
|[CMFCDropDownToolBar::LoadToolBar](#loadtoolbar)|(Geçersiz kılmaları [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar).)|
|[CMFCDropDownToolBar::OnLButtonUp](#onlbuttonup)||
|[CMFCDropDownToolBar::OnMouseMove](#onmousemove)||
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|(Geçersiz kılmaları `CMFCToolBar::OnSendCommand`.)|
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|(Geçersiz kılmaları [CMFCToolBar::OnUpdateCmdUI](cmfctoolbar-class.md).|

### <a name="remarks"></a>Açıklamalar

A `CMFCDropDownToolBar` nesne ile bir açılan menü davranışını bir araç çubuğu görsel görünümünü birleştirir. Ne zaman bir kullanıcının bastığında ve bir açılır araç çubuğu düğmesini (bkz [CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), aşağı açılan araç çubuğu görünür ve kullanıcı bir düğme açılan araç çubuğundan için kaydırma ve fare düğmesini bırakmadan seçebilirsiniz düğmesi. Kullanıcının açılan araç çubuğunda bir düğmeyi seçtiğinde sonra bu düğme olarak geçerli bir üst düzey araç çubuğunda görüntülenir.

Bir açılır araç çubuğunu özelleştirilmiş veya yerleştirilmiş olamaz ve etkinleştiriliyorken durumu yok.

Aşağıdaki çizimde gösterildiği bir `CMFCDropDownToolBar` nesnesi:

![CMFCDropDownToolbar örneği](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDownToolbar örneği")

Oluşturduğunuz bir `CMFCDropDownToolBar` sıradan bir araç çubuğu oluşturma aynı şekilde nesnesi (bkz [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)).

Üst araç çubuğuna açılan araç çubuğu eklemek için:

1. Üst araç çubuğunda kaynağında düğme için bir işlevsiz kaynak kimliği saklı tutarız.

2. Oluşturma bir `CMFCDropDownToolBarButton` açılan araç çubuğu içeren nesne (daha fazla bilgi için [CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).

3. İşlevsiz bir düğmeyle değiştirin `CMFCDropDownToolBarButton` kullanarak nesne [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Araç çubuğu düğmeleri hakkında daha fazla bilgi için bkz: [izlenecek yol: Araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md). Örnek Proje VisualStudioDemo bir açılır araç çubuğunu örneği için bkz.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `Create` yönteminde `CMFCDropDownToolBar` sınıfı. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdropdowntoolbar.h

##  <a name="allowshowonpanemenu"></a>  CMFCDropDownToolBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="loadbitmap"></a>  CMFCDropDownToolBar::LoadBitmap

Araç çubuğu görüntülerini uygulama kaynaklarından yükler.

```
virtual BOOL LoadBitmap(
    UINT uiResID,
    UINT uiColdResID=0,
    UINT uiMenuResID=0,
    BOOL bLocked=FALSE,
    UINT uiDisabledResID=0,
    UINT uiMenuDisabledResID=0);
```

### <a name="parameters"></a>Parametreler

*uiResID*<br/>
[in] Etkin araç çubuğu görüntülerini başvuran bir bit eşlem kaynak kimliği.

*uiColdResID*<br/>
[in] Soğuk araç görüntülere başvuruyor bit eşlemi kaynak kimliği.

*uiMenuResID*<br/>
[in] Normal menü görüntülere başvuruyor bit eşlemi kaynak kimliği.

*Engellendi*<br/>
[in] Araç kilitlemek için TRUE; Aksi durumda FALSE.

*uiDisabledResID*<br/>
[in] Devre dışı araç görüntülere başvuruyor bit eşlemi kaynak kimliği.

*uiMenuDisabledResID*<br/>
[in] Devre dışı bırakılmış menü görüntülere başvuruyor bit eşlemi kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

[CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) yöntemi araç ile ilişkili görüntü yüklemek için bu yöntemi çağırır. Özel resim kaynakları yüklemesini gerçekleştirmek için bu yöntemi yok sayın.

Çağrı `LoadBitmapEx` araç oluşturduktan sonra ek resimleri yüklemek için yöntemi.

##  <a name="loadtoolbar"></a>  CMFCDropDownToolBar::LoadToolBar

```
virtual BOOL LoadToolBar(
    UINT uiResID,
    UINT uiColdResID = 0,
    UINT uiMenuResID = 0,
    BOOL = FALSE,
    UINT uiDisabledResID = 0,
    UINT uiMenuDisabledResID = 0,
    UINT uiHotResID = 0);
```

### <a name="parameters"></a>Parametreler

[in] *uiResID*<br/>

[in] *uiColdResID*<br/>

[in] *uiMenuResID*<br/>

[in] *BOOL*<br/>

[in] *uiDisabledResID*<br/>

[in] *uiMenuDisabledResID*<br/>

[in] *uiHotResID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onlbuttonup"></a>  CMFCDropDownToolBar::OnLButtonUp

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

[in] *nFlags*<br/>

[in] *noktası*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="onmousemove"></a>  CMFCDropDownToolBar::OnMouseMove

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

[in] *nFlags*<br/>

[in] *noktası*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="onsendcommand"></a>  CMFCDropDownToolBar::OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parametreler

[in] *pButton*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="onupdatecmdui"></a>  CMFCDropDownToolBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

[in] *pTarget*<br/>

[in] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar::Create](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[İzlenecek yol: Araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
