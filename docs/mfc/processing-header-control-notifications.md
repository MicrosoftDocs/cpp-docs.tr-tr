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
ms.openlocfilehash: f60a0c918476702881984f976b220130727cf4b0
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507939"
---
# <a name="processing-header-control-notifications"></a>Üstbilgi Denetimi Bildirimlerini İşleme

Görünüm veya iletişim işlevinizde, işlemek istediğiniz herhangi bir üstbilgi-Control ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) bildirim iletisi için bir switch Ifadesiyle bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) işleyici işlevi oluşturmak için Özellikler penceresi kullanın (bkz. [iletileri işlevlere eşleme ](../mfc/reference/mapping-messages-to-functions.md)). Kullanıcı bir üst bilgi öğesine tıkladığında veya çift tıkladığı, öğeler arasında bir ayırıcıyı sürüklediğinde ve benzeri bir ana pencereye Bildirimler gönderilir.

Bir üstbilgi denetimiyle ilişkili bildirim iletileri Windows SDK [üst bilgi denetim başvurusunda](/windows/win32/controls/header-control-reference) listelenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
