---
title: Liste denetimlerinde bildirim iletilerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3362074ce0f8d4d7a3a3463d22f9089f847e747d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208716"
---
# <a name="processing-notification-messages-in-list-controls"></a>Liste Denetimlerinde Bildirim İletilerini İşleme
Sütun üst bilgilerini kullanıcılar gibi simgeler sürükleyin, etiketler ve benzeri, liste denetimi Düzenle ([CListCtrl](../mfc/reference/clistctrl-class.md)) üst pencereye bildirim iletileri gönderir. Yanıt bir şey yapmak istiyorsanız, bu iletileri işler. Örneğin, kullanıcı bir sütun başlığını tıkladığında Microsoft Outlook gibi tıklandı sütunun içeriğine göre öğeleri sıralamak isteyebilirsiniz.  
  
 Görünüm veya iletişim sınıfınızdaki liste denetiminden işlem wm_notıfy iletileri. Oluşturmak için Özellikler penceresini kullanın. bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyicisi işlevini temel hangi bildirim iletisi ele alınır.  
  
 Liste denetimi üst pencereye gönderebilir bildirimler listesi için bkz. [liste görünümü denetimi başvuru](/windows/desktop/Controls/list-view-control-reference) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

