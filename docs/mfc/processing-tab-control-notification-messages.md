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
ms.openlocfilehash: 32e1b5954bc3f09f16c5516fc1c143dac716bc41
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693238"
---
# <a name="processing-tab-control-notification-messages"></a>Sekme Denetimi Bildirim İletilerini İşleme

Kullanıcıları gibi sekmeler veya düğmeler, sekme denetiminin ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) üst pencereye bildirim iletileri gönderir. Yanıt bir şey yapmak istiyorsanız, bu iletileri işler. Örneğin, kullanıcı bir sekmeye tıkladığında denetim verilerini görüntülemeden önce sayfasında önceden isteyebilirsiniz.

Sekme denetimi, görünümü veya iletişim kutusu sınıfında gelen işlem wm_notıfy iletileri. Oluşturmak için Özellikler penceresini kullanın. bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi işleyicisi işlevini temel hangi bildirim iletisi ele alınır. Sekme denetimi üst pencereye gönderebilir bildirimler listesi için bkz. **bildirimleri** bölümünü [sekme denetim başvurusu](/windows/desktop/controls/tab-control-reference) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

