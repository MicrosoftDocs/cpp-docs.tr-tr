---
description: 'Hakkında daha fazla bilgi edinin: üst bilgi öğeleri için sürükle ve bırak desteği sağlama'
title: Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: ed42f61220ee2033dbc36e11c18664be3968dddd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248794"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>Üstbilgi Öğeleri için Sürükle ve Bırak Desteği Sağlama

Üstbilgi öğeleri için sürükle ve bırak desteği sağlamak üzere HDS_DRAGDROP stilini belirtin. Üst bilgi öğeleri için sürükle ve bırak desteği, kullanıcıya bir üst bilgi denetiminin üstbilgi öğelerini yeniden sıralama özelliği sağlar. Varsayılan davranış, Sürüklenmekte olan üst bilgi öğesinin bir yarı saydam sürükleme görüntüsünü ve başlık öğesi bırakıldığında yeni konumun görsel göstergesini sağlar.

Ortak sürükle ve bırak işlevlerinde olduğu gibi, HDN_BEGINDRAG ve HDN_ENDDRAG bildirimlerini işleyerek varsayılan sürükle ve bırak davranışını genişletebilirsiniz. Ayrıca, [CHeaderCtrl:: CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) üye işlevini geçersiz kılarak sürükle resminin görünümünü özelleştirebilirsiniz.

> [!NOTE]
> Bir liste denetiminde katıştırılmış üst bilgi denetimi için sürükle ve bırak desteği sağlıyorsanız, [değişen liste denetim stilleri](../mfc/changing-list-control-styles.md) konusunun Genişletilmiş Stil bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)
