---
title: Denetimlerinde bildirim iletilerini işleme tarih ve Saat Seçici | Microsoft Docs
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
ms.openlocfilehash: 7a1a3d4e224b1bcbc9a808387860a07c8ec85a0a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213606"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>Tarih ve Saat Seçici Denetimlerinde Bildirim İletilerini İşleme
Kullanıcıların etkileşimli olarak tarih ve Saat Seçici denetimini, denetimi (`CDateTimeCtrl`) üst pencereye bildirim iletilerini gönderen genellikle bir görünüm veya iletişim nesnesi. Yanıt bir şey yapmak istiyorsanız, bu iletileri işler. Örneğin, tarih ve Saat Seçici katıştırılmış aylık takvim denetiminin görüntülemek için kullanıcı oturum açtığında, DTN_DROPDOWN bildirimi gönderilir.  
  
 Üst sınıf uygulamak istediğiniz bu iletileri için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.  
  
 Aşağıdaki listede, tarih ve Saat Seçici denetim tarafından gönderilen çeşitli bildirimler açıklanmaktadır.  
  
-   DTN_DROPDOWN katıştırılmış aylık takvim denetimi üst gösterilmek üzere olduğunu bildirir. Bu bildirim yalnızca DTS_UPDOWN stili ayarlanmamışsa gönderilir. Bu bildirim hakkında daha fazla bilgi için bkz. [katıştırılmış aylık takvim denetiminin erişme](../mfc/accessing-the-embedded-month-calendar-control.md).  
  
-   DTN_CLOSEUP katıştırılmış aylık takvim denetimi üst Kapatılmak üzere olduğunu bildirir. Bu bildirim yalnızca DTS_UPDOWN stili ayarlanmamışsa gönderilir.  
  
-   Dtn_datetımechange Notifies denetiminde bir değişikliği oluştu üst.  
  
-   DTN_FORMAT bildirir, bir geri çağırma alanında gösterilecek metin üst gerekli. Bu bildirim ve geri çağrı alanlarını hakkında daha fazla bilgi için bkz. [bir tarih ve Saat Seçici denetiminin geri çağrı alanlarını kullanma](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   DTN_FORMATQUERY geri çağırma alanında gösterilecek dizesi izin verilen en büyük boyutunu sağlamak için üst ister. Bu bildirim işleme, her zaman, denetimin görüntü içinde titreşimi düzgün görünen çıkış denetimi sağlar. Bu bildirim hakkında daha fazla bilgi için bkz. [bir tarih ve Saat Seçici denetiminin geri çağrı alanlarını kullanma](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
-   DTN_USERSTRING bildirir, kullanıcının tarih ve Saat Seçici içeriğini düzenlemeyi bitirdiğini üst denetim. Bu bildirim, yalnızca DTS_APPCANPARSE stili ayarladığınızda gönderilir.  
  
-   Kullanıcı geri çağırma alanında yazdığında DTN_WMKEYDOWN üste bildirir. Desteklenen bir tarih ve Saat Seçici denetiminde geri çağrı olmayan alanlarını için aynı klavye yanıt öykünmek için bu bildirimi işleyin. Bu bildirim hakkında daha fazla bilgi için bkz. [DTP denetiminde geri çağrı alanlarını destekleyen](/windows/desktop/Controls/date-and-time-picker-controls) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDateTimeCtrl kullanma](../mfc/using-cdatetimectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

