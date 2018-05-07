---
title: Genişletilmiş Birleşik giriş kutusu denetimlerinde bildirim iletilerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1e71502f818321dc8893f89f21993c25b032602
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme
Genişletilmiş Birleşik giriş kutusu, denetimi kullanıcıların etkileşimli olarak (`CComboBoxEx`) üst pencereye, bildirim iletileri gönderir genellikle bir görünüm veya iletişim nesnesi. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, ne zaman kullanıcı aşağı açılan liste etkinleştirir veya denetimin tıklama düzenleme kutusuna, **CBEN_BEGINEDIT** bildirim gönderilir.  
  
 Üst sınıf uygulamak isterseniz bu iletiler için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.  
  
 Genişletilmiş Birleşik giriş kutusu denetimi tarafından gönderilen çeşitli bildirimler aşağıdaki listede açıklanmaktadır.  
  
-   **CBEN_BEGINEDIT** kullanıcı aşağı açılan liste etkinleştirir veya denetimin tıklama düzenleme kutusuna gönderilir.  
  
-   **CBEN_DELETEITEM** bir öğe silindiğinde gönderilir.  
  
-   **CBEN_DRAGBEGIN** kullanıcı denetimi Düzenle kısmında görüntülenen öğesini görüntü sürükleme başladığında gönderilir.  
  
-   **CBEN_ENDEDIT** kullanıcı düzenleme kutusu içinde bir işlemi tamamlanmış ya da denetimin aşağı açılan listeden bir öğe seçti gönderilir.  
  
-   **CBEN_GETDISPINFO** bir geri çağırma öğesinin görüntü bilgilerini almak için gönderilir.  
  
-   **CBEN_INSERTITEM** denetiminde yeni bir öğe eklendiğinde gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComboBoxEx kullanma](../mfc/using-ccomboboxex.md)   
 [Denetimler](../mfc/controls-mfc.md)

