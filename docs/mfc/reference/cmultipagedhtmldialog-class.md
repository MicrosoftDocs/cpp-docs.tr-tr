---
title: "CMultiPageDHtmlDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs: C++
helpviewer_keywords: CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4b34d488269b47d432ffc35369725e7ca9fb7e5e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
##  <a name="cmultipagedhtmldialog"></a>CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
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
 `lpszTemplateName`  
 Bir iletişim kutusu şablon kaynağı adı null ile sonlandırılmış bir dize.  
  
 `szHtmlResID`  
 Bir HTML kaynak adı null ile sonlandırılmış bir dize.  
  
 `pParentWnd`  
 Üst veya sahibi pencere nesnesi için bir işaretçi (tür [CWnd](../../mfc/reference/cwnd-class.md)) iletişim nesnesi ait olduğu. Eğer öyleyse **NULL**, iletişim nesnenin üst pencere ana uygulama penceresine ayarlanır.  
  
 `nIDTemplate`  
 Bir iletişim kutusu şablon kaynağı kimliği numarasını içerir.  
  
 `nHtmlResID`  
 Bir HTML kaynak kimliği sayısını içerir.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 Birden çok DHTML iletişim nesnesi yok eder.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDHtmlDialog sınıfı](../../mfc/reference/cdhtmldialog-class.md)
