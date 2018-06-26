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
ms.openlocfilehash: 576735841748d0b99053d038f8d5f674d5692f00
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930195"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme
Genişletilmiş Birleşik giriş kutusu, denetimi kullanıcıların etkileşimli olarak (`CComboBoxEx`) üst pencereye, bildirim iletileri gönderir genellikle bir görünüm veya iletişim nesnesi. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcının açılan listenin etkinleştirir ya da denetimin düzenleme kutusuna tıklar CBEN_BEGINEDIT bildirim gönderilir.  
  
 Üst sınıf uygulamak isterseniz bu iletiler için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.  
  
 Genişletilmiş Birleşik giriş kutusu denetimi tarafından gönderilen çeşitli bildirimler aşağıdaki listede açıklanmaktadır.  
  
-   Kullanıcı aşağı açılan liste etkinleştirir veya denetimin düzenleme kutusuna tıklattığında CBEN_BEGINEDIT gönderdi.  
  
-   Bir öğe silindiğinde CBEN_DELETEITEM gönderdi.  
  
-   Kullanıcı denetimi Düzenle kısmında görüntülenen öğesini görüntü sürükleme başladığında CBEN_DRAGBEGIN gönderdi.  
  
-   Kullanıcı düzenleme kutusu içinde bir işlem sonuçları veya denetimin aşağı açılan listeden bir öğe seçti CBEN_ENDEDIT gönderilir.  
  
-   Bir geri çağırma öğesinin görüntü bilgilerini almak için gönderilen CBEN_GETDISPINFO.  
  
-   CBEN_INSERTITEM denetiminde yeni bir öğe eklendiğinde gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComboBoxEx kullanma](../mfc/using-ccomboboxex.md)   
 [Denetimler](../mfc/controls-mfc.md)

