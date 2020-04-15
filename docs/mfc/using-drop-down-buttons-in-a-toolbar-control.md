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
ms.openlocfilehash: 0bc4df4c07ec4b8bc5b488925cbb140609302186
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365062"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminde Açılır Düğmeler Kullanma

Standart basma düğmelerine ek olarak, araç çubuğunda açılır düğmeler de olabilir. Açılır düğme genellikle ekli bir aşağı ok varlığı ile gösterilir.

> [!NOTE]
> Ekli aşağı ok yalnızca TBSTYLE_EX_DRAWDDARROWS genişletilmiş stil ayarlanmışsa görünür.

Kullanıcı bu oku tıklattığında (veya düğmenin kendisi, ok yoksa), araç çubuğu denetiminin üst öğesine bir TBN_DROPDOWN bildirim iletisi gönderilir. Daha sonra bu bildirimi işleyebilir ve bir açılır menü görüntüleyebilirsiniz; Internet Explorer'ın davranışına benzer.

Aşağıdaki yordam, açılır menüyle açılır araç çubuğu düğmesinin nasıl uygulanacağını gösterir:

### <a name="to-implement-a-drop-down-button"></a>Açılır düğmeyi uygulamak için

1. Nesneniz `CToolBarCtrl` oluşturulduktan sonra, aşağıdaki kodu kullanarak TBSTYLE_EX_DRAWDDARROWS stilini ayarlayın:

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. Herhangi bir yeni[(InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) veya [AddButtons)](../mfc/reference/ctoolbarctrl-class.md#addbuttons)veya açılan düğmeler olacak mevcut[(SetButtonInfo)](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)düğmeleri için TBSTYLE_DROPDOWN stilini ayarlayın. Aşağıdaki örnek, bir `CToolBarCtrl` nesnede varolan bir düğmeyi değiştirmeyi gösterir:

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. Araç çubuğu nesnesinin üst sınıfına TBN_DROPDOWN işleyicisi ekleyin.

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. Yeni işleyicide, uygun açılır menüyü görüntüleyin. Aşağıdaki kod bir yöntemi gösterir:

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
