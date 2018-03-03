---
title: "Takvim denetimlerinde bildirim iletilerini işleme aydaki | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75b07973b1410c7f8bbaa527876efa9b9f1481a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>Aylık Takvim Denetimlerinde Bildirim İletilerini İşleme
Kullanıcı denetimi (tarihleri seçme ve/veya farklı bir ay görüntüleme), aylık takvim denetiminin ile etkileşimli olarak (`CMonthCalCtrl`) üst pencereye, bildirim iletileri gönderir genellikle bir görünüm veya iletişim nesnesi. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı görüntülemek için yeni bir ayın seçtiğinde vurgulanmış tarih kümesini sağlayabilir.  
  
 Üst sınıf uygulamak isterseniz bu iletiler için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.  
  
 Aşağıdaki listede aylık takvim denetiminin tarafından gönderilen çeşitli bildirimler açıklanmaktadır.  
  
-   **MCN_GETDAYSTATE** hakkında gün görüntülenmesi kalın olarak bilgi ister. Bu bildirim işleme hakkında daha fazla bilgi için bkz: [aylık takvim denetiminin gün durumunu ayarlama](../mfc/setting-the-day-state-of-a-month-calendar-control.md).  
  
-   **MCN_SELCHANGE** seçili tarih veya tarih aralığı değişti üst bildirir.  
  
-   **MCN_SELECT** açık tarih seçimi yapılan üst bildirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CMonthCalCtrl kullanma](../mfc/using-cmonthcalctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

