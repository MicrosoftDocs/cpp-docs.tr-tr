---
title: Araç çubuğu denetiminde açılır düğmeler kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39edda143e28d262e8eea826ced5c24855fb310b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminde Açılır Düğmeler Kullanma
Standart düğmeler yanı sıra bir araç çubuğu açılır düğmeler da sağlayabilirsiniz. Açılan düğmesine bir ekli aşağı ok varlığını tarafından genellikle gösterilir.  
  
> [!NOTE]
>  Ekli aşağı ok yalnızca görünür `TBSTYLE_EX_DRAWDDARROWS` genişletilmiş stili ayarlayın.  
  
 Bu oku (veya düğmesinin kendisini ok mevcut değilse), kullanıcı tıkladığında bir `TBN_DROPDOWN` bildirim iletisi araç çubuğu denetimi üst öğeye gönderilir. Ardından, bu bildirimi tutamacı ve açılır menü görüntüleme; Internet Explorer'ın davranışını benzer.  
  
 Aşağıdaki yordam nasıl açılır menü ile açılan araç çubuğu düğmesi uygulandığını gösterir:  
  
### <a name="to-implement-a-drop-down-button"></a>Açılan düğmesine uygulamak için  
  
1.  Bir kez, `CToolBarCtrl` nesnesi oluşturulamadı, ayarlama `TBSTYLE_EX_DRAWDDARROWS` stili, aşağıdaki kodu kullanarak:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  Ayarlama `TBSTYLE_DROPDOWN` yeni stil herhangi ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) veya [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) veya varolan ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) aşağı açılır düğmeler olacak düğmeler. Aşağıdaki örnek, varolan bir düğmeyi değiştirme gösterir bir `CToolBarCtrl` nesnesi:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  Ekleme bir `TBN_DROPDOWN` araç nesnenin üst sınıfı için işleyici.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  Yeni işleyicisinde uygun açılan menüsünü görüntüler. Aşağıdaki kod bir yöntem gösterilmektedir:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

