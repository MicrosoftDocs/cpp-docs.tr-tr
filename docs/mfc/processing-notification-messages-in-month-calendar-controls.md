---
title: Takvim denetimlerinde bildirim iletilerini işleme aydaki | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce9906a738ed6c577f46d2919a5cdac80b877110
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930995"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Aylık Takvim Denetimlerinde Bildirim İletilerini İşleme
Kullanıcı denetimi (tarihleri seçme ve/veya farklı bir ay görüntüleme), aylık takvim denetiminin ile etkileşimli olarak (`CMonthCalCtrl`) üst pencereye, bildirim iletileri gönderir genellikle bir görünüm veya iletişim nesnesi. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı görüntülemek için yeni bir ayın seçtiğinde vurgulanmış tarih kümesini sağlayabilir.  
  
 Üst sınıf uygulamak isterseniz bu iletiler için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.  
  
 Aşağıdaki listede aylık takvim denetiminin tarafından gönderilen çeşitli bildirimler açıklanmaktadır.  
  
-   MCN_GETDAYSTATE istekleri bilgiler hakkında günleri kalın olarak görüntülenmesi gerekir. Bu bildirim işleme hakkında daha fazla bilgi için bkz: [aylık takvim denetiminin gün durumunu ayarlama](../mfc/setting-the-day-state-of-a-month-calendar-control.md).  
  
-   MCN_SELCHANGE Notifies seçili tarih veya tarih aralığı değişti üst.  
  
-   MCN_SELECT Notifies açık tarih seçimi yapılan üst.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CMonthCalCtrl kullanma](../mfc/using-cmonthcalctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

