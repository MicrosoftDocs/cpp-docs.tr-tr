---
title: Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: 21ff14982baac93fac1cf3ee441353c079f4f760
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602975"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama

Üstbilgi öğeleri için sürükle ve bırak desteği sağlamak için HDS_DRAGDROP stili belirtin. Üstbilgi öğeleri için sürükle ve bırak desteği, kullanıcı bir üst bilgi denetiminin üst öğeleri yeniden sıralamak olanağı sağlar. Üstbilgi öğesi kesilirse varsayılan davranışı sürüklenen üstbilgi öğesi yarı saydam fırçalarla Sürükle görüntüsü ve yeni konumu, görsel bir gösterge sağlar.

Olarak ortak sürükle ve bırak işleviyle, sürükle ve bırak davranışı HDN_BEGINDRAG ve HDN_ENDDRAG bildirimleri işleyerek genişletebilirsiniz. Geçersiz kılarak görüntüyü Sürükle görünümünü özelleştirebilirsiniz [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) üye işlevi.

> [!NOTE]
>  Liste denetimi bir katıştırılmış üstbilgi denetimindeki için sürükle ve bırak desteği sağlama, genişletilmiş stili bölümüne bakın. [liste denetim stillerini değiştirme](../mfc/changing-list-control-styles.md) konu.

## <a name="see-also"></a>Ayrıca Bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)

