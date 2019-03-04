---
title: CMFCRibbonCustomizeDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: d73fd05a775ac26f5d289a5233341102f40e9af3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260003"
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog sınıfı

Şerit görüntüler **Özelleştir** sayfası.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Oluşturur bir `CMFCRibbonCustomizeDialog` nesne.|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|

## <a name="remarks"></a>Açıklamalar

MFC bu sınıf AFX_WM_ON_RIBBON_CUSTOMIZE iletiyi işlemez veya 0'ı ileti işleyicisi dönerseniz otomatik olarak başlatır.

Bu sınıf, Şerit görüntülemek için uygulamanızda kullanmak istiyorsanız **Özelleştir** iletişim kutusunda, yalnızca bu örneği ve çağırmayı `DoModal` yöntemi.

Bu sınıf türetilir çünkü [CMFCPropertySheet sınıfı](../../mfc/reference/cmfcpropertysheet-class.md), kullanarak özel sayfalar ekleyebilirsiniz `CMFCPropertySheet` API.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

[CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxribboncustomizedialog.h

##  <a name="cmfcribboncustomizedialog"></a>  CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog

Oluşturur bir `CMFCRibbonCustomizeDialog` nesne.

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] (Genellikle ana çerçeve) üst penceresine bir işaretçi.

*pRibbon*<br/>
[in] Bir işaretçi `CMFCRibbonBar` özelleştirilecek olmasıdır.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCRibbonCustomizeDialog` nesne.

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>Açıklamalar

Oluşturucu örnekleyen bir [CMFCRibbonCustomizePropertyPage sınıfı](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) nesne ve özellik sayfası sayfaları koleksiyonuna ekler.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
