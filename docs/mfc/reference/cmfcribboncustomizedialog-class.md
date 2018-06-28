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
ms.openlocfilehash: 8e693a0e6a2353693f676ed0d63d7087d3e57455
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040905"
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
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|Oluşturan bir `CMFCRibbonCustomizeDialog` nesnesi.|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 MFC bu sınıf AFX_WM_ON_RIBBON_CUSTOMIZE yapılacak işlem yok, ya da ileti işleyicisini 0 döndürürse otomatik olarak başlatır.  
  
 Bu sınıf, Şerit görüntülemek için uygulamanızda kullanmak isteyip istemediğinizi **Özelleştir** iletişim kutusu, yalnızca, örneği ve çağrısı `DoModal` yöntemi.  
  
 Bu sınıfın türetildiği için [CMFCPropertySheet sınıfı](../../mfc/reference/cmfcpropertysheet-class.md), kullanarak özel sayfalar ekleyebilirsiniz `CMFCPropertySheet` API.  
  
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
 Oluşturan bir `CMFCRibbonCustomizeDialog` nesnesi.  
  
```  
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,  
    CMFCRibbonBar* pRibbon);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndParent*  
 Üst pencere (genellikle ana çerçeve) için bir işaretçi.  
  
 [in] *pRibbon*  
 Bir işaretçi `CMFCRibbonBar` özelleştirilmek üzere olmasıdır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCRibbonCustomizeDialog` nesnesi.  
  
 [!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu başlatır bir [CMFCRibbonCustomizePropertyPage sınıfı](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) nesne ve özellik sayfası sayfaları koleksiyonuna ekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıflar](../../mfc/reference/mfc-classes.md)
