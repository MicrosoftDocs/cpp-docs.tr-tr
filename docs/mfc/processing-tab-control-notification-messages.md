---
title: Sekme Denetimi Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: 97abde8285a3baf307df79fd97d4f9a379c8f58f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507840"
---
# <a name="processing-tab-control-notification-messages"></a>Sekme Denetimi Bildirim İletilerini İşleme

Kullanıcılar sekmeler veya düğmelere tıklayabilecekleri şekilde sekme denetimi ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), bildirim iletilerini üst penceresine gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, Kullanıcı bir sekmeye tıkladığında, onu görüntülemeden önce sayfadaki denetim verilerini önceden ayarlamak isteyebilirsiniz.

Görünüm veya iletişim sınıfınızın sekme denetiminden WM_NOTIFY iletileri işleyin. Hangi bildirim iletisinin işlendiğini temel alan Switch ifadesiyle bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) işleyici işlevi oluşturmak için Özellikler penceresi kullanın. Bir sekme denetiminin üst penceresine gönderebileceği bildirimlerin listesi için, Windows SDK [sekme denetimi başvurusunun](/windows/win32/controls/tab-control-reference) **Bildirimler** bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
