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
ms.openlocfilehash: 75b19033a31d707fcc87c1b5c824acffca725c96
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441983"
---
# <a name="processing-tab-control-notification-messages"></a>Sekme Denetimi Bildirim İletilerini İşleme

Kullanıcıları gibi sekmeler veya düğmeler, sekme denetiminin ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) üst pencereye bildirim iletileri gönderir. Yanıt bir şey yapmak istiyorsanız, bu iletileri işler. Örneğin, kullanıcı bir sekmeye tıkladığında denetim verilerini görüntülemeden önce sayfasında önceden isteyebilirsiniz.

Sekme denetimi, görünümü veya iletişim kutusu sınıfında gelen işlem wm_notıfy iletileri. Oluşturmak için Özellikler penceresini kullanın. bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyicisi işlevini temel hangi bildirim iletisi ele alınır. Sekme denetimi üst pencereye gönderebilir bildirimler listesi için bkz. **bildirimleri** bölümünü [sekme denetim başvurusu](https://msdn.microsoft.com/library/windows/desktop/bb760548) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

