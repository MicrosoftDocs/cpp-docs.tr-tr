---
title: Denetime Öğe Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 88e008f06fb669db1c13872b1a58555eeb357d86
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304606"
---
# <a name="adding-items-to-the-control"></a>Denetime Öğe Ekleme

Öğeleri liste denetimine eklemek için ([CListCtrl](../mfc/reference/clistctrl-class.md)), çeşitli sürümlerinden birini çağırın [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) hangi bilgilerin elinizde bağlı olarak üye işlevi. Bir sürüm alır bir [LV_ITEM](/windows/desktop/api/commctrl/ns-commctrl-taglvitema) hazırlamanız yapısı. Çünkü `LV_ITEM` listesi denetim öğesini özniteliklerini üzerinde daha fazla denetime sahip, yapısı birçok üye içerir.

(Rapor görünümü) in regard to iki önemli üyeleri `LV_ITEM` yapılar `iItem` ve `iSubItem` üyeleri. `iItem` Yapısı başvuruyor öğenin sıfır tabanlı dizinini üyesidir ve `iSubItem` üyesi olan bir alt veya sıfır tabanlı dizin yapısı bir öğe hakkında bilgi içeriyorsa. Bu iki üyeleri ile her öğe türü ve liste denetimi rapor görünümü'nde olduğunda görüntülenen alt bilgi değerini belirler. Daha fazla bilgi için [CListCtrl::SetItem](../mfc/reference/clistctrl-class.md#setitem).

Diğer üyeleri, öğenin metin, simge, durum ve öğesi verileri belirtin. "Veri öğesi" bir liste görünümü öğesi ile ilişkili bir uygulama tanımlı değeri. Hakkında daha fazla bilgi için `LV_ITEM` yapısı için bkz: [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem).

Diğer sürümleri `InsertItem` üyeleri karşılık gelen bir veya daha fazla ayrı değerler alır `LV_ITEM` yapısı, yalnızca desteklemek istediğiniz üyeleri başlatma etmenize imkan sağlar. Genellikle, liste öğeleri için depolama liste denetimi yönetir, ancak bazı bilgiler uygulamanızda bunun yerine, "geri çağrı öğeleri" kullanarak depolayabileceğiniz Daha fazla bilgi için [geri çağrı öğeleri ve geri çağrı maskesi](../mfc/callback-items-and-the-callback-mask.md) bu konudaki ve [geri çağrı öğeleri ve geri çağrı maskesi](/windows/desktop/Controls/using-list-view-controls) Windows SDK.

Daha fazla bilgi için [liste görünümü öğelerini ekleme ve alt öğelerini](/windows/desktop/Controls/using-list-view-controls).

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
