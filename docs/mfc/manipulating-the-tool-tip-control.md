---
description: 'Hakkında daha fazla bilgi edinin: araç Ipucu denetimini düzenleme'
title: Araç İpucunu Denetimini Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
ms.openlocfilehash: f04a2a9fe7d9b32d4b0fab1c6fea0d82f48cbf1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281073"
---
# <a name="manipulating-the-tool-tip-control"></a>Araç İpucunu Denetimini Düzenleme

Sınıfı, `CToolTipCtrl` `CToolTipCtrl` nesne ve araç ipucu penceresinin çeşitli özniteliklerini denetleyen bir üye işlevleri grubu sağlar.

Araç ipucu pencerelerinin ilk, açılan ve resme süreleri [GetDelayTime](reference/ctooltipctrl-class.md#getdelaytime) ve [SetDelayTime](reference/ctooltipctrl-class.md#setdelaytime)çağrılarıyla ayarlanabilir ve geri alınabilir.

Araç ipucu pencerelerinin görünüşünü aşağıdaki işlevlerle değiştirin:

- [GetMargin](reference/ctooltipctrl-class.md#getmargin) ve [SetMargin](reference/ctooltipctrl-class.md#setmargin) , araç ipucu kenarlığı ve araç ipucu metni arasındaki genişliği alır ve ayarlar.

- [Getmaxtıpwidth](reference/ctooltipctrl-class.md#getmaxtipwidth) ve [SetMaxTipWidth](reference/ctooltipctrl-class.md#setmaxtipwidth) , araç ipucu penceresinin en büyük genişliğini alır ve ayarlar.

- [GetTipBkColor](reference/ctooltipctrl-class.md#gettipbkcolor) ve [SetTipBkColor](reference/ctooltipctrl-class.md#settipbkcolor) araç ipucu penceresinin arka plan rengini alır ve ayarlar.

- [GetTipTextColor](reference/ctooltipctrl-class.md#gettiptextcolor) ve [SetTipTextColor](reference/ctooltipctrl-class.md#settiptextcolor) , araç ipucu penceresinin metin rengini alır ve ayarlar.

Araç ipucu denetimine WM_LBUTTONXXX iletileri gibi önemli mesajlar bildirilmeye yönelik iletileri araç ipucu denetimine geçirmeli. Bu geçiş için en iyi yöntem, sahip penceresinin işlevinde [CToolTipCtrl:: RelayEvent](reference/ctooltipctrl-class.md#relayevent)için bir çağrı yapmak içindir `PreTranslateMessage` . Aşağıdaki örnek, olası bir yöntemi gösterir (araç ipucu denetiminin çağrıldığı varsayılarak `m_ToolTip` ):

[!code-cpp[NVC_MFCControlLadenDialog#41](codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]

Bir araç ipucu penceresini hemen kaldırmak için, [pop](reference/ctooltipctrl-class.md#pop) üye işlevini çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[CToolTipCtrl Kullanma](using-ctooltipctrl.md)<br/>
[Denetimler](controls-mfc.md)
