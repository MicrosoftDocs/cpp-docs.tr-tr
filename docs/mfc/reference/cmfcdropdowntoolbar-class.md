---
title: CMFCDropDownToolToolBar Sınıfı
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
ms.openlocfilehash: 68dd976471b39d7f50c2f0378b2fce99ad3feeca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367596"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolToolBar Sınıfı

Kullanıcı üst düzey bir araç çubuğu düğmesine bastığında ve tuttuğunda görünen araç çubuğu.

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDropDownToolBar::İzinShowOnPaneMenu](#allowshowonpanemenu)|(Geçersiz `CPane::AllowShowOnPaneMenu`kılar .)|
|[CMFCDropDownToolBar::LoadBitmap](#loadbitmap)|[(CMFCToolBar geçersiz kılar::LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap).)|
|[CMFCDropDownToolBar::loadtoolbar](#loadtoolbar)|[(Overrides CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar).)|
|[CMFCDropDownToolBar::OnlbuttonUp](#onlbuttonup)||
|[CMFCDropDownToolBar::Fare Taşı](#onmousemove)||
|[CMFCDropDownToolBar::OnSendCommand](#onsendcommand)|(Geçersiz `CMFCToolBar::OnSendCommand`kılar .)|
|[CMFCDropDownToolBar::OnUpdateCmdUI](#onupdatecmdui)|[(Overrides CMFCToolBar::OnUpdateCmdUI](cmfctoolbar-class.md).|

### <a name="remarks"></a>Açıklamalar

Nesne, `CMFCDropDownToolBar` araç çubuğunun görsel görünümünü açılır menü davranışıyla birleştirir. Bir kullanıcı açılır araç çubuğuna basıp tuttuğunda [(cmfcDropDropToolbarButton Class'a](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)bakınız), açılır araç çubuğu belirir ve kullanıcı açılan araç çubuğundan bir düğmeyi kaydırarak ve fare düğmesini serbest bırakarak seçebilir. Kullanıcı açılır araç çubuğunda bir düğme seçtikten sonra, bu düğme üst düzey araç çubuğundaki geçerli düğme olarak görüntülenir.

Açılan araç çubuğu özelleştirilemez veya sabitlenemez ve yırtılma durumu yoktur.

Aşağıdaki resimde bir `CMFCDropDownToolBar` nesne gösterilmektedir:

![CMFCDropDownToolbar örneği](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDownToolbar örneği")

Bir `CMFCDropDownToolBar` nesneyi, sıradan bir araç çubuğu oluşturduğunuz şekilde oluşturursunuz (bkz. [CMFCToolBar Class).](../../mfc/reference/cmfctoolbar-class.md)

Açılır araç çubuğunu üst araç çubuğuna eklemek için:

1. Ana araç çubuğu kaynağındaki düğme için sahte bir kaynak kimliği ayırın.

2. Açılır `CMFCDropDownToolBarButton` araç çubuğunu içeren bir nesne oluşturun (daha fazla bilgi için bkz. [CMFCDropDropToolbarButton::CMFCDropDropToolbarButton).](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)

3. CMFCToolBar kullanarak `CMFCDropDownToolBarButton` kukla düğmesini nesne ile [değiştirin::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Araç çubuğu düğmeleri hakkında daha fazla bilgi için [Bkz. Walkthrough: Denetimleri Araç Çubuklarına Koyma](../../mfc/walkthrough-putting-controls-on-toolbars.md). Açılan araç çubuğu örneği için, örnek proje VisualStudioDemo bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `Create` nasıl `CMFCDropDownToolBar` kullanılacağını göstermektedir. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#29](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#30](../../mfc/codesnippet/cpp/cmfcdropdowntoolbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[Cmfctoolbar](../../mfc/reference/cmfctoolbar-class.md)

[Cmfcdropdowntoolbar](../../mfc/reference/cmfcdropdowntoolbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCDropDownToolBar::İzinShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a>CMFCDropDownToolBar::LoadBitmap

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
[içinde] Sıcak araç çubuğu görüntülerine başvuran bit eşlemikaynak kimliği.

*uiColdResID*<br/>
[içinde] Bit eşleminin uçuk araç çubuğu görüntülerine atıfta bulunan kaynak kimliği.

*uiMenuResID*<br/>
[içinde] Normal menü görüntülerine başvuran bit eşlemikaynak kimliği.

*Engellenen*<br/>
[içinde] ARAÇ ÇUBUĞUNU kilitlemek için DOĞRU; aksi takdirde YANLIŞ.

*uiDisabledResID*<br/>
[içinde] Devre dışı bırakılan araç çubuğu görüntülerine başvuran bit eşlemikaynak kimliği.

*uiMenuDisabledResID*<br/>
[içinde] Devre dışı bırakılmış menü görüntülerine başvuran bit eşlemikaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) yöntemi, araç çubuğuyla ilişkili görüntüleri yüklemek için bu yöntemi çağırır. Görüntü kaynaklarının özel yüklemesini gerçekleştirmek için bu yöntemi geçersiz kılın.

Araç `LoadBitmapEx` çubuğunu oluşturduktan sonra ek görüntüler yüklemek için yöntemi arayın.

## <a name="cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a>CMFCDropDownToolBar::loadtoolbar

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

[içinde] *uiResID*<br/>

[içinde] *uiColdResID*<br/>

[içinde] *uiMenuResID*<br/>

[içinde] *BOOL*<br/>

[içinde] *uiDisabledResID*<br/>

[içinde] *uiMenuDisabledResID*<br/>

[içinde] *uiHotResID*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a>CMFCDropDownToolBar::OnlbuttonUp

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

[içinde] *nBayraklar*<br/>

[içinde] *nokta*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a>CMFCDropDownToolBar::Fare Taşı

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

[içinde] *nBayraklar*<br/>

[içinde] *nokta*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a>CMFCDropDownToolBar::OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDüğme*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCDropDownToolBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

[içinde] *pTarget*<br/>

[içinde] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar::Oluştur](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CMFCDropDownToolbarButton Sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[İzlenecek yol: Araç Çubuklarına Denetimler Yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
