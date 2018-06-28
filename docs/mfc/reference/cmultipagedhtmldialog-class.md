---
title: CMultiPageDHtmlDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a1a4ca77e4b7a2cda10d87bd657e73931a50612
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038012"
---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog sınıfı
Birden çok sayfa iletişim her sayfasından olayları işler ve birden çok HTML sayfaları sıralı olarak görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|Birden çok sayfa (Sihirbazı-stil) DHTML iletişim nesnesi oluşturur.|  
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|Birden çok DHTML iletişim nesnesi yok eder.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bunu yapmak için mekanizma bir [DHTML ve URL olay eşlemesi](dhtml-event-maps.md), her bir sayfa için olay eşlemeleri içeren katıştırılmış.  
  
## <a name="example"></a>Örnek  
 Bu birden çok sayfa iletişim basit Sihirbazı benzeri işlevsellik tanımlayan üç HTML kaynakları varsayar. İlk sayfasına sahip bir `Next` düğmesi, ikinci bir **önceki** ve `Next` düğmesi ve üçüncü bir **önceki** düğmesi. Düğmeleri birini basıldığında bir işleyici işlevi çağırır [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) uygun yeni sayfa yüklenemiyor.  
  
 Sınıf bildiriminde (CMyMultiPageDlg.h) ilgili bölümleri:  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 Sınıf uygulamasında (CMyMultipageDlg.cpp) ilgili bölümleri:  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdhtml.h  
  
##  <a name="cmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 Birden çok sayfa (Sihirbazı-stil) DHTML iletişim nesnesi oluşturur.  
  
```  
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID = NULL,  
    CWnd* pParentWnd = NULL);

 
CMultiPageDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd* pParentWnd = NULL);  
  
CMultiPageDHtmlDialog();
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszTemplateName*  
 Bir iletişim kutusu şablon kaynağı adı null ile sonlandırılmış bir dize.  
  
 *szHtmlResID*  
 Bir HTML kaynak adı null ile sonlandırılmış bir dize.  
  
 *pParentWnd*  
 Üst veya sahibi pencere nesnesi için bir işaretçi (tür [CWnd](../../mfc/reference/cwnd-class.md)) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
 *nIDTemplate*  
 Bir iletişim kutusu şablon kaynağı kimliği numarasını içerir.  
  
 *nHtmlResID*  
 Bir HTML kaynak kimliği sayısını içerir.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 Birden çok DHTML iletişim nesnesi yok eder.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDHtmlDialog Sınıfı](../../mfc/reference/cdhtmldialog-class.md)
