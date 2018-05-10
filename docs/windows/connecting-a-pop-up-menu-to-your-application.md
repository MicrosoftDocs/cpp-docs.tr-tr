---
title: Uygulamanıza açılır menü bağlanma | Microsoft Docs
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
ms.openlocfilehash: 533fc4eea9299d51183a91febb371ff8142e0a7b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="connecting-a-pop-up-menu-to-your-application"></a>Uygulamanıza Açılır Menü Bağlantısı Yapma
### <a name="to-connect-a-pop-up-menu-to-your-application"></a>Uygulamanıza açılır menü bağlanmak için  
  
1.  Bir ileti işleyicisini WM_CONTEXTMENU için (örneğin) ekleyin. Daha fazla bilgi için bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).  
  
2.  İleti işleyicisi için aşağıdaki kodu ekleyin:  
  
    ```  
    CMenu menu;  
    VERIFY(menu.LoadMenu(IDR_MENU1));  
    CMenu* pPopup = menu.GetSubMenu(0);  
    ASSERT(pPopup != NULL);  
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());  
    ```  
  
    > [!NOTE]
    >  [CPoint](../atl-mfc-shared/reference/cpoint-class.md) **geçirilen ekran koordinatları olarak ileti işleyicisidir.**  
  

  
 **Gereksinimler**  
  
 MFC  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açılır menüler oluşturma](../windows/creating-pop-up-menus.md)   
 [Menü Düzenleyicisi](../windows/menu-editor.md)   
