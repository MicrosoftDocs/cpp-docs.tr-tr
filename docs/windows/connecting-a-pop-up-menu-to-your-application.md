---
title: C++ uygulamanıza açılır menü bağlantısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- menus [C++], pop-up
- shortcut menus [C++], connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f1ebb5e2151fe770e6a59210ac564237155fafd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412086"
---
# <a name="connecting-a-pop-up-menu-to-your-c-application"></a>C++ uygulamanıza açılır menü bağlantısı

### <a name="to-connect-a-pop-up-menu-to-your-application"></a>Açılır menü, uygulamanızı bağlamak için

1. Bir ileti işleyicisi WM_CONTEXTMENU için (örneğin) ekleyin. Daha fazla bilgi için [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).

2. Aşağıdaki kodu için ileti işleyicisi ekleyin:

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > [CPoint](../atl-mfc-shared/reference/cpoint-class.md) geçirilen ekran koordinatlarında ileti işleyicisidir.

## <a name="requirements"></a>Gereksinimler

MFC

## <a name="see-also"></a>Ayrıca Bkz.

[Açılır Menüler Oluşturma](../windows/creating-pop-up-menus.md)<br/>
[Menü Düzenleyicisi](../windows/menu-editor.md)  