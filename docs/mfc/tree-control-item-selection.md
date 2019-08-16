---
title: Ağaç Denetim Öğesi Seçimi
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: 07c7b673e0f9029f8ece928b0ab17760b3863cc7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513345"
---
# <a name="tree-control-item-selection"></a>Ağaç Denetim Öğesi Seçimi

Seçim bir öğeden diğerine değiştirdiğinde, ağaç denetimi ([Ctreecu](../mfc/reference/ctreectrl-class.md)) [TVN_SELCHANGING](/windows/win32/Controls/tvn-selchanging) ve [TVN_SELCHANGED](/windows/win32/Controls/tvn-selchanged) bildirim iletileri gönderir. Her iki bildirim de, değişikliğin bir fare tıklaması veya bir tuş vuruşu sonucu olup olmadığını belirten bir değer içerir. Bildirimler ayrıca seçimi karşılayan öğe ve seçimi kaybetmekte olan öğe hakkındaki bilgileri de içerir. Bu bilgiyi, öğenin seçim durumuna bağlı öğe özniteliklerini ayarlamak için kullanabilirsiniz. Yanıtta **true döndürme** seçimin değiştirilmesini engelliyor;falsedöndürmedeğişikliğeizinverir.`TVN_SELCHANGING`

Bir uygulama [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) üye işlevini çağırarak seçimi değiştirebilir.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
