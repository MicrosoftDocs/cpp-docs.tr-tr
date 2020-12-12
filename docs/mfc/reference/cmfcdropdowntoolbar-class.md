---
description: 'Daha fazla bilgi edinin: CMFCDropDownToolBar sınıfı'
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
ms.openlocfilehash: 158562829cb5bbebfb9a858d34751c56bdf46ed8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293995"
---
# <a name="cmfcdropdowntoolbar-class"></a>CMFCDropDownToolBar sınıfı

Kullanıcı üst düzey bir araç çubuğu düğmesine bastığında ve bu düğmeyi tutuyorsa görüntülenen bir araç çubuğu.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCDropDownToolBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDropDownToolBar:: Allowshowonbölmesi menüsü](#allowshowonpanemenu)|(Geçersiz kılmalar `CPane::AllowShowOnPaneMenu` .)|
|[CMFCDropDownToolBar:: LoadBitmap](#loadbitmap)|( [CMFCToolBar:: LoadBitmap](../../mfc/reference/cmfctoolbar-class.md#loadbitmap)'i geçersiz kılar.)|
|[CMFCDropDownToolBar:: LoadToolBar](#loadtoolbar)|( [CMFCToolBar:: LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar)'ı geçersiz kılar.)|
|[CMFCDropDownToolBar:: OnLButtonUp](#onlbuttonup)||
|[CMFCDropDownToolBar:: OnMouseMove](#onmousemove)||
|[CMFCDropDownToolBar:: OnSendCommand](#onsendcommand)|(Geçersiz kılmalar `CMFCToolBar::OnSendCommand` .)|
|[CMFCDropDownToolBar:: OnUpdateCmdUI](#onupdatecmdui)|( [CMFCToolBar:: OnUpdateCmdUI](cmfctoolbar-class.md)geçersiz kılar.|

### <a name="remarks"></a>Açıklamalar

Bir `CMFCDropDownToolBar` nesne, bir araç çubuğunun görsel görünümünü bir açılan menünün davranışıyla birleştirir. Bir Kullanıcı bir açılan araç çubuğu düğmesine bastığında ve tutuyorsa (bkz. [CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)), açılan bir araç çubuğu görüntülenir ve Kullanıcı, fare düğmesini bırakarak açılan araç çubuğundan bir düğme seçebilir. Kullanıcı açılan araç çubuğunda bir düğme seçtikten sonra, bu düğme üst düzey araç çubuğunda geçerli düğme olarak görüntülenir.

Açılan bir araç çubuğu özelleştirilemez veya sabitlenemez ve bir koparma durumuna sahip değildir.

Aşağıdaki çizimde bir nesne gösterilmektedir `CMFCDropDownToolBar` :

![CMFCDropDownToolbar örneği](../../mfc/reference/media/cmfcdropdown.png "CMFCDropDownToolbar örneği")

`CMFCDropDownToolBar`Sıradan bir araç çubuğu oluşturduğunuz şekilde bir nesne oluşturursunuz (bkz. [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)).

Açılan araç çubuğunu bir üst araç çubuğuna eklemek için:

1. Ana araç çubuğu kaynağında düğme için bir kukla kaynak KIMLIĞI ayırın.

2. `CMFCDropDownToolBarButton`Açılan araç çubuğunu içeren bir nesne oluşturun (daha fazla bilgi için bkz. [CMFCDropDownToolbarButton:: CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md#cmfcdropdowntoolbarbutton)).

3. `CMFCDropDownToolBarButton` [CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)öğesini kullanarak kukla düğmesini nesneyle değiştirin.

Araç çubuğu düğmeleri hakkında daha fazla bilgi için bkz. [Izlenecek yol: denetimleri araç çubuklarına yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md). Açılan araç çubuğuna bir örnek için bkz. VisualStudioDemo Sample Project.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yönteminin nasıl kullanılacağını gösterir `Create` `CMFCDropDownToolBar` . Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

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

**Üstbilgi:** afxdropdowntoolbar. h

## <a name="cmfcdropdowntoolbarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a> CMFCDropDownToolBar:: Allowshowonbölmesi menüsü

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbarloadbitmap"></a><a name="loadbitmap"></a> CMFCDropDownToolBar:: LoadBitmap

Uygulama kaynaklarından araç çubuğu görüntülerini yükler.

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

*Uırestıd*<br/>
'ndaki Etkin araç çubuğu görüntülerine başvuran bit eşlemin kaynak KIMLIĞI.

*Uııoldresd*<br/>
'ndaki Soğuk araç çubuğu görüntülerine başvuran bit eşlemin kaynak KIMLIĞI.

*Uııd*<br/>
'ndaki Normal menü görüntülerine başvuran bit eşlemin kaynak KIMLIĞI.

*engellendiğini*<br/>
'ndaki Araç çubuğunu kilitlemek için TRUE; Aksi halde yanlış.

*Uıdisabledresd*<br/>
'ndaki Devre dışı araç çubuğu görüntülerine başvuran bit eşlemin kaynak KIMLIĞI.

*Uıımtrıg*<br/>
'ndaki Devre dışı menü görüntülerine başvuran bit eşlemin kaynak KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CMFCToolBar:: LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) yöntemi, araç çubuğuyla ilişkili görüntüleri yüklemek için bu yöntemi çağırır. Görüntü kaynaklarının özel yükleme işlemini gerçekleştirmek için bu yöntemi geçersiz kılın.

`LoadBitmapEx`Araç çubuğunu oluşturduktan sonra ek görüntüleri yüklemek için yöntemini çağırın.

## <a name="cmfcdropdowntoolbarloadtoolbar"></a><a name="loadtoolbar"></a> CMFCDropDownToolBar:: LoadToolBar

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

'ndaki *Uırestıd*<br/>

'ndaki *Uııoldresd*<br/>

'ndaki *Uııd*<br/>

'ndaki *Bool*<br/>

'ndaki *Uıdisabledresd*<br/>

'ndaki *Uıımtrıg*<br/>

'ndaki *Uıhotresd*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbaronlbuttonup"></a><a name="onlbuttonup"></a> CMFCDropDownToolBar:: OnLButtonUp

```
afx_msg void OnLButtonUp(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

'ndaki *nFlags*<br/>

'ndaki *nokta*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbaronmousemove"></a><a name="onmousemove"></a> CMFCDropDownToolBar:: OnMouseMove

```
afx_msg void OnMouseMove(
    UINT nFlags,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

'ndaki *nFlags*<br/>

'ndaki *nokta*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbaronsendcommand"></a><a name="onsendcommand"></a> CMFCDropDownToolBar:: OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parametreler

'ndaki *pButton*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdropdowntoolbaronupdatecmdui"></a><a name="onupdatecmdui"></a> CMFCDropDownToolBar:: OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

'ndaki *pTarget*<br/>

'ndaki *Bdisableifnohndler*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBar:: Create](../../mfc/reference/cmfctoolbar-class.md#create)<br/>
[CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[CMFCDropDownToolbarButton sınıfı](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)<br/>
[İzlenecek yol: araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)
