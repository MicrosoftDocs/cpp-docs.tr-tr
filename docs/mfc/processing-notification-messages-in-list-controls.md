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
ms.openlocfilehash: af648a0bf4ae78c5c5e8bcceeac12c5dbc87307a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347682"
---
# <a name="processing-notification-messages-in-list-controls"></a>Liste Denetimlerinde Bildirim İletilerini İşleme
Sütun başlıklarını kullanıcılar tıklatma gibi simgeler sürükleyin, etiketleri ve benzeri, liste denetimini düzenleme ([CListCtrl](../mfc/reference/clistctrl-class.md)) kendi üst penceresi bildirim iletileri gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, kullanıcı bir sütun başlığını tıkladığında, Microsoft Outlook gibi tıklatılan sütunun içeriğine göre öğeleri sıralama isteyebilirsiniz.  
  
 İşlem **wm_notıfy** görünümü ya da iletişim sınıfınızı liste denetiminde gelen iletileri. Özellikler penceresini oluşturulacağı bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyici işleviyle dayalı hangi bildirim iletisi ele alınmasına.  
  
 Liste denetimi, kendi üst penceresi gönderebilir bildirimleri bir listesi için bkz: [liste görünümü denetimi başvurusu](http://msdn.microsoft.com/library/windows/desktop/bb774737) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CListCtrl kullanma](../mfc/using-clistctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

