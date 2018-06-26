---
title: Bildirim iletilerini işleme tarih ve Saat Seçici denetimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
dev_langs:
- C++
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 630792eb4bdd89cbe8081894c4ee026437568f3b
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930770"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Tarih ve Saat Seçici Denetimlerinde Bildirim İletilerini İşleme
Kullanıcıların etkileşimli olarak tarih ve saat seçici denetimi, denetim (`CDateTimeCtrl`) üst pencereye, bildirim iletileri gönderir genellikle bir görünüm veya iletişim nesnesi. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, katıştırılmış aylık takvim denetiminin görüntülemek için tarih ve Saat Seçici kullanıcı oturum açtığında, DTN_DROPDOWN bildirimi gönderilir.  
  
 Üst sınıf uygulamak isterseniz bu iletiler için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.  
  
 Aşağıdaki liste tarih ve Saat Seçici denetiminde gönderilen çeşitli bildirimler açıklar.  
  
-   Katıştırılmış aylık takvim denetimi üst hakkında görüntülenecek olan DTN_DROPDOWN bildirir. Bu bildirim yalnızca DTS_UPDOWN stili ayarlanmamış gönderilir. Bu bildirim hakkında daha fazla bilgi için bkz: [katıştırılmış aylık takvim denetiminin erişme](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   DTN_CLOSEUP katıştırılmış aylık takvim denetimi üst Kapatılmak üzere olduğunu bildirir. Bu bildirim yalnızca DTS_UPDOWN stili ayarlanmamış gönderilir.  
  
-   Dtn_datetımechange Notifies denetiminde gerçekleşen bir değişikliği üst.  
  
-   DTN_FORMAT bir geri çağırma alanında görüntülenecek metni üst gerekli bildirir. Bu bildirim ve geri arama alanları hakkında daha fazla bilgi için bkz: [kullanarak geri arama alanları bir tarih ve Saat Seçici denetimini](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   DTN_FORMATQUERY bir geri çağırma alanında görüntülenen dizesi izin verilen en büyük boyutunu sağlamak için üst ister. Bu bildirim işleme her zaman, denetimin görüntüleme içinde titreşimi azaltma düzgün görüntü çıkış denetimi sağlar. Bu bildirim hakkında daha fazla bilgi için bkz: [kullanarak geri arama alanları bir tarih ve Saat Seçici denetimini](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   DTN_USERSTRING bildirir kullanıcı tarih ve Saat Seçici içeriğini düzenleme tamamlandığını üst kontrol eder. Bu bildirim, yalnızca DTS_APPCANPARSE stili ayarladığınızda gönderilir.  
  
-   Kullanıcı, bir geri çağırma alana yazdığında DTN_WMKEYDOWN üst bildirir. Desteklenen bir tarih ve Saat Seçici denetiminde geri çağırma olmayan alanlar için aynı klavye yanıt benzetmek için bu bildirimi işleyin. Bu bildirim hakkında daha fazla bilgi için bkz: [DTP denetiminde geri çağrı alanlarını destekleyen](http://msdn.microsoft.com/library/windows/desktop/bb761726) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDateTimeCtrl kullanma](../mfc/using-cdatetimectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

