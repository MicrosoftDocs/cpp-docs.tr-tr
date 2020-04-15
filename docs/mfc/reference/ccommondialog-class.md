---
title: CCommonDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 853a4756df3b70f4f33deb7159b4d1aee610092c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369441"
---
# <a name="ccommondialog-class"></a>CCommonDialog Sınıfı

Windows ortak iletişim iletişim lerinin işlevselliğini kapsülleyen sınıflar için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCommonDialog::CCommonDialog](#ccommondialog)|Bir `CCommonDialog` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki sınıflar Windows ortak iletişim iletişim lerinin işlevselliğini kapsüller:

- [Cfiledialog](../../mfc/reference/cfiledialog-class.md)

- [Cfontdialog](../../mfc/reference/cfontdialog-class.md)

- [Ccolordialog](../../mfc/reference/ccolordialog-class.md)

- [Cpagesetupdialog](../../mfc/reference/cpagesetupdialog-class.md)

- [Cprintdialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [Cfindreplacedialog](../../mfc/reference/cfindreplacedialog-class.md)

- [COleDialog](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="ccommondialogccommondialog"></a><a name="ccommondialog"></a>CCommonDialog::CCommonDialog

Bir `CCommonDialog` nesne inşa eder.

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip penceresi nesnesine [(CWnd](../../mfc/reference/cwnd-class.md)türünden) işaret eder. NULL ise, iletişim nesnesinin üst penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Bkz. [CDialog::Tam](../../mfc/reference/cdialog-class.md#cdialog) bilgi için CDialog.

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
