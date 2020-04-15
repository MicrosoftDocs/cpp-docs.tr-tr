---
title: CMFCRibbonCustomizeDialog Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: a66c0a19c04e0a900b91c0c28c45bb9c766d25c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375200"
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog Sınıfı

Şeridi **Özelleştir** sayfasını görüntüler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Bir `CMFCRibbonCustomizeDialog` nesne inşa eder.|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|

## <a name="remarks"></a>Açıklamalar

MFC, AFX_WM_ON_RIBBON_CUSTOMIZE iletiyi işlemezseniz veya ileti işleyicisinden 0 döndürerseniz bu sınıfı otomatik olarak anında alar.

Şeridi **özelleştir** iletişim kutusunu görüntülemek için uygulamanızda bu sınıfı kullanmak istiyorsanız, hemen anlık `DoModal` olarak yapın ve yöntemi arayın.

Bu sınıf [CMFCPropertySheet Class'tan](../../mfc/reference/cmfcpropertysheet-class.md)türetildiği için, `CMFCPropertySheet` API'yi kullanarak özel sayfalar ekleyebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cpropertysheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCÖzellik Sayfası](../../mfc/reference/cmfcpropertysheet-class.md)

[CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncustomizedialog.h

## <a name="cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a>CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog

Bir `CMFCRibbonCustomizeDialog` nesne inşa eder.

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Üst pencereye (genellikle ana çerçeve) işaretçi.

*pRibbon*<br/>
[içinde] Bunun için `CMFCRibbonBar` bir işaretçi özelleştirilmiş olmasıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCRibbonCustomizeDialog` nesnenin nasıl inşa edilebildiğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>Açıklamalar

Oluşturucu bir [CMFCRibbonCustomizePropertyPage Class](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) nesnesini anında alır ve özellik sayfası sayfalarının koleksiyonuna ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
