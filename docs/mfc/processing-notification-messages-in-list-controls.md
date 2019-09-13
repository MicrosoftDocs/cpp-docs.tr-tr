---
title: Liste Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: 92111e3e0a4869ca06b89d2d18d38aab9f10ab7d
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908089"
---
# <a name="processing-notification-messages-in-list-controls"></a>Liste Denetimlerinde Bildirim İletilerini İşleme

Kullanıcılar sütun başlıklarına tıklamaları, simgeleri sürüklemek, etiketleri düzenlemek vb., liste denetimi ([CListCtrl](../mfc/reference/clistctrl-class.md)), bildirim iletilerini ana penceresine gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, Kullanıcı bir sütun başlığına tıkladığında, öğeleri Microsoft Outlook 'ta olduğu gibi, tıklanan sütunun içeriğine göre sıralamak isteyebilirsiniz.

Görünüm veya iletişim sınıfınız içindeki liste denetiminden WM_NOTIFY iletileri işleyin. Hangi bildirim iletisinin işlendiğini temel alan Switch ifadesiyle bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) işleyici işlevi oluşturmak Için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın.

Liste denetiminin üst penceresine gönderebileceği bildirimlerin listesi için, bkz. Windows SDK [liste görünümü Denetim başvurusu](/windows/win32/Controls/list-view-control-reference) .

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
