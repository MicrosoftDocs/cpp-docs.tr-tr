---
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
ms.openlocfilehash: abe10d764cb05f75bc6505a806b45452ee99635f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509402"
---
# <a name="cmfcdesktopalertdialog-class"></a>CMFCDesktopAlertDialog sınıfı

`CMFCDesktopAlertDialog` Sınıfı ile birlikte kullanılır [CMFCDesktopAlertWnd sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md) açılır pencerede özel bir iletişim kutusu görüntülenecek.

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

## <a name="syntax"></a>Sözdizimi

```
class CMFCDesktopAlertDialog : public CDialogEx
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCDesktopAlertDialog::CreateFromParams](#createfromparams)||
|[CMFCDesktopAlertDialog::GetDlgSize](#getdlgsize)||
|[CMFCDesktopAlertDialog::HasFocus](#hasfocus)||
|[CMFCDesktopAlertDialog::PreTranslateMessage](#pretranslatemessage)|(Geçersiz kılmaları `CDialogEx::PreTranslateMessage`.)|

### <a name="remarks"></a>Açıklamalar

Açılır pencerede özel bir iletişim kutusu görüntülemek için aşağıdaki adımları gerçekleştirin:

1. Öğesinden bir sınıf türetin `CMFCDesktopAlertDialog`.

1. Bir alt iletişim şablonu projesinin kaynakları oluşturun.

1. Çağrı [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) iletişim şablonu ve parametre olarak çalışma zamanı sınıf bilgileri türetilmiş sınıfın bir işaretçisi kaynak kimliği.

1. Bu bildirimleri doğrudan işlemek için barındırılan denetimleri program veya program barındırılan denetimlerden gönderilen tüm bildirimler işlemek için özel iletişim.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxDesktopAlertDialog.h

##  <a name="createfromparams"></a>  CMFCDesktopAlertDialog::CreateFromParams

```
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,
    CMFCDesktopAlertWnd* pParent);
```

### <a name="parameters"></a>Parametreler

[in] *params*<br/>

[in] *pParent*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getdlgsize"></a>  CMFCDesktopAlertDialog::GetDlgSize

```
CSize GetDlgSize();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="hasfocus"></a>  CMFCDesktopAlertDialog::HasFocus

```
BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="pretranslatemessage"></a>  CMFCDesktopAlertDialog::PreTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

[in] *pMsg*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd Sınıfı](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWndInfo Sınıfı](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CDialogEx Sınıfı](../../mfc/reference/cdialogex-class.md)
