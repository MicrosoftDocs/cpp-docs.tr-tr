---
title: COleUpdateDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f522635c170af784b5bd9f2bb7011fd51e345b3
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211614"
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog sınıfı
Kullanılması gereken OLE Edit Links iletişim kutusu için bir özel durum kullanılan yalnızca mevcut güncelleştirme gerektiğinde, bağlantılı veya katıştırılmış bir belgede nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Oluşturur bir `COleUpdateDialog` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|Görüntüler **Edit Links** güncelleştirme modunda iletişim kutusu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Özel OLE iletişim kutuları hakkında daha fazla bilgi için bkz [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="coleupdatedialog"></a>  COleUpdateDialog::COleUpdateDialog  
 Oluşturur bir `COleUpdateDialog` nesne.  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDoc*  
 Güncelleştirilmesi gereken bağlantıları içeren belge işaret eder.  
  
 *bUpdateLinks*  
 Bağlantılı nesneleri güncelleştirilecek olup olmadığını belirleyen bayrak.  
  
 *bUpdateEmbeddings*  
 Katıştırılmış nesneler güncelleştirilecek olup olmadığını belirleyen bayrak.  
  
 *pParentWnd*  
 Üst veya sahibi pencere nesnesi için işaret (tür `CWnd`) ait olduğu iletişim nesnesi. NULL ise, ana uygulama penceresini iletişim kutusunun üst pencere ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca oluşturan bir `COleUpdateDialog` nesne. İletişim kutusunu görüntülemek için çağrı [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Bu sınıf yerine kullanılması gereken `COleLinksDialog` yalnızca mevcut güncelleştirmek istediğiniz zaman bağlantılı veya katıştırılmış öğeler.  
  
##  <a name="domodal"></a>  COleUpdateDialog::DoModal  
 Güncelleştirme modu Edit Links iletişim kutusu görüntüler.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- İletişim kutusu başarıyla döndürdüyse IDOK.  
  
- Geçerli belgedeki bağlantılı veya katıştırılmış öğeler hiçbiri IDCANCEL güncelleştirilmesi gerekir.  
  
- Bir hata oluşursa IDABORT. IDABORT döndürülürse, çağrı [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) konusu hatanın türü hakkında daha fazla bilgi almak için üye işlevi. Olası hataları bir listesi için bkz. [OleUIEditLinks](/windows/desktop/api/oledlg/nf-oledlg-oleuieditlinksa) Windows SDK'sında işlev.  
  
### <a name="remarks"></a>Açıklamalar  
 İptal düğmesi kullanıcının seçtiği sürece tüm bağlantılar ve/veya Gömmeleri güncelleştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog sınıfı](../../mfc/reference/colelinksdialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog Sınıfı](../../mfc/reference/colelinksdialog-class.md)
