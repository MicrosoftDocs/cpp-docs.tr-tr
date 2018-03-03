---
title: "Sekme denetimi bildirim iletilerini işleme | Microsoft Docs"
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
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 840ff6fc5dd47a2059e62608b5a5d6f231f8f17c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-tab-control-notification-messages"></a>Sekme Denetimi Bildirim İletilerini İşleme
Kullanıcılar gibi sekmeler veya düğmeler, sekme denetimi ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) kendi üst penceresi bildirim iletileri gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı bir sekme tıklattığında görüntülemeden önce sayfasında denetim önayarlarını isteyebilirsiniz.  
  
 İşlem **wm_notıfy** görünümü ya da iletişim sınıfınızda sekmesi denetim iletileri. Özellikler penceresini oluşturulacağı bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyici işleviyle dayalı hangi bildirim iletisi ele alınmasına. Sekme denetimi, kendi üst penceresi gönderebilir bildirimleri bir listesi için bkz: **bildirimleri** bölümünü [sekme denetimi başvurusu](http://msdn.microsoft.com/library/windows/desktop/bb760548) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTabCtrl kullanma](../mfc/using-ctabctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

