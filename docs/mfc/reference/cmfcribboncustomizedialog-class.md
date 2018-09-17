---
title: CMFCRibbonCustomizeDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d342ec75fd45224dcd36ba3fc17aa1a6f8c12e33
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720661"
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
