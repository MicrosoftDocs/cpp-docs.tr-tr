---
title: CFolderPickerDialog Sınıfı
ms.date: 03/27/2019
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: ed3dc151060519bce216cf4a2f3d6559d6b8937e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373865"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog Sınıfı

CFolderPickerDialog sınıfı klasör seçici modunda CFileDialog uygular.

## <a name="syntax"></a>Sözdizimi

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFolderPickerDialog::~CFolderPickerDialog](#_dtorcfolderpickerdialog)|Yıkıcı.|
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[Cfiledialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs.h

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="cfolderpickerdialog"></a>CFolderPickerDialog::CFolderPickerDialog

Oluşturucu.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>Parametreler

*lpszKlasör*<br/>
İlk klasör.

*Dwflags*<br/>
İletişim kutusunu özelleştirmenize olanak tanıyan bir veya daha fazla bayrağın birleşimi.

*pParentWnd*<br/>
İletişim kutusu nesnesinin üst veya sahibi penceresiiçin bir işaretçi.

*dwSize*<br/>
OPENFILENAME yapısının boyutu.

### <a name="remarks"></a>Açıklamalar

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="_dtorcfolderpickerdialog"></a>CFolderPickerDialog::~CFolderPickerDialog

Yıkıcı.

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
