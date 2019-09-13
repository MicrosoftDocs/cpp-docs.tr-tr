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
ms.openlocfilehash: cc322a038717d48f440df1ec571674cec80743ce
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908072"
---
# <a name="processing-tab-control-notification-messages"></a>Sekme Denetimi Bildirim İletilerini İşleme

Kullanıcılar sekmeler veya düğmelere tıklayabilecekleri şekilde sekme denetimi ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), bildirim iletilerini üst penceresine gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, Kullanıcı bir sekmeye tıkladığında, onu görüntülemeden önce sayfadaki denetim verilerini önceden ayarlamak isteyebilirsiniz.

Görünüm veya iletişim sınıfınızın sekme denetiminden WM_NOTIFY iletileri işleyin. Hangi bildirim iletisinin işlendiğini temel alan Switch ifadesiyle bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) işleyici işlevi oluşturmak Için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın. Bir sekme denetiminin üst penceresine gönderebileceği bildirimlerin listesi için, Windows SDK [sekme denetimi başvurusunun](/windows/win32/controls/tab-control-reference) **Bildirimler** bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
