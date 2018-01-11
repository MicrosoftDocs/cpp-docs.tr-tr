---
title: "COleBusyDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
dev_langs: C++
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e57881dad305a5a0d5cec25ddcc93f82eca5f26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="colebusydialog-class"></a>COleBusyDialog sınıfı
OLE sunucu yanıt vermiyor veya sunucu meşgul iletişim kutuları için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|Oluşturan bir `COleBusyDialog` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|OLE sunucu meşgul iletişim kutusunu görüntüler.|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|İletişim kutusunda yaptığınız seçim şunu belirler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|Türü yapısını **OLEUIBUSY** iletişim kutusu davranışını denetler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi oluşturma `COleBusyDialog` bu iletişim kutularından çağırmak istediğinizde. Sonra bir `COleBusyDialog` nesne oluşturulan, kullanabileceğiniz [m_bz](#m_bz) yapısı değerleri veya iletişim kutusu denetimleri durumlarını başlatılamadı. `m_bz` Yapısıdır türü **OLEUIBUSY**. Bu iletişim kutusu sınıfı kullanma hakkında daha fazla bilgi için bkz: [DoModal](#domodal) üye işlevi.  
  
> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan kapsayıcı kodu bu sınıfı kullanır.  
  
 Daha fazla bilgi için bkz: [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK'sındaki yapısı.  
  
 OLE özel iletişim kutuları hakkında daha fazla bilgi için bkz: [ole'deki iletişim kutuları](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxodlgs.h  
  
##  <a name="colebusydialog"></a>COleBusyDialog::COleBusyDialog  
 Bu işlev yalnızca oluşturan bir `COleBusyDialog` nesnesi.  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *htaskBusy*  
 Meşgul sunucu görev işleyin.  
  
 *bNotResponding*  
 Varsa **doğru**, yanıt iletişim kutusu yerine sunucu meşgul iletişim kutusu çağırın. Yanıt iletişim kutusunda ifade biraz sunucu meşgul iletişim kutusunda ifade farklıdır ve iptal düğmesi devre dışıdır.  
  
 `dwFlags`  
 Oluşturma bayrağı. Sıfır veya daha fazla bit düzeyinde OR işleci ile birlikte aşağıdaki değerleri içerebilir:  
  
- **BZ_DISABLECANCELBUTTON** iletişim kutusu çağrılırken iptal düğmesi devre dışı bırakın.  
  
- **BZ_DISABLESWITCHTOBUTTON** iletişim kutusu çağrılırken Geçiş Yap düğmesini devre dışı bırakın.  
  
- **BZ_DISABLERETRYBUTTON** iletişim kutusu çağrılırken yeniden dene düğmesi devre dışı bırakın.  
  
 `pParentWnd`  
 İşaret üst veya sahibi pencere nesnesi için (tür `CWnd`) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusunu görüntülemek için arama [DoModal](#domodal).  
  
 Daha fazla bilgi için bkz: [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK'sındaki yapısı.  
  
##  <a name="domodal"></a>COleBusyDialog::DoModal  
 OLE sunucu meşgul veya sunucu yanıt iletişim kutusunu görüntülemek için bu işlevini çağırın.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tamamlanma durumu iletişim kutusu için. Aşağıdaki değerlerden biri:  
  
- **IDOK** iletişim kutusu başarıyla görüntüleniyorsa.  
  
- **IDCANCEL** kullanıcı iletişim kutusunu iptal ederseniz.  
  
- **IDABORT** durumunda bir hata oluştu. Varsa **IDABORT** olan döndürülen arama `COleDialog::GetLastError` oluştu hata türü hakkında daha fazla bilgi almak için üye işlevi. Olası hatalar listesi için bkz: [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) Windows SDK'sındaki işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üyeleri ayarlayarak çeşitli iletişim kutusu denetimleri başlatmak istiyorsanız [m_bz](#m_bz) yapısı, bu çağırmadan önce yapmanız gerektiğini `DoModal`, ancak iletişim nesnesi oluşturulur.  
  
 Varsa `DoModal` döndürür **IDOK**, diğer üye ayarları veya kullanıcı tarafından iletişim kutusuna giriş bilgileri almak için işlevleri çağırabilir.  
  
##  <a name="getselectiontype"></a>COleBusyDialog::GetSelectionType  
 Sunucu meşgul iletişim kutusunda kullanıcı tarafından seçilen seçim türünü almak için bu işlevini çağırın.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yapılan seçim türü.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından belirtilen dönüş türü değerleri **seçimi** numaralandırma türü içinde bildirilen `COleBusyDialog` sınıfı.  
  
```  
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```  
  
 Bu değerlerin kısa açıklamaları izleyin:  
  
- **COleBusyDialog::switchTo** geçiş yap düğmesine basıldığında.  
  
- **COleBusyDialog::retry** yeniden deneme düğmesine basıldığında.  
  
- **COleBusyDialog::callUnblocked** Sunucusu'nu etkinleştirmek için çağrıdır şimdi engellenmemiş.  
  
##  <a name="m_bz"></a>COleBusyDialog::m_bz  
 Türü yapısını **OLEUIBUSY** sunucu meşgul iletişim kutusunun davranışını denetlemek için kullanılır.  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yapı üyeleri, doğrudan veya üye işlevleri aracılığıyla değiştirilebilir.  
  
 Daha fazla bilgi için bkz: [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK'sındaki yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleDialog sınıfı](../../mfc/reference/coledialog-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDialog Sınıfı](../../mfc/reference/coledialog-class.md)
