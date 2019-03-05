---
title: Liste Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: 2a7899c74bfcddcdc8d54f7d9eb894553115ad66
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288083"
---
# <a name="processing-notification-messages-in-list-controls"></a>Liste Denetimlerinde Bildirim İletilerini İşleme

Sütun üst bilgilerini kullanıcılar gibi simgeler sürükleyin, etiketler ve benzeri, liste denetimi Düzenle ([CListCtrl](../mfc/reference/clistctrl-class.md)) üst pencereye bildirim iletileri gönderir. Yanıt bir şey yapmak istiyorsanız, bu iletileri işler. Örneğin, kullanıcı bir sütun başlığını tıkladığında Microsoft Outlook gibi tıklandı sütunun içeriğine göre öğeleri sıralamak isteyebilirsiniz.

Görünüm veya iletişim sınıfınızdaki liste denetiminden işlem wm_notıfy iletileri. Oluşturmak için Özellikler penceresini kullanın. bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyicisi işlevini temel hangi bildirim iletisi ele alınır.

Liste denetimi üst pencereye gönderebilir bildirimler listesi için bkz. [liste görünümü denetimi başvuru](/windows/desktop/Controls/list-view-control-reference) Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
