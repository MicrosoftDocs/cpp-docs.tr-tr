---
description: 'Daha fazla bilgi edinin: CMFCWindowsManagerDialog sınıfı'
title: CMFCWindowsManagerDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: 526cf731e049ffd267382b0c3895b5d29792dcb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331624"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog sınıfı

`CMFCWindowsManagerDialog`Nesnesi BIR MDI uygulamasında bir kullanıcının MDI alt pencerelerini yönetmesine olanak sağlar.

## <a name="syntax"></a>Syntax

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCWindowsManagerDialog:: CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Bir `CMFCWindowsManagerDialog` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

, `CMFCWindowsManagerDialog` Uygulamada açık olan MDI alt pencerelerinin bir listesini içerir. Kullanıcı, bu iletişim kutusunu kullanarak MDI alt pencerelerinin durumunu el ile denetleyebilir.

`CMFCWindowsManagerDialog` , [Cmdiframewndex sınıfının](../../mfc/reference/cmdiframewndex-class.md)içine katıştırılır. , `CMFCWindowsManagerDialog` El ile oluşturmanız gereken bir sınıf değildir. Bunun yerine, [CMDIFrameWndEx:: ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)işlevini çağırın ve bir nesnesi oluşturur ve görüntüler `CMFCWindowsManagerDialog` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, çağırarak bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCWindowsManagerDialog` `CMDIFrameWndEx::ShowWindowsDialog` . Bu kod parçacığı, [Visual Studio Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwindowsmanagerdialog. h

## <a name="cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a> CMFCWindowsManagerDialog:: CMFCWindowsManagerDialog

Bir [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) nesnesi oluşturur.

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pmdıframe*<br/>
'ndaki Üst veya sahip penceresine yönelik bir işaretçi.

*bHelpButton*<br/>
'ndaki Çerçevenin bir **Yardım** düğmesi görüntüleyip görüntülemediğini belirten bir Boole parametresi.

### <a name="remarks"></a>Açıklamalar

Görsel yöneticiler hakkında daha fazla bilgi için bkz. [görselleştirme Yöneticisi](../../mfc/visualization-manager.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMDIFrameWndEx sınıfı](../../mfc/reference/cmdiframewndex-class.md)
