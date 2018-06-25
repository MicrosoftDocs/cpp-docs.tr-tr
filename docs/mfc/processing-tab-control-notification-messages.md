---
title: Sekme denetimi bildirim iletilerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 462d9177b1f6300eb356d052cbdfff3b85db86a1
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928068"
---
# <a name="processing-tab-control-notification-messages"></a>Sekme Denetimi Bildirim İletilerini İşleme
Kullanıcılar gibi sekmeler veya düğmeler, sekme denetimi ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) kendi üst penceresi bildirim iletileri gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı bir sekme tıklattığında görüntülemeden önce sayfasında denetim önayarlarını isteyebilirsiniz.  
  
 Sekme denetimi görünümü ya da iletişim sınıfınızda işlem wm_notıfy iletileri. Özellikler penceresini oluşturulacağı bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyici işleviyle dayalı hangi bildirim iletisi ele alınmasına. Sekme denetimi, kendi üst penceresi gönderebilir bildirimleri bir listesi için bkz: **bildirimleri** bölümünü [sekme denetimi başvurusu](http://msdn.microsoft.com/library/windows/desktop/bb760548) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTabCtrl kullanma](../mfc/using-ctabctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

