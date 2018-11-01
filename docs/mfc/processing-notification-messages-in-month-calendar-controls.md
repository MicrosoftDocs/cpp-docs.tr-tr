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
ms.openlocfilehash: 3dbf50080bea59c4df4a9c92a135a65b093f7674
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511936"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Aylık Takvim Denetimlerinde Bildirim İletilerini İşleme

Kullanıcı denetimi (tarihleri seçme ve/veya farklı bir ayın görüntüleme), aylık takvim denetiminin ile etkileşime geçtiğimiz sırada (`CMonthCalCtrl`) üst pencereye bildirim iletilerini gönderen genellikle bir görünüm veya iletişim nesnesi. Yanıt bir şey yapmak istiyorsanız, bu iletileri işler. Örneğin, kullanıcı görüntülemek için yeni bir ayın seçtiğinde vurgulanmış tarih kümesini sağlayabilir.

Üst sınıf uygulamak istediğiniz bu iletileri için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.

Aşağıdaki listede, ay takvimi tarafından gönderilen çeşitli bildirimler açıklanmaktadır.

- MCN_GETDAYSTATE istekleri bilgiler hakkında gün kalın yazı tipinde görüntülenmelidir. Bu bildirim işleme hakkında daha fazla bilgi için bkz: [aylık takvim denetiminin gün durumunu ayarlama](../mfc/setting-the-day-state-of-a-month-calendar-control.md).

- Seçilen tarih veya tarih aralığını değiştirilmiş üst Notifies MCN_SELCHANGE.

- MCN_SELECT Notifies açık tarih seçimi yapılan üst.

## <a name="see-also"></a>Ayrıca Bkz.

[CMonthCalCtrl Kullanma](../mfc/using-cmonthcalctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

