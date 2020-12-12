---
description: 'Daha fazla bilgi edinin: CCommonDialog sınıfı'
title: CCommonDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
ms.openlocfilehash: 927348982529f14eb0ad762019bb4463aaa77c99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227903"
---
# <a name="ccommondialog-class"></a>CCommonDialog sınıfı

Windows ortak iletişim kutularının işlevselliğini kapsülleyen sınıflar için temel sınıf.

## <a name="syntax"></a>Syntax

```
class CCommonDialog : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCommonDialog:: Ccommoniletişim kutusu](#ccommondialog)|Bir `CCommonDialog` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Aşağıdaki sınıflar Windows ortak iletişim kutularının işlevlerini kapsülleyebilirsiniz:

- [CFileDialog](../../mfc/reference/cfiledialog-class.md)

- [CFontDialog](../../mfc/reference/cfontdialog-class.md)

- [CColorDialog](../../mfc/reference/ccolordialog-class.md)

- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)

- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)

- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)

- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)

- [Colet Iletişim kutusu](../../mfc/reference/coledialog-class.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`CCommonDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

## <a name="ccommondialogccommondialog"></a><a name="ccommondialog"></a> CCommonDialog:: Ccommoniletişim kutusu

Bir `CCommonDialog` nesnesi oluşturur.

```
explicit CCommonDialog(CWnd* pParentWnd);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
İletişim nesnesinin ait olduğu üst veya sahip pencere nesnesine ( [CWnd](../../mfc/reference/cwnd-class.md)türü) işaret eder. NULL ise, iletişim kutusu nesnesinin ana penceresi ana uygulama penceresine ayarlanır.

### <a name="remarks"></a>Açıklamalar

Tüm bilgiler için bkz. [CDialog:: CDialog](../../mfc/reference/cdialog-class.md#cdialog) .

## <a name="see-also"></a>Ayrıca bkz.

[CDialog sınıfı](../../mfc/reference/cdialog-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFileDialog sınıfı](../../mfc/reference/cfiledialog-class.md)<br/>
[CFontDialog sınıfı](../../mfc/reference/cfontdialog-class.md)<br/>
[CColorDialog sınıfı](../../mfc/reference/ccolordialog-class.md)<br/>
[CPageSetupDialog sınıfı](../../mfc/reference/cpagesetupdialog-class.md)<br/>
[CPrintDialog sınıfı](../../mfc/reference/cprintdialog-class.md)<br/>
[CFindReplaceDialog sınıfı](../../mfc/reference/cfindreplacedialog-class.md)<br/>
[Coeldialog sınıfı](../../mfc/reference/coledialog-class.md)
