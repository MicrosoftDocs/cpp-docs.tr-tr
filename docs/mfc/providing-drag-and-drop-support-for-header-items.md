---
title: Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: 8dfaabf3da62c216d3da662f59c57b63e695d9ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371159"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama

Üstbilgi öğeleri için sürükle ve bırak desteği sağlamak için HDS_DRAGDROP stilini belirtin. Üstbilgi öğeleri için sürükle ve bırak desteği, kullanıcıya üstbilgi denetiminin üstbilgi öğelerini yeniden sıralama olanağı sağlar. Varsayılan davranış, üstbilgi öğesi bırakılırsa, üstbilgi öğesinin sürüklenen yarı saydam sürükleme görüntüsünü ve yeni konumun görsel bir göstergesini sağlar.

Ortak sürükle ve bırak işlevlerinde olduğu gibi, HDN_BEGINDRAG ve HDN_ENDDRAG bildirimleri işleyerek varsayılan sürükle ve bırak davranışını genişletebilirsiniz. [Ayrıca CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) üye işlevini geçersiz kılarak sürükleme görüntüsünün görünümünü özelleştirebilirsiniz.

> [!NOTE]
> Liste denetiminde katıştırılmış üstbilgi denetimi için sürükle ve bırak desteği sağlıyorsanız, [Liste Denetim Stillerini Değiştirme](../mfc/changing-list-control-styles.md) konusundaki Genişletilmiş Stil bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)
