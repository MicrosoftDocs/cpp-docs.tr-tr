---
title: "Bildirim iletilerini işleme tarih ve Saat Seçici denetimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
dev_langs: C++
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5057f29192661b858a0a54eccd3189c6147777d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Tarih ve Saat Seçici Denetimlerinde Bildirim İletilerini İşleme
Kullanıcıların etkileşimli olarak tarih ve saat seçici denetimi, denetim (`CDateTimeCtrl`) üst pencereye, bildirim iletileri gönderir genellikle bir görünüm veya iletişim nesnesi. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı açtığında katıştırılmış aylık takvim denetiminin görüntülemek için tarih ve Saat Seçici **DTN_DROPDOWN** bildirim gönderilir.  
  
 Üst sınıf uygulamak isterseniz bu iletiler için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.  
  
 Aşağıdaki liste tarih ve Saat Seçici denetiminde gönderilen çeşitli bildirimler açıklar.  
  
-   **DTN_DROPDOWN** katıştırılmış aylık takvim denetimi hakkında görüntülenecek olan üst bildirir. Bu bildirim yalnızca zaman gönderilir **DTS_UPDOWN** stili ayarlanmamış. Bu bildirim hakkında daha fazla bilgi için bkz: [katıştırılmış aylık takvim denetiminin erişme](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   **DTN_CLOSEUP** üst Kapatılmak üzere katıştırılmış aylık takvim denetiminin olan bildirir. Bu bildirim yalnızca zaman gönderilir **DTS_UPDOWN** stili ayarlanmamış.  
  
-   **Dtn_datetımechange** denetiminde gerçekleşen bir değişikliği üst bildirir.  
  
-   **DTN_FORMAT** üst metin bir geri çağırma alanında görüntülenecek gerektiğini bildirir. Bu bildirim ve geri arama alanları hakkında daha fazla bilgi için bkz: [kullanarak geri arama alanları bir tarih ve Saat Seçici denetimini](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN_FORMATQUERY** bir geri çağırma alanında görüntülenen dizesi izin verilen en büyük boyutunu sağlamak için üst ister. Bu bildirim işleme her zaman, denetimin görüntüleme içinde titreşimi azaltma düzgün görüntü çıkış denetimi sağlar. Bu bildirim hakkında daha fazla bilgi için bkz: [kullanarak geri arama alanları bir tarih ve Saat Seçici denetimini](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   **DTN_USERSTRING** üst kullanıcı tarih ve Saat Seçici denetimini içeriğini düzenleme tamamlandığını bildirir. Bu bildirim yalnızca zaman gönderilir **DTS_APPCANPARSE** stili ayarlayın.  
  
-   **DTN_WMKEYDOWN** kullanıcı, bir geri çağırma alana yazdığında üst bildirir. Desteklenen bir tarih ve Saat Seçici denetiminde geri çağırma olmayan alanlar için aynı klavye yanıt benzetmek için bu bildirimi işleyin. Bu bildirim hakkında daha fazla bilgi için bkz: [DTP denetiminde geri çağrı alanlarını destekleyen](http://msdn.microsoft.com/library/windows/desktop/bb761726) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDateTimeCtrl kullanma](../mfc/using-cdatetimectrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

