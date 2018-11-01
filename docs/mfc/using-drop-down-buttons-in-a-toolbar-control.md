---
title: Bir Araç Çubuğu Denetiminde Açılır Düğmeler Kullanma
ms.date: 11/04/2016
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
ms.openlocfilehash: fe314e0fdff70979dfc858bb89578170f9a9ee02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453502"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminde Açılır Düğmeler Kullanma

Standart düğmeler yanı sıra bir araç çubuğu aşağı açılır düğmeler da olabilir. Bir açılan düğmeye genellikle eklenen aşağı ok varlığını tarafından gösterilir.

> [!NOTE]
>  Yalnızca genişletilmiş TBSTYLE_EX_DRAWDDARROWS alındıysa eklenen aşağı ok görünür.

Kullanıcı bu ok (veya düğmenin kendisini, ok varsa) tıkladığında, araç çubuğu denetiminin üst TBN_DROPDOWN bildirim iletisi gönderilir. Bu bildirim işlemek ve bir açılır menü görüntüler; Internet Explorer'ın davranışına benzer.

Aşağıdaki yordamda, açılır menü ile bir açılan araç çubuğu düğmesinin nasıl uygulanacağını göstermektedir:

### <a name="to-implement-a-drop-down-button"></a>Bir açılan düğmeye uygulamak için

1. Bir kez, `CToolBarCtrl` nesnesi oluşturuldu, aşağıdaki kodu kullanarak TBSTYLE_EX_DRAWDDARROWS stilini ayarlayın:

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. TBSTYLE_DROPDOWN stili için yeni bir ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) veya [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) veya varolan ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) düğmeler, aşağı açılır düğmeler olacaktır. Aşağıdaki örnek, varolan bir düğmeyi içinde değişiklik gösterir. bir `CToolBarCtrl` nesnesi:

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. Araç çubuğu nesnesi üst sınıf TBN_DROPDOWN işleyicisi ekleyin.

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. Yeni işleyicisinde uygun açılan menü görüntüler. Aşağıdaki kod bir yöntemi gösterir:

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

