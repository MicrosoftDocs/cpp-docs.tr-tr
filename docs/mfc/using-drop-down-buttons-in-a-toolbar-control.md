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
ms.openlocfilehash: 1e76db0bacd7984c97fd8e2696b3543f6e9bf66b
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953249"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminde Açılır Düğmeler Kullanma
Standart düğmeler yanı sıra bir araç çubuğu açılır düğmeler da sağlayabilirsiniz. Açılan düğmesine bir ekli aşağı ok varlığını tarafından genellikle gösterilir.  
  
> [!NOTE]
>  Yalnızca genişletilmiş stili TBSTYLE_EX_DRAWDDARROWS ayarlanmışsa ekli aşağı ok görünür.  
  
 Kullanıcı bu ok (veya düğmesinin kendisini ok varsa) tıklattığında TBN_DROPDOWN bildirim iletisi araç çubuğu denetimi üst öğeye gönderilir. Ardından, bu bildirimi tutamacı ve açılır menü görüntüleme; Internet Explorer'ın davranışını benzer.  
  
 Aşağıdaki yordam nasıl açılır menü ile açılan araç çubuğu düğmesi uygulandığını gösterir:  
  
### <a name="to-implement-a-drop-down-button"></a>Açılan düğmesine uygulamak için  
  
1.  Bir kez, `CToolBarCtrl` nesnesi oluşturulamadı, aşağıdaki kodu kullanarak TBSTYLE_EX_DRAWDDARROWS stili ayarlayın:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  TBSTYLE_DROPDOWN stili için yeni ayarlayın ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) veya [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) veya varolan ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) aşağı açılır düğmeler olacak düğmeler. Aşağıdaki örnek, varolan bir düğmeyi değiştirme gösterir bir `CToolBarCtrl` nesnesi:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  TBN_DROPDOWN işleyici araç nesnenin üst sınıfı ekleyin.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  Yeni işleyicisinde uygun açılan menüsünü görüntüler. Aşağıdaki kod bir yöntem gösterilmektedir:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

