---
description: 'Hakkında daha fazla bilgi edinin: aylık takvim denetimlerinde bildirim Iletilerini Işleme'
title: Aylık Takvim Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
ms.openlocfilehash: 4c527bd2c950277d36164ec14c7c714d82d2c812
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154792"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Aylık Takvim Denetimlerinde Bildirim İletilerini İşleme

Kullanıcılar aylık takvim denetimiyle etkileşime geçerek (tarihleri seçip/veya farklı bir ay görüntülerken) denetim ( `CMonthCalCtrl` ), bildirim iletilerini üst penceresine (genellikle bir görünüm veya iletişim nesnesi) gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı görüntülemek için yeni bir ay seçtiğinde vurgulamamalıdır bir tarih kümesi sağlayabilirsiniz.

Uygulamak istediğiniz iletilerin üst sınıfına bildirim işleyicileri eklemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın.

Aşağıdaki listede, aylık Takvim denetimi tarafından gönderilen çeşitli bildirimler açıklanmaktadır.

- MCN_GETDAYSTATE, hangi günlerin kalın olarak gösterilmesi gerektiği hakkında bilgi Ister. Bu bildirimi işleme hakkında daha fazla bilgi için, bkz. [bir aylık takvim denetiminin gün durumunu ayarlama](../mfc/setting-the-day-state-of-a-month-calendar-control.md).

- MCN_SELCHANGE, üst öğeye seçilen tarih veya tarih aralığının değiştiğini bildirir.

- MCN_SELECT, üst öğeye açık bir tarih seçimi yapıldığını bildirir.

## <a name="see-also"></a>Ayrıca bkz.

[CMonthCalCtrl Kullanma](../mfc/using-cmonthcalctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
