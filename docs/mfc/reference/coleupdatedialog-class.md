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
ms.openlocfilehash: c0208a24b69c1884d72c0ae525ce95b3d3258271
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079980"
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog sınıfı
Kullanılması gereken OLE bağlantıları Düzenle iletişim kutusu için bir özel durum kullanılan, bağlantılı yalnızca var olan güncelleştirme gerektiğinde veya bir belgede katıştırılmış nesneler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Oluşturan bir `COleUpdateDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|Görüntüler **Bağlantıları Düzenle** iletişim kutusu, bir güncelleştirme modunda.|  
  
## <a name="remarks"></a>Açıklamalar  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
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
 Oluşturan bir `COleUpdateDialog` nesnesi.  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDoc*  
 Güncelleştirilmesi gereken bağlantılar içeren belge noktalarına.  
  
 *bUpdateLinks*  
 Bağlantılı nesneler güncelleştirilmesi olup olmadığını belirleyen bayrak.  
  
 *bUpdateEmbeddings*  
 Katıştırılmış nesneler güncelleştirilmesi olup olmadığını belirleyen bayrak.  
  
 *pParentWnd*  
 İşaret üst veya sahibi pencere nesnesi için (tür `CWnd`) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim kutusunun üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca oluşturan bir `COleUpdateDialog` nesnesi. İletişim kutusunu görüntülemek için arama [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Bu sınıf yerine kullanılmalıdır `COleLinksDialog` yalnızca varolan güncelleştirmek istediğiniz zaman veya bağlı öğeleri katıştırılmış.  
  
##  <a name="domodal"></a>  COleUpdateDialog::DoModal  
 Güncelleştirme modu Bağlantıları Düzenle iletişim kutusu görüntüler.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- **IDOK** iletişim kutusu başarıyla döndürülürse.  
  
- **IDCANCEL** geçerli belgede bağlantılı veya katıştırılmış öğelerin hiçbiri güncelleştirme gerekip gerekmediğini.  
  
- **IDABORT** durumunda bir hata oluştu. Varsa **IDABORT** olan döndürülen arama [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) oluştu hata türü hakkında daha fazla bilgi almak için üye işlevi. Olası hatalar listesi için bkz: [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) Windows SDK'sındaki işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 İptal düğmesi kullanıcının seçtiği sürece tüm bağlantılar ve/veya eklerinin güncelleştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog sınıfı](../../mfc/reference/colelinksdialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog Sınıfı](../../mfc/reference/colelinksdialog-class.md)
