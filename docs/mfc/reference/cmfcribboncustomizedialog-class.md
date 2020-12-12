---
description: 'Daha fazla bilgi edinin: CMFCRibbonCustomizeDialog Class'
title: CMFCRibbonCustomizeDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: 9420ebdf32a1c26cba6efee17467fd3dfe202574
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293618"
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog sınıfı

Şerit **Özelleştirme** sayfasını görüntüler.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Bir `CMFCRibbonCustomizeDialog` nesnesi oluşturur.|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|

## <a name="remarks"></a>Açıklamalar

AFX_WM_ON_RIBBON_CUSTOMIZE iletisini işlemeyin veya ileti işleyicisinden 0 döndürmeyin MFC bu sınıfı otomatik olarak başlatır.

Şerit **Özelleştirme** iletişim kutusunu göstermek için uygulamanızda bu sınıfı kullanmak istiyorsanız, yalnızca örneğini oluşturun ve `DoModal` yöntemi çağırın.

Bu sınıf [CMFCPropertySheet sınıfından](../../mfc/reference/cmfcpropertysheet-class.md)türetildiğinden, API 'yi kullanarak özel sayfalar ekleyebilirsiniz `CMFCPropertySheet` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

[CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncustomizedialog. h

## <a name="cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a> CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog

Bir `CMFCRibbonCustomizeDialog` nesnesi oluşturur.

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Ana pencereye (genellikle ana çerçeve) yönelik bir işaretçi.

*pRibbon*<br/>
'ndaki `CMFCRibbonBar` Özelleştirilmek üzere bir işaretçisi.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCRibbonCustomizeDialog` .

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>Açıklamalar

Oluşturucu bir [CMFCRibbonCustomizePropertyPage Class](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) nesnesi oluşturur ve onu Özellik sayfası sayfaları koleksiyonuna ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
