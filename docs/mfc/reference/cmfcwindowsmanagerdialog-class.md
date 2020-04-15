---
title: CMFCWindowsManagerDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: e3928c0d3ae4f607dceb99c0762277e8ea9ddbde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319834"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog Sınıfı

Nesne, `CMFCWindowsManagerDialog` bir MDI uygulamasında bir kullanıcının MDI alt pencerelerini yönetmesini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Bir `CMFCWindowsManagerDialog` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Uygulamada `CMFCWindowsManagerDialog` şu anda açık olan MDI alt pencerelerinin listesini içerir. Kullanıcı, bu iletişim kutusunu kullanarak MDI alt pencerelerinin durumunu el ile denetleyebilir.

`CMFCWindowsManagerDialog`[CMDIFrameWndEx Sınıfı'nın](../../mfc/reference/cmdiframewndex-class.md)içine gömülüdür. El `CMFCWindowsManagerDialog` ile oluşturmanız gereken bir sınıf değildir. Bunun yerine, [CMDIFrameWndEx işlevini arayın::ShowWindowsDialog,](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)ve `CMFCWindowsManagerDialog` bir nesne oluşturup görüntüleyecek.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCWindowsManagerDialog` nesneyi arayarak `CMDIFrameWndEx::ShowWindowsDialog`nasıl oluşturulabildiğini gösterir. Bu kod snippet [Visual Studio Demo örnek](../../overview/visual-cpp-samples.md)parçasıdır.

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cdialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxWindowsManagerDialog.h

## <a name="cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a>CMFCWindowsManagerDialog::CMFCWindowsManagerDialog

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) nesnesi oluşturuyor.

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>Parametreler

*pMDIFrame*<br/>
[içinde] Üst veya sahip penceresi için bir işaretçi.

*bHelpButton*<br/>
[içinde] Çerçevenin **Yardım** düğmesi gösterip görüntülemediğini belirten bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

Görsel yöneticiler hakkında daha fazla bilgi için [Visualization Manager'a](../../mfc/visualization-manager.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMDIFrameWndEx Sınıfı](../../mfc/reference/cmdiframewndex-class.md)
