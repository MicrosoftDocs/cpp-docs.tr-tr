---
title: Üstbilgi Denetimi Bildirimlerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
ms.openlocfilehash: bc811763fe3f4717b8baaeb4a23df1ae59bb1979
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908132"
---
# <a name="processing-header-control-notifications"></a>Üstbilgi Denetimi Bildirimlerini İşleme

Görünüm veya iletişim işlevinizde, işlemek istediğiniz herhangi bir başlık denetimi ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) bildirim iletisi için bir switch Ifadesiyle bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) Işleyici Işlevi oluşturmak için [sınıf Sihirbazı](reference/mfc-class-wizard.md) 'Nı kullanın (bkz. [iletileri eşleme İşlevler](../mfc/reference/mapping-messages-to-functions.md)). Kullanıcı bir üst bilgi öğesine tıkladığında veya çift tıkladığı, öğeler arasında bir ayırıcıyı sürüklediğinde ve benzeri bir ana pencereye Bildirimler gönderilir.

Bir üstbilgi denetimiyle ilişkili bildirim iletileri Windows SDK [üst bilgi denetim başvurusunda](/windows/win32/controls/header-control-reference) listelenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
