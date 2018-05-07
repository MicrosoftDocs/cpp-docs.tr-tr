---
title: CMFCWindowsManagerDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6900164b3ce89031d0db7630c026a302616511c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog sınıfı
`CMFCWindowsManagerDialog` MDI alt pencereleri MDI uygulamasında yönetmek bir kullanıcı nesnesi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Oluşturan bir `CMFCWindowsManagerDialog` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCWindowsManagerDialog` Uygulamada açık olan MDI alt pencereleri listesini içerir. Kullanıcı, bu iletişim kutusunu kullanarak MDI alt pencereleri durumunu el ile denetleyebilirsiniz.  
  
 `CMFCWindowsManagerDialog` içinde katıştırılmış [CMDIFrameWndEx sınıfı](../../mfc/reference/cmdiframewndex-class.md). `CMFCWindowsManagerDialog` El ile oluşturmanız gerekir bir sınıf değil. Bunun yerine, bir işlevi çağırmak [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), görüntüler oluşturmak ve ve bir `CMFCWindowsManagerDialog` nesnesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCWindowsManagerDialog` çağırarak nesne `CMDIFrameWndEx::ShowWindowsDialog`. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
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
 Oluşturan bir [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) nesnesi.  
  
```  
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,  
    BOOL bHelpButton = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pMDIFrame`  
 Üst veya sahibi penceresi için bir işaretçi.  
  
 [in] `bHelpButton`  
 Framework mı gösterileceğini belirten bir Boolean parametresiyle bir **yardımcı** düğmesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Görsel yöneticileri hakkında daha fazla bilgi için bkz: [seri hale getirme Yöneticisi](../../mfc/visualization-manager.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx Sınıfı](../../mfc/reference/cmdiframewndex-class.md)
