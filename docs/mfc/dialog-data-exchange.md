---
title: "İletişim kutusu veri değişimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing dialog boxes
- canceling data exchange
- dialog box data, retrieving
- DDX (dialog data exchange), data exchange mechanism
- dialog boxes [MFC], initializing
- dialog boxes [MFC], retrieving user input using DDX
- dialog box data
- dialog boxes [MFC], data exchange
- CDataExchange class [MFC], using DDX
- DoDataExchange method [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- transferring dialog box data
- DDX (dialog data exchange), canceling
- UpdateData method [MFC]
- retrieving dialog box data [MFC]
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 35f280228d523c7401e2a90ca395a79a9c87cd51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-data-exchange"></a>İletişim Kutusu Veri Değişimi
DDX mekanizması kullanırsanız, iletişim kutusunun Başlangıç değerlerini nesnenin üye değişkenleri, genellikle ayarlamak, `OnInitDialog` işleyicisi veya iletişim Oluşturucusu. İletişim kutusu görüntülenmeden önce framework'ün DDX mekanizması nerede göründüklerinden iletişim kutusu denetimleri için üye değişkenlerin değerleri aktarır hemen iletişim kutusu görüntülendiğinde yanıt olarak `DoModal` veya **oluştur** . Varsayılan uygulaması `OnInitDialog` içinde `CDialog` çağrıları `UpdateData` sınıfının üye işlevini `CWnd` iletişim kutusu denetimleri başlatılamadı.  
  
 Kullanıcı Tamam düğmesine tıkladığında aynı mekanizmayı değerleri denetimleri için üye değişkenleri aktarır (veya çağırmanız her `UpdateData` üye işlevi bağımsız değişkeniyle **TRUE**). İletişim kutusu veri doğrulama mekanizmasını doğrulama kuralları belirtilen tüm veri öğelerinin doğrular.  
  
 Aşağıdaki şekilde iletişim kutusu veri değişimi gösterilmektedir.  
  
 ![İletişim kutusu veri değişimi](../mfc/media/vc379d1.gif "vc379d1")  
İletişim Kutusu Veri Değişimi  
  
 `UpdateData`Her iki yönde belirtildiği gibi çalışır **BOOL** kendisine geçirilen parametre. Exchange taşımak için `UpdateData` ayarlayan bir `CDataExchange` nesne ve çağrıları iletişim sınıfınızın geçersiz kılmak `CDialog`'s `DoDataExchange` üye işlevi. `DoDataExchange`bir bağımsız değişken türü `CDataExchange`. `CDataExchange` Nesne geçirilen `UpdateData` gibi bilgileri exchange yönünü tanımlama exchange bağlamını temsil eder.  
  
 Ne zaman sizin (veya bir kod sihirbaz) geçersiz kılma `DoDataExchange`, veri üyesi (Denetim) başına bir DDX işlevi çağrısı belirtin. Her DDX işlevi tarafından sağlanan bağlam göre her iki yönde veri değişimi bildiği `CDataExchange` geçirilen bağımsız değişken, `DoDataExchange` tarafından `UpdateData`.  
  
 MFC exchange farklı türde pek çok DDX işlevleri sağlar. Aşağıdaki örnekte gösterildiği bir `DoDataExchange` geçersiz kılma hangi iki DDX işlevleri ve bir DDV işlevi çağrılır:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]  
  
 `DDX_` Ve `DDV_` satırlar mevcut bir veri eşleme. Gösterilen örnek DDX ve DDV bir onay kutusu ve bir düzenleme kutusu denetimi için sırasıyla işlevlerdir.  
  
 Kalıcı iletişim kutusu, kullanıcı iptal ederse `OnCancel` üye işlevi iletişim kutusunu sonlandırır ve `DoModal` değeri döndürür **IDCANCEL**. Bu durumda, veri iletişim kutusu ile iletişim nesnesi arasında değiştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)   
 [İletişim Verisi Doğrulama](../mfc/dialog-data-validation.md)

