---
title: Araç ipucunu denetimini düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 336ba8466e1d1eefbd07d35c4856b273faea7537
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377376"
---
# <a name="manipulating-the-tool-tip-control"></a>Araç İpucunu Denetimini Düzenleme

Sınıf `CToolTipCtrl` bir Grup üyesinin çeşitli özniteliklerini denetleyen işlevleri sağlayan `CToolTipCtrl` nesne ve araç ipucu penceresi.

Başlangıç, açılan ve araç ipucu windows ayarlamak ve çağrı alınan süreleri reshow [GetDelayTime](../mfc/reference/ctooltipctrl-class.md#getdelaytime) ve [SetDelayTime](../mfc/reference/ctooltipctrl-class.md#setdelaytime).

Aşağıdaki işlevleri ile araç ipucu windows görünümünü değiştirin:

- [GetMargin](../mfc/reference/ctooltipctrl-class.md#getmargin) ve [SetMargin](../mfc/reference/ctooltipctrl-class.md#setmargin) alır ve ayarlar araç ipucu kenarlığı ve aracı arasındaki genişliği İpucu metni.

- [GetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#getmaxtipwidth) ve [SetMaxTipWidth](../mfc/reference/ctooltipctrl-class.md#setmaxtipwidth) aracı en fazla genişliğini alır ve ayarlar penceresi ipucu.

- [GetTipBkColor](../mfc/reference/ctooltipctrl-class.md#gettipbkcolor) ve [SetTipBkColor](../mfc/reference/ctooltipctrl-class.md#settipbkcolor) alır ve ayarlar arka plan rengi araç ipucu penceresi.

- [GetTipTextColor](../mfc/reference/ctooltipctrl-class.md#gettiptextcolor) ve [SetTipTextColor](../mfc/reference/ctooltipctrl-class.md#settiptextcolor) alır ve ayarlar penceresi ipucu aracının metin rengi.

Araç ipucunu denetimini WM_LBUTTONXXX iletileri gibi önemli iletilerinin bildirim almak için sırayla, araç ipucu denetimi için iletileri düzenlemeniz gerekir. Bir çağrı yapmak için bu geçiş için en iyi yöntem olan [CToolTipCtrl::RelayEvent](../mfc/reference/ctooltipctrl-class.md#relayevent), `PreTranslateMessage` sahibi penceresinin işlevi. Aşağıdaki örnekte, olası bir yöntem gösterilmektedir (araç ipucunu denetimini varsayılarak çağrılır `m_ToolTip`):

[!code-cpp[NVC_MFCControlLadenDialog#41](../mfc/codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]

Hemen bir araç ipucu penceresi kaldırmak için çağrı [Pop](../mfc/reference/ctooltipctrl-class.md#pop) üye işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[CToolTipCtrl Kullanma](../mfc/using-ctooltipctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

