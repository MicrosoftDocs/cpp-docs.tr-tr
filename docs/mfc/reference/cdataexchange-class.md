---
title: CDataExchange sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
dev_langs:
- C++
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed2f918a51c1dca1aa7e1713ac919102a599e38
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953353"
---
# <a name="cdataexchange-class"></a>CDataExchange sınıfı
İletişim kutusu veri değişimi (DDX) ve Microsoft Foundation sınıfları tarafından kullanılan iletişim kutusu veri doğrulama (DDV) yordamları destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDataExchange  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDataExchange::CDataExchange](#cdataexchange)|Oluşturan bir `CDataExchange` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDataExchange::Fail](#fail)|Doğrulama başarısız olduğunda çağrılır. Önceki denetim odağı sıfırlar ve bir özel durum oluşturur.|  
|[CDataExchange::PrepareCtrl](#preparectrl)|Belirtilen denetim veri değişimi veya doğrulama için hazırlar. Nonedit denetimleri için kullanın.|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|Belirtilen düzenleme denetimi, veri değişimi veya doğrulama için hazırlar.|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|Belirtilen OLE denetimi, veri değişimi veya doğrulama için hazırlar. Nonedit denetimleri için kullanın.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|DDX ve DDV yönünü için bayrak.|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|Burada veri değişimi penceresi ya da iletişim kutusunda gerçekleşir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDataExchange` bir taban sınıfı yok.  
  
 Özel veri türleri veya denetimleri için veri değişimi rutinleri yazıyorsanız, bu sınıfı kullanın veya kendi veri doğrulama yordamları yazıyorsanız. Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutuları](../../mfc/dialog-boxes.md).  
  
 A `CDataExchange` nesnesi DDX ve DDV yapılacak yerleştirmek için gereken bağlam bilgilerini sağlar. Bayrak *m_bSaveAndValidate* olan **FALSE** zaman DDX iletişim kutusu denetimleri veri üyelerinden ilk değerleri doldurmak için kullanılır. Bayrak *m_bSaveAndValidate* olan **TRUE** zaman DDX veri üyeleri ve DDV veri değerlerini doğrulamak için kullanıldığında iletişim kutusu denetimleri geçerli değerlerini ayarlamak için kullanılır. DDV doğrulama başarısız olursa, DDV yordam giriş hatası açıklayan bir ileti kutusu görüntüler. DDV yordam sonra çağıracak `Fail` sorunlu denetim odağı sıfırlama ve doğrulama işlemi durdurmak için bir özel durum.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CDataExchange`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cdataexchange"></a>  CDataExchange::CDataExchange  
 Oluşturmak için bu üye işlevini çağırın bir `CDataExchange` nesnesi.  
  
```  
CDataExchange(
    CWnd* pDlgWnd,  
    BOOL bSaveAndValidate);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDlgWnd*  
 Denetimi içeren üst pencere için bir işaretçi. Genellikle bu olan bir [CDialog](../../mfc/reference/cdialog-class.md)-türetilmiş bir nesne içermelidir.  
  
 *bSaveAndValidate*  
 Varsa **doğru**, bu nesne verileri doğrular ve ardından verileri denetimlerden üyelerine yazar. Varsa **yanlış**, bu nesnenin veri denetimlere üyeleri taşınır.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CDataExchange` nesne kendiniz, pencerenin geçirmek için veri exchange nesnesindeki ek bilgileri depolamak için [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>  CDataExchange::Fail  
 Bir iletişim kutusu veri doğrulama (DDV) işlemi başarısız olduğunda framework bu üye işlevi çağırır.  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `Fail` odak ve seçim (geri yüklemek için bir denetim varsa), doğrulama başarısız oldu denetim geri yükler. `Fail` türünde bir özel durum atar [CUserException](../../mfc/reference/cuserexception-class.md) doğrulama işlemi durdurmak için. Özel durum görüntülenecek hatayı açıklayan bir ileti kutusu neden olur. DDV doğrulama başarısız olduktan sonra kullanıcı verileri sorunlu denetiminde yeniden girebilirsiniz.  
  
 Özel DDV rutinleri implementors çağırabilir `Fail` bir doğrulama başarısız olduğunda kendi yordamları gelen.  
  
 Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusunu konularına](../../mfc/dialog-boxes.md).  
  
##  <a name="m_bsaveandvalidate"></a>  CDataExchange::m_bSaveAndValidate  
 Bu bayrak bir iletişim kutusu veri değişimi (DDX) işlemi yönünü belirtir.  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bayrak sıfır olmayan varsa `CDataExchange` nesnesi, kullanıcı denetimleri düzenledikten sonra veri iletişim kutusu sınıfı veri üyelerine iletişim denetimlerden taşımak için kullanılıyor. Nesne iletişim kutusu denetimleri iletişim kutusu sınıfı veri üyelerinden başlatmak için kullanılıp kullanılmadığını bayrağı sıfır olur.  
  
 Bayrağı de iletişim verisi doğrulama (DDV) sırasında sıfır olur.  
  
 Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusunu konularına](../../mfc/dialog-boxes.md).  
  
##  <a name="m_pdlgwnd"></a>  CDataExchange::m_pDlgWnd  
 Bir işaretçi içeriyor [CWnd](../../mfc/reference/cwnd-class.md) nesne için hangi iletişim kutusu veri değişimi (DDX) veya doğrulama (DDV) sürüyor yerleştir.  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu nesnesidir genellikle bir [CDialog](../../mfc/reference/cdialog-class.md) nesnesi. Özel DDX veya DDV rutinleri implementors this işaretçisi üzerinde işletim denetimleri içeren iletişim kutusu penceresinin erişim sağlamak için kullanabilirsiniz.  
  
 Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusunu konularına](../../mfc/dialog-boxes.md).  
  
##  <a name="preparectrl"></a>  CDataExchange::PrepareCtrl  
 Framework'te iletişim kutusu veri değişimi (DDX) ve doğrulama (DDV) için belirtilen denetim hazırlamak için bu üye işlevi çağırır.  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDC*  
 DDX veya DDV için hazırlıklı olmak için denetim kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `HWND` DDX veya DDV için hazırlanan denetimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanmak [PrepareEditCtrl](#prepareeditctrl) düzenleme denetimlerinde; diğer denetimler için bu üye işlevini kullanın.  
  
 Hazırlık oluşur denetimin depolayabilen `HWND` içinde `CDataExchange` sınıfı. Çerçeve bu tanıtıcıyı odağı DDX veya DDV hatası durumunda önceden odaklı denetimin geri yüklemek için kullanır.  
  
 Özel DDX veya DDV rutinleri implementors çağrısı `PrepareCtrl` , bunlar DDX aracılığıyla veri değişimi veya verileri DDV aracılığıyla doğrulama tüm düzen olmayan denetimler için.  
  
 Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusunu konularına](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareeditctrl"></a>  CDataExchange::PrepareEditCtrl  
 Framework'te iletişim kutusu veri değişimi (DDX) ve doğrulama (DDV) için belirtilen düzenleme denetimi hazırlamak için bu üye işlevi çağırır.  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDC*  
 DDX veya DDV için hazırlıklı olmak için düzenleme denetimi kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `HWND` DDX veya DDV için hazırlanan düzenleme denetimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [PrepareCtrl](#preparectrl) bunun yerine tüm düzen olmayan denetimler için.  
  
 Hazırlık ikisinden oluşur. İlk olarak, `PrepareEditCtrl` denetimin depolar `HWND` içinde `CDataExchange` sınıfı. Çerçeve bu tanıtıcıyı odağı DDX veya DDV hatası durumunda önceden odaklı denetimin geri yüklemek için kullanır. İkinci, `PrepareEditCtrl` bir bayrak ayarlar `CDataExchange` sınıfı belirtmek için veriler değiştirilen veya doğrulanmış bir düzenleme denetimi denetim.  
  
 Özel DDX veya DDV rutinleri implementors çağrısı `PrepareEditCtrl` tüm, bunlar DDX aracılığıyla veri değişimi veya verileri DDV aracılığıyla doğrulama denetimleri düzenlemek için.  
  
 Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusunu konularına](../../mfc/dialog-boxes.md).  
  
##  <a name="prepareolectrl"></a>  CDataExchange::PrepareOleCtrl  
 Framework'te iletişim kutusu veri değişimi (DDX) ve doğrulama (DDV) için belirtilen OLE denetim hazırlamak için bu üye işlevi çağırır.  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDC*  
 DDX veya DDV için hazırlıklı olmak için OLE denetimi kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 OLE denetim site için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [PrepareEditCtrl](#prepareeditctrl) yerine düzenleme denetimlerinde veya [PrepareCtrl](#preparectrl) diğer tüm OLE dışı denetimler için.  
  
 Özel DDX veya DDV rutinleri implementors çağrısı `PrepareOleCtrl` , bunlar DDX aracılığıyla veri değişimi veya verileri DDV aracılığıyla doğrulama tüm OLE denetimleri için.  
  
 Kendi DDX ve DDV rutinleri yazma ile ilgili daha fazla bilgi için bkz: [Teknik Not 26](../../mfc/tn026-ddx-and-ddv-routines.md). DDX ve DDV genel bakış için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md) ve [iletişim kutusunu konularına](../../mfc/dialog-boxes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek VIEWEX](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)

