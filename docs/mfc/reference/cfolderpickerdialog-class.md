---
title: CFolderPickerDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: f1718919a4fe9019ef591d83473c118eba966900
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276188"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog sınıfı

CFolderPickerDialog sınıfı Klasör Seçici modunda CFileDialog uygular.

## <a name="syntax"></a>Sözdizimi

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFolderPickerDialog:: ~ CFolderPickerDialog](#cfolderpickerdialog__~cfolderpickerdialog)|Yıkıcı.|
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdlgs.h

##  <a name="cfolderpickerdialog"></a>  CFolderPickerDialog::CFolderPickerDialog

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
Başlangıç klasörü.

*CertOpenStore*<br/>
Özelleştir iletişim kutusu olanak tanıyan bir veya daha fazla bayrakların birleşimi.

*pParentWnd*<br/>
İletişim kutusu nesnenin üst veya sahip penceresine bir işaretçi.

*dwSize*<br/>
LPSTRFİLE yapısı boyutu.

### <a name="remarks"></a>Açıklamalar

##  <a name="_dtorcfolderpickerdialog"></a>  CFolderPickerDialog:: ~ CFolderPickerDialog

Yıkıcı.

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar](../../mfc/reference/mfc-classes.md)
