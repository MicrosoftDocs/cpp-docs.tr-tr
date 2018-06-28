---
title: COleLinksDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs:
- C++
helpviewer_keywords:
- COleLinksDialog [MFC], COleLinksDialog
- COleLinksDialog [MFC], DoModal
- COleLinksDialog [MFC], m_el
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb24b73ba23b430e29ed9144e51372eefdb673a3
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042540"
---
# <a name="colelinksdialog-class"></a>COleLinksDialog sınıfı
OLE bağlantıları Düzenle iletişim kutusu için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Oluşturan bir `COleLinksDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|OLE bağlantıları Düzenle iletişim kutusu görüntüler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|Türü yapısını **OLEUIEDITLINKS** iletişim kutusu davranışını denetler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi oluşturma `COleLinksDialog` bu iletişim kutusunu çağırmak istediğinizde. Sonra bir `COleLinksDialog` nesne oluşturulan, kullanabileceğiniz [m_el](#m_el) yapısı değerleri veya iletişim kutusu denetimleri durumlarını başlatılamadı. `m_el` Yapısıdır türü **OLEUIEDITLINKS**. Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz: [DoModal](#domodal) üye işlevi.  
  
> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.  
  
 Daha fazla bilgi için bkz: [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) Windows SDK'sındaki yapısı.  
  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="domodal"></a>  COleLinksDialog::DoModal  
 OLE bağlantıları Düzenle iletişim kutusu görüntüler.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- **IDOK** iletişim kutusu başarıyla görüntüleniyorsa.  
  
- **IDCANCEL** kullanıcı iletişim kutusunu iptal ederseniz.  
  
- **IDABORT** durumunda bir hata oluştu. Varsa **IDABORT** olan döndürülen arama `COleDialog::GetLastError` oluştu hata türü hakkında daha fazla bilgi almak için üye işlevi. Olası hatalar listesi için bkz: [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) Windows SDK'sındaki işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli iletişim kutusu denetimleri başlatmak istiyorsanız [m_el](#m_el) yapısı, size bunu çağırmadan önce `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
##  <a name="colelinksdialog"></a>  COleLinksDialog::COleLinksDialog  
 Oluşturan bir `COleLinksDialog` nesnesi.  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDoc*  
 Düzenlenecek bağlantıları içeren OLE belge noktalarına.  
  
 *pView*  
 Geçerli Görünüm işaret *pDoc*.  
  
 *dwFlags*  
 Ya da 0 içeren oluşturma bayrağı veya **ELF_SHOWHELP** iletişim kutusu görüntülendiğinde Yardım düğmesini görüntülenip görüntülenmeyeceğini belirtmek için.  
  
 *pParentWnd*  
 İşaret üst veya sahibi pencere nesnesi için (tür `CWnd`) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim kutusunun üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca oluşturan bir `COleLinksDialog` nesnesi. İletişim kutusunu görüntülemek için arama [DoModal](#domodal) işlevi.  
  
##  <a name="m_el"></a>  COleLinksDialog::m_el  
 Türü yapısını **OLEUIEDITLINKS** Bağlantıları Düzenle iletişim kutusu davranışını denetlemek için kullanılır.  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı üyeleri, doğrudan ya da üye işlevleri üzerinden değiştirilebilir.  
  
 Daha fazla bilgi için bkz: [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) Windows SDK'sındaki yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
