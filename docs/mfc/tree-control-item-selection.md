---
title: Ağaç denetim öğesi seçimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa9c82a57ff8504c8e3eba7becff1e1cdccaae2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431573"
---
# <a name="tree-control-item-selection"></a>Ağaç Denetim Öğesi Seçimi

Seçimi değiştiğinde bir öğeden diğerine, bir ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) gönderir [TVN_SELCHANGING](/windows/desktop/Controls/tvn-selchanging) ve [TVN_SELCHANGED](/windows/desktop/Controls/tvn-selchanged) bildirim iletileri. Her iki bildirim değişiklik fare tıklatın veya tuş vuruşu sonucu olup olmadığını belirten bir değer içerir. Bildirimler, ayrıca seçimi sağlamasını öğesi ve seçim kaybetme öğesi hakkında bilgiler içerir. Öğe seçimi durumuna bağımlı öğesi öznitelikleri ayarlamak için bu bilgileri kullanabilirsiniz. Döndüren **TRUE** yanıt olarak `TVN_SELCHANGING` döndüren değiştirmesini; seçimi engeller **FALSE** değişiklik sağlar.

Uygulama seçimi çağırarak değiştirebilirsiniz [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) üye işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

