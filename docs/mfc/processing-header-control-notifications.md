---
description: 'Hakkında daha fazla bilgi edinin: Header-Control bildirimleri Işleme'
title: Üstbilgi Denetimi Bildirimlerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
ms.openlocfilehash: ac1cdbf5efc3e82cdf417a38072cf344ca2ee1a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154857"
---
# <a name="processing-header-control-notifications"></a>Üstbilgi Denetimi Bildirimlerini İşleme

Görünüm veya iletişim işlevinizde, işlemek istediğiniz herhangi bir üst bilgi denetimi ([CHeaderCtrl](reference/cheaderctrl-class.md)) bildirim iletisi için bir switch Ifadesiyle bir [OnChildNotify](reference/cwnd-class.md#onchildnotify) Işleyici Işlevi oluşturmak için [sınıf Sihirbazı](reference/mfc-class-wizard.md) 'Nı kullanın (bkz. [iletileri işlevlere eşleme](reference/mapping-messages-to-functions.md)). Kullanıcı bir üst bilgi öğesine tıkladığında veya çift tıkladığı, öğeler arasında bir ayırıcıyı sürüklediğinde ve benzeri bir ana pencereye Bildirimler gönderilir.

Bir üstbilgi denetimiyle ilişkili bildirim iletileri Windows SDK [üst bilgi denetim başvurusunda](/windows/win32/controls/header-control-reference) listelenmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](using-cheaderctrl.md)<br/>
[Denetimler](controls-mfc.md)
