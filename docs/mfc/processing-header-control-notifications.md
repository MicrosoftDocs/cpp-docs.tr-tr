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
ms.openlocfilehash: c313382b8be7538ba5bb465c6ba383955e414662
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619790"
---
# <a name="processing-header-control-notifications"></a>Üstbilgi Denetimi Bildirimlerini İşleme

Görünüm veya iletişim işlevinizde, işlemek istediğiniz herhangi bir üst bilgi denetimi ([CHeaderCtrl](reference/cheaderctrl-class.md)) bildirim iletisi için bir switch Ifadesiyle bir [OnChildNotify](reference/cwnd-class.md#onchildnotify) Işleyici Işlevi oluşturmak için [sınıf Sihirbazı](reference/mfc-class-wizard.md) 'Nı kullanın (bkz. [iletileri işlevlere eşleme](reference/mapping-messages-to-functions.md)). Kullanıcı bir üst bilgi öğesine tıkladığında veya çift tıkladığı, öğeler arasında bir ayırıcıyı sürüklediğinde ve benzeri bir ana pencereye Bildirimler gönderilir.

Bir üstbilgi denetimiyle ilişkili bildirim iletileri Windows SDK [üst bilgi denetim başvurusunda](/windows/win32/controls/header-control-reference) listelenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](using-cheaderctrl.md)<br/>
[Denetimler](controls-mfc.md)
