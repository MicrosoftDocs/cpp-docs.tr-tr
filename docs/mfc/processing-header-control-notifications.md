---
title: Üstbilgi denetimi bildirimlerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd7c6fa8a85aee06aca3b1bf804a06df428e82cb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387763"
---
# <a name="processing-header-control-notifications"></a>Üstbilgi Denetimi Bildirimlerini İşleme

Görünüm veya iletişim kutusu sınıfında oluşturmak için Özellikler penceresini kullanın. bir [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch deyimi için herhangi bir üst bilgi denetimi işleyicisi işlevini ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) istediğiniz bildirim iletileri işleme (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)). Kullanıcı tıkladığında veya öğeleri vb. arasında bir ayırıcı etkileyen bir üstbilgi öğesi çift tıklamaları birbirinden ayırma bildirimleri üst pencereye gönderilir.

Üstbilgi denetimiyle ilişkili bildirim iletilerini listelenen [üstbilgi denetim başvurusu](https://msdn.microsoft.com/library/windows/desktop/bb775239) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

