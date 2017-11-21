---
title: "Sekme denetimi bildirim iletilerini işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d5e107485dee3412c24d0348189c0aa483921df5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="processing-tab-control-notification-messages"></a>Sekme Denetimi Bildirim İletilerini İşleme
Kullanıcılar gibi sekmeler veya düğmeler, sekme denetimi ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) kendi üst penceresi bildirim iletileri gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı bir sekme tıklattığında görüntülemeden önce sayfasında denetim önayarlarını isteyebilirsiniz.  
  
 İşlem **wm_notıfy** görünümü ya da iletişim sınıfınızda sekmesi denetim iletileri. Özellikler penceresini oluşturulacağı bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyici işleviyle dayalı hangi bildirim iletisi ele alınmasına. Sekme denetimi, kendi üst penceresi gönderebilir bildirimleri bir listesi için bkz: **bildirimleri** bölümünü [sekme denetimi başvurusu](http://msdn.microsoft.com/library/windows/desktop/bb760548) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTabCtrl kullanma](../mfc/using-ctabctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

