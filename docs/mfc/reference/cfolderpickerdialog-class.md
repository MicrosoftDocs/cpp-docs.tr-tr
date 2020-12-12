---
description: 'Daha fazla bilgi edinin: CFolderPickerDialog sınıfı'
title: CFolderPickerDialog sınıfı
ms.date: 03/27/2019
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: f4a5bcc3162a5fffcc723d7ec420685b02be10f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184432"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog sınıfı

CFolderPickerDialog sınıfı, Klasör Seçici modunda CFileDialog uygular.

## <a name="syntax"></a>Syntax

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#_dtorcfolderpickerdialog)|Yıkıcı.|
|[CFolderPickerDialog:: CFolderPickerDialog](#cfolderpickerdialog)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[Ccommoniletişim kutusu](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdlgs. h

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="cfolderpickerdialog"></a> CFolderPickerDialog:: CFolderPickerDialog

Oluşturucu.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>Parametreler

*lpszFolder*<br/>
İlk klasör.

*dwFlags*<br/>
İletişim kutusunu özelleştirmenizi sağlayan bir veya daha fazla bayrak birleşimi.

*pParentWnd*<br/>
İletişim kutusu nesnesinin üst veya sahip penceresine yönelik bir işaretçi.

*dwSize*<br/>
OPENFILENAME yapısının boyutu.

### <a name="remarks"></a>Açıklamalar

## <a name="cfolderpickerdialogcfolderpickerdialog"></a><a name="_dtorcfolderpickerdialog"></a> CFolderPickerDialog:: ~ CFolderPickerDialog

Yıkıcı.

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
