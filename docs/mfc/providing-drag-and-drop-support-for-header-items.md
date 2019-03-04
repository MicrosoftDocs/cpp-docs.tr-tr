---
title: Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: f30ad029742a01280abda85cbd1a81104d01d8cd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263728"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama

Üstbilgi öğeleri için sürükle ve bırak desteği sağlamak için HDS_DRAGDROP stili belirtin. Üstbilgi öğeleri için sürükle ve bırak desteği, kullanıcı bir üst bilgi denetiminin üst öğeleri yeniden sıralamak olanağı sağlar. Üstbilgi öğesi kesilirse varsayılan davranışı sürüklenen üstbilgi öğesi yarı saydam fırçalarla Sürükle görüntüsü ve yeni konumu, görsel bir gösterge sağlar.

Olarak ortak sürükle ve bırak işleviyle, sürükle ve bırak davranışı HDN_BEGINDRAG ve HDN_ENDDRAG bildirimleri işleyerek genişletebilirsiniz. Geçersiz kılarak görüntüyü Sürükle görünümünü özelleştirebilirsiniz [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) üye işlevi.

> [!NOTE]
>  Liste denetimi bir katıştırılmış üstbilgi denetimindeki için sürükle ve bırak desteği sağlama, genişletilmiş stili bölümüne bakın. [liste denetim stillerini değiştirme](../mfc/changing-list-control-styles.md) konu.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)
