---
title: CMFCDesktopAlertDialog Sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::CreateFromParams
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::GetDlgSize
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::HasFocus
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::PreTranslateMessage
helpviewer_keywords:
- CMFCDesktopAlertDialog [MFC], CreateFromParams
- CMFCDesktopAlertDialog [MFC], GetDlgSize
- CMFCDesktopAlertDialog [MFC], HasFocus
- CMFCDesktopAlertDialog [MFC], PreTranslateMessage
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
ms.openlocfilehash: 479959e9b021255e309caf6fee02588a8cd8f1d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367649"
---
# <a name="cmfcdesktopalertdialog-class"></a>CMFCDesktopAlertDialog Sınıfı

Sınıf, `CMFCDesktopAlertDialog` açılan pencerede özel bir iletişim kutusu görüntülemek için [CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md) ile birlikte kullanılır.

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDesktopAlertDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertDialog::CreateFromParams](#createfromparams)||
|[CMFCDesktopAlertDialog::GetDlgSize](#getdlgsize)||
|[CMFCDesktopAlertDialog::HasFocus](#hasfocus)||
|[CMFCDesktopAlertDialog::PreTranslateMessage](#pretranslatemessage)|(Geçersiz `CDialogEx::PreTranslateMessage`kılar .)|

### <a name="remarks"></a>Açıklamalar

Açılan pencerede özel bir iletişim kutusu görüntülemek için aşağıdaki adımları gerçekleştirin:

1. Bir sınıf türetmek `CMFCDesktopAlertDialog`.

1. Projenin kaynaklarında bir alt iletişim şablonu oluşturun.

1. [CMFCDesktopAlertWnd'i arayın::İletişim](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) şablonunun kaynak kimliği ve parametre olarak türemiş sınıfın çalışma zamanı sınıf bilgilerine işaretçisi ile oluşturun.

1. Barındırılan denetimlerden gelen tüm bildirimleri işlemek için özel iletişim kutusunu programla veya bu bildirimleri doğrudan işlemek için barındırılan denetimleri programla.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDesktopAlertDialog.h

## <a name="cmfcdesktopalertdialogcreatefromparams"></a><a name="createfromparams"></a>CMFCDesktopAlertDialog::CreateFromParams

```
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,
    CMFCDesktopAlertWnd* pParent);
```

### <a name="parameters"></a>Parametreler

[içinde] *params*<br/>

[içinde] *pParent*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertdialoggetdlgsize"></a><a name="getdlgsize"></a>CMFCDesktopAlertDialog::GetDlgSize

```
CSize GetDlgSize();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertdialoghasfocus"></a><a name="hasfocus"></a>CMFCDesktopAlertDialog::HasFocus

```
BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertdialogpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCDesktopAlertDialog::PreTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

[içinde] *pMsg*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd Sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWndInfo Sınıfı](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CDialogEx Sınıfı](../../mfc/reference/cdialogex-class.md)
