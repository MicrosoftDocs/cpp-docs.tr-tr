---
title: Ağaç Denetim Öğesi Seçimi
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: a88a2c8ea5b935bbcb1f40b705337ff676d8b8a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363565"
---
# <a name="tree-control-item-selection"></a>Ağaç Denetim Öğesi Seçimi

Seçimi değiştiğinde bir öğeden diğerine, bir ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) gönderir [TVN_SELCHANGING](/windows/desktop/Controls/tvn-selchanging) ve [TVN_SELCHANGED](/windows/desktop/Controls/tvn-selchanged) bildirim iletileri. Her iki bildirim değişiklik fare tıklatın veya tuş vuruşu sonucu olup olmadığını belirten bir değer içerir. Bildirimler, ayrıca seçimi sağlamasını öğesi ve seçim kaybetme öğesi hakkında bilgiler içerir. Öğe seçimi durumuna bağımlı öğesi öznitelikleri ayarlamak için bu bilgileri kullanabilirsiniz. Döndüren **TRUE** yanıt olarak `TVN_SELCHANGING` döndüren değiştirmesini; seçimi engeller **FALSE** değişiklik sağlar.

Uygulama seçimi çağırarak değiştirebilirsiniz [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) üye işlevi.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
