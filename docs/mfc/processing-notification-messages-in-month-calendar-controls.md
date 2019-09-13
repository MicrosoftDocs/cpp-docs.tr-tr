---
title: Aylık Takvim Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
ms.openlocfilehash: 452d24bf1ffd157366f357a510e8c8cfaad28d91
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908075"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Aylık Takvim Denetimlerinde Bildirim İletilerini İşleme

Kullanıcılar aylık takvim denetimiyle etkileşime geçerek (tarihleri seçip/veya farklı bir ay görüntülerken) denetim (`CMonthCalCtrl`), bildirim iletilerini üst penceresine (genellikle bir görünüm veya iletişim nesnesi) gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı görüntülemek için yeni bir ay seçtiğinde vurgulamamalıdır bir tarih kümesi sağlayabilirsiniz.

Uygulamak istediğiniz iletilerin üst sınıfına bildirim işleyicileri eklemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın.

Aşağıdaki listede, aylık Takvim denetimi tarafından gönderilen çeşitli bildirimler açıklanmaktadır.

- MCN_GETDAYSTATE, hangi günlerin kalın olarak gösterilmesi gerektiği hakkında bilgi Ister. Bu bildirimi işleme hakkında daha fazla bilgi için, bkz. [bir aylık takvim denetiminin gün durumunu ayarlama](../mfc/setting-the-day-state-of-a-month-calendar-control.md).

- MCN_SELCHANGE, seçili tarih veya tarih aralığının değiştiğini üst öğeye bildirir.

- MCN_SELECT, üst öğeye açık bir tarih seçimi yapıldığını bildirir.

## <a name="see-also"></a>Ayrıca bkz.

[CMonthCalCtrl Kullanma](../mfc/using-cmonthcalctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
