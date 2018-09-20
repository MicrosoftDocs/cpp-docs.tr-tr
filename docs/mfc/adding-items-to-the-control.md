---
title: Denetime öğe ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc1d4cefd7d292333c4797afea369104733d117d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385072"
---
# <a name="adding-items-to-the-control"></a>Denetime Öğe Ekleme

Öğeleri liste denetimine eklemek için ([CListCtrl](../mfc/reference/clistctrl-class.md)), çeşitli sürümlerinden birini çağırın [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) hangi bilgilerin elinizde bağlı olarak üye işlevi. Bir sürüm alır bir [LV_ITEM](/windows/desktop/api/commctrl/ns-commctrl-taglvitema) hazırlamanız yapısı. Çünkü `LV_ITEM` listesi denetim öğesini özniteliklerini üzerinde daha fazla denetime sahip, yapısı birçok üye içerir.

(Rapor görünümü) in regard to iki önemli üyeleri `LV_ITEM` yapılar `iItem` ve `iSubItem` üyeleri. `iItem` Yapısı başvuruyor öğenin sıfır tabanlı dizinini üyesidir ve `iSubItem` üyesi olan bir alt veya sıfır tabanlı dizin yapısı bir öğe hakkında bilgi içeriyorsa. Bu iki üyeleri ile her öğe türü ve liste denetimi rapor görünümü'nde olduğunda görüntülenen alt bilgi değerini belirler. Daha fazla bilgi için [CListCtrl::SetItem](../mfc/reference/clistctrl-class.md#setitem).

Diğer üyeleri, öğenin metin, simge, durum ve öğesi verileri belirtin. "Veri öğesi" bir liste görünümü öğesi ile ilişkili bir uygulama tanımlı değeri. Hakkında daha fazla bilgi için `LV_ITEM` yapısı için bkz: [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem).

Diğer sürümleri `InsertItem` üyeleri karşılık gelen bir veya daha fazla ayrı değerler alır `LV_ITEM` yapısı, yalnızca desteklemek istediğiniz üyeleri başlatma etmenize imkan sağlar. Genellikle, liste öğeleri için depolama liste denetimi yönetir, ancak bazı bilgiler uygulamanızda bunun yerine, "geri çağrı öğeleri" kullanarak depolayabileceğiniz Daha fazla bilgi için [geri çağrı öğeleri ve geri çağrı maskesi](../mfc/callback-items-and-the-callback-mask.md) bu konudaki ve [geri çağrı öğeleri ve geri çağrı maskesi](/windows/desktop/Controls/using-list-view-controls) Windows SDK.

Daha fazla bilgi için [liste görünümü öğelerini ekleme ve alt öğelerini](/windows/desktop/Controls/using-list-view-controls).

## <a name="see-also"></a>Ayrıca Bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

