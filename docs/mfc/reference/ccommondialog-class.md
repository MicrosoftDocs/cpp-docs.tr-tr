---
title: CCommonDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 4fa7aa51d1ce482e00f68365045cd35c3fb7939b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264878"
---
# <a name="ccommondialog-class"></a>CCommonDialog sınıfı

Windows ortak iletişim kutularının işlevlerini kapsayan sınıflar için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCommonDialog::CCommonDialog](#ccommondialog)|Oluşturur bir `CCommonDialog` nesne.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki sınıflar Windows ortak iletişim kutularının işlevi kapsülleyen:

- [CFileDialog](../../mfc/reference/cfiledialog-class.md)

- [CFontDialog](../../mfc/reference/cfontdialog-class.md)

- [CColorDialog](../../mfc/reference/ccolordialog-class.md)

- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)

- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)

- [COleDialog](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="ccommondialog"></a>  CCommonDialog::CCommonDialog

Oluşturur bir `CCommonDialog` nesne.

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
Üst veya sahibi pencere nesnesi için işaret (tür [CWnd](../../mfc/reference/cwnd-class.md)) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim nesnenin üst penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bkz: [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) eksiksiz bilgi.

## <a name="see-also"></a>Ayrıca bkz.

[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFileDialog Sınıfı](../../mfc/reference/cfiledialog-class.md)<br/>
[CFontDialog Sınıfı](../../mfc/reference/cfontdialog-class.md)<br/>
[CColorDialog Sınıfı](../../mfc/reference/ccolordialog-class.md)<br/>
[CPageSetupDialog Sınıfı](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[CPrintDialog Sınıfı](../../mfc/reference/cprintdialog-class.md)<br/>
[CFindReplaceDialog Sınıfı](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
