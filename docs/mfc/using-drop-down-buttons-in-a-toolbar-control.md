---
description: 'Hakkında daha fazla bilgi edinin: bir araç çubuğu denetiminde Drop-Down düğmeleri kullanma'
title: Bir araç çubuğu denetiminde Drop-Down düğmeleri kullanma
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
ms.openlocfilehash: a37f39397f6b6f66bed1ad1d2fbd9530b55f3d7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154467"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Bir araç çubuğu denetiminde Drop-Down düğmeleri kullanma

Standart gönderme düğmelerine ek olarak, bir araç çubuğu da açılan düğmelere sahip olabilir. Açılan düğme genellikle, bir aşağı açılan okun varlığına göre belirtilir.

> [!NOTE]
> Eklenen aşağı ok yalnızca TBSTYLE_EX_DRAWDDARROWS genişletilmiş stili ayarlandıysa görüntülenir.

Kullanıcı bu oka tıkladığında (veya bir ok yoksa, düğme yoksa), araç çubuğu denetiminin üst öğesine bir TBN_DROPDOWN bildirim iletisi gönderilir. Daha sonra bu bildirimi işleyebilir ve bir açılan menüyü görüntüleyebilirsiniz. Internet Explorer davranışına benzer.

Aşağıdaki yordamda, açılır menü ile açılan bir araç çubuğu düğmesinin nasıl uygulanacağı gösterilmektedir:

### <a name="to-implement-a-drop-down-button"></a>Açılan düğmeyi uygulamak için

1. Nesneniz oluşturulduktan sonra, `CToolBarCtrl` aşağıdaki kodu kullanarak TBSTYLE_EX_DRAWDDARROWS stilini ayarlayın:

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. Açılan düğme olacak yeni ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) veya [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) veya var olan ([setbuttonınfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) düğmelerinin TBSTYLE_DROPDOWN stilini ayarlayın. Aşağıdaki örnek, bir nesnede var olan bir düğmenin değiştirilmesini gösterir `CToolBarCtrl` :

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. Toolbar nesnesinin üst sınıfına bir TBN_DROPDOWN işleyicisi ekleyin.

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. Yeni İşleyicide, uygun açılan menüyü görüntüleyin. Aşağıdaki kod bir yöntemi gösterir:

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
