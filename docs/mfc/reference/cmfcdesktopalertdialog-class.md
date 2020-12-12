---
description: 'Daha fazla bilgi edinin: CMFCDesktopAlertDialog sınıfı'
title: CMFCDesktopAlertDialog sınıfı
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
ms.openlocfilehash: 327ec72b1e58d90e768f51c083ff9545f24f6f0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193194"
---
# <a name="cmfcdesktopalertdialog-class"></a>CMFCDesktopAlertDialog sınıfı

`CMFCDesktopAlertDialog`Sınıf, bir açılan pencerede özel bir iletişim kutusu göstermek Için [CMFCDesktopAlertWnd sınıfıyla](../../mfc/reference/cmfcdesktopalertwnd-class.md) birlikte kullanılır.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCDesktopAlertDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertDialog:: CreateFromParams](#createfromparams)||
|[CMFCDesktopAlertDialog:: Getdlsize](#getdlgsize)||
|[CMFCDesktopAlertDialog:: HasFocus](#hasfocus)||
|[CMFCDesktopAlertDialog::P reTranslateMessage](#pretranslatemessage)|(Geçersiz kılmalar `CDialogEx::PreTranslateMessage` .)|

### <a name="remarks"></a>Açıklamalar

Açılan pencerede özel bir iletişim kutusu göstermek için aşağıdaki adımları gerçekleştirin:

1. Sınıfından bir sınıf türet `CMFCDesktopAlertDialog` .

1. Projenin kaynaklarında bir alt iletişim kutusu şablonu oluşturun.

1. İletişim kutusu şablonunun kaynak KIMLIĞIYLE [CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) ' i çağırın ve türetilmiş sınıfın çalışma zamanı sınıfı bilgilerine parametre olarak bir işaretçi koyun.

1. Barındırılan denetimlerden gelen tüm bildirimleri işlemek için özel iletişim kutusunu programlama veya barındırılan denetimleri bu bildirimleri doğrudan işleyecek şekilde programlama.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDesktopAlertDialog. h

## <a name="cmfcdesktopalertdialogcreatefromparams"></a><a name="createfromparams"></a> CMFCDesktopAlertDialog:: CreateFromParams

```
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,
    CMFCDesktopAlertWnd* pParent);
```

### <a name="parameters"></a>Parametreler

'ndaki *params*<br/>

'ndaki *pParent*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertdialoggetdlgsize"></a><a name="getdlgsize"></a> CMFCDesktopAlertDialog:: Getdlsize

```
CSize GetDlgSize();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertdialoghasfocus"></a><a name="hasfocus"></a> CMFCDesktopAlertDialog:: HasFocus

```
BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcdesktopalertdialogpretranslatemessage"></a><a name="pretranslatemessage"></a> CMFCDesktopAlertDialog::P reTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

'ndaki *pMsg*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[Cmfcdesktopalertwnınfo sınıfı](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CDialogEx sınıfı](../../mfc/reference/cdialogex-class.md)
