---
description: 'Daha fazla bilgi edinin: Ağaç Denetim öğesi seçimi'
title: Ağaç Denetim Öğesi Seçimi
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
ms.openlocfilehash: 46e1256eea3e8175b996a1b6bdfdd7c1de2739d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264043"
---
# <a name="tree-control-item-selection"></a>Ağaç Denetim Öğesi Seçimi

Seçim bir öğeden diğerine değiştirdiğinde, ağaç denetimi ([Ctreecu](../mfc/reference/ctreectrl-class.md)) [TVN_SELCHANGING](/windows/win32/Controls/tvn-selchanging) ve [TVN_SELCHANGED](/windows/win32/Controls/tvn-selchanged) bildirim iletileri gönderir. Her iki bildirim de, değişikliğin bir fare tıklaması veya bir tuş vuruşu sonucu olup olmadığını belirten bir değer içerir. Bildirimler ayrıca seçimi karşılayan öğe ve seçimi kaybetmekte olan öğe hakkındaki bilgileri de içerir. Bu bilgiyi, öğenin seçim durumuna bağlı öğe özniteliklerini ayarlamak için kullanabilirsiniz. Yanıtta **true** döndürme `TVN_SELCHANGING` seçimin değiştirilmesini engelliyor; **false** döndürme değişikliğe izin verir.

Bir uygulama [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) üye işlevini çağırarak seçimi değiştirebilir.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
