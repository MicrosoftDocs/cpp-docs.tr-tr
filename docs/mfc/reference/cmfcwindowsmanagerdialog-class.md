---
title: CMFCWindowsManagerDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: 67fbd1ed066b47cdedf1b5ea2952b042c69bd978
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554316"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog sınıfı

`CMFCWindowsManagerDialog` Bir MDI uygulamasında MDI alt pencereleri yönetmek bir kullanıcı nesnesi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Oluşturur bir `CMFCWindowsManagerDialog` nesne.|

## <a name="remarks"></a>Açıklamalar

`CMFCWindowsManagerDialog` Uygulamada açık olan MDI alt pencereleri listesini içerir. Kullanıcı, bu iletişim kutusunu kullanarak MDI alt pencereleri durumunu el ile denetleyebilirsiniz.

`CMFCWindowsManagerDialog` içinde katıştırılmış [Cmdıframewndex sınıfı](../../mfc/reference/cmdiframewndex-class.md). `CMFCWindowsManagerDialog` El ile oluşturması gereken bir sınıf değil. Bunun yerine, işlev çağrısı [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), oluşturmak ve görüntülemek ve bir `CMFCWindowsManagerDialog` nesne.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCWindowsManagerDialog` çağırarak `CMDIFrameWndEx::ShowWindowsDialog`. Bu kod parçacığı parçasıdır [Visual Studio gösterim örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxWindowsManagerDialog.h

##  <a name="cmfcwindowsmanagerdialog"></a>  CMFCWindowsManagerDialog::CMFCWindowsManagerDialog

Oluşturur bir [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) nesne.

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>Parametreler

*pMDIFrame*<br/>
[in] Üst veya sahip penceresine bir işaretçi.

*bHelpButton*<br/>
[in] Framework görüntülenip görüntülenmeyeceğini belirten bir Boole parametresi bir **yardımcı** düğmesi.

### <a name="remarks"></a>Açıklamalar

Görsel Yöneticiler hakkında daha fazla bilgi için bkz: [seri hale getirme Yöneticisi](../../mfc/visualization-manager.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMDIFrameWndEx Sınıfı](../../mfc/reference/cmdiframewndex-class.md)
