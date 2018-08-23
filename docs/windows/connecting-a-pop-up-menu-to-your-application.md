---
title: Uygulamanıza açılır menü bağlantısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pop-up menus, connecting to applications
- context menus, connecting to applications
- menus, pop-up
- shortcut menus, connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce7a8d53c56e6a17d5ef57222bab725a4addf8fd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581163"
---
# <a name="connecting-a-pop-up-menu-to-your-application"></a>Uygulamanıza Açılır Menü Bağlantısı Yapma

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

[Açılır Menüler Oluşturma](../windows/creating-pop-up-menus.md)  
[Menü Düzenleyicisi](../windows/menu-editor.md)  