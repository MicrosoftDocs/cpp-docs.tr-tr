---
title: Yansımış pencere iletisi kimlikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OCM_CTLCOLORBTN
- OCM_PARENTNOTIFY
- OCM_VKEYTOITEM
- OCM_CTLCOLORSTATIC
- OCM_HSCROLL
- OCM_CHARTOITEM
- OCM_DRAWITEM
- OCM_MEASUREITEM
- OCM_COMPAREITEM
- OCM_COMMAND
- OCM_NOTIFY
- OCM_CTLCOLORMSGBOX
- OCM_DELETEITEM
- OCM_CTLCOLORLISTBOX
- OCM_CTLCOLORDLG
- OCM_CTLCOLOREDIT
- OCM_CTLCOLORSCROLLBAR
- OCM_VSCROLL
- OCM_CTLCOLOR
dev_langs:
- C++
helpviewer_keywords:
- OCM_HSCROLL message [MFC]
- OCM_PARENTNOTIFY message [MFC]
- messages, reflected
- reflected messages, window message Ids
- OCM_CTLCOLORDLG message [MFC]
- OCM_COMMAND message [MFC]
- OCM_CTLCOLORMSGBOX message [MFC]
- OCM_COMPAREITEM message [MFC]
- OCM_DRAWITEM message [MFC]
- OCM_VSCROLL message [MFC]
- OCM_CTLCOLOREDIT message [MFC]
- OCM_VKEYTOITEM message [MFC]
- OCM_CHARTOITEM message [MFC]
- OCM_CTLCOLORBTN message [MFC]
- OCM_CTLCOLORSTATIC message [MFC]
- OCM_MEASUREITEM message [MFC]
- OCM_CTLCOLOR message [MFC]
- OCM_CTLCOLORSCROLLBAR message [MFC]
- OCM_ messages
- OCM_DELETEITEM message [MFC]
- OCM_CTLCOLORLISTBOX message [MFC]
- OCM_NOTIFY message [MFC]
- reflected messages
ms.assetid: 3417ff51-ff9f-458c-bff4-17c200f00d96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 037eaa864f4b24622fdd72e15674fb8489f9b4bb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220020"
---
# <a name="reflected-window-message-ids"></a>Yansımış Pencere İletisi Kimlikleri
ActiveX denetimi veya başka özel denetim oluşturmak için hızlı bir şekilde alt sınıfı için bir penceredir. Daha fazla bilgi için [MFC ActiveX denetimleri: bir Windows denetimini alt sınıf yapma](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
 Denetimin kapsayıcı sınıflandırılmış bir Windows Denetim tarafından gönderilen pencere iletilerini almasını önlemek için [COleControl](../mfc/reference/colecontrol-class.md) belirli pencere iletilerini kesebilir ve bunları denetime geri göndermek için bir "reflector" pencere oluşturur. Denetimi alt pencere yordamı, bir ActiveX denetimi için uygun eylemleri gerçekleştirerek bu yansımış iletiler ardından işleyebilir.  
  
 Aşağıdaki tabloda, yakalanan iletiler ve reflector pencerenin gönderen karşılık gelen iletileri gösterir.  
  
|Denetim tarafından gönderilen ileti|İleti denetimine yansıtılır|  
|---------------------------------|--------------------------------------|  
|[WM_COMMAND](/windows/desktop/menurc/wm-command)|OCM_COMMAND|  
|[WM_CTLCOLORBTN](/windows/desktop/Controls/wm-ctlcolorbtn)|OCM_CTLCOLORBTN|  
|[WM_CTLCOLOREDIT](/windows/desktop/Controls/wm-ctlcoloredit)|OCM_CTLCOLOREDIT|  
|[WM_CTLCOLORDLG](/windows/desktop/dlgbox/wm-ctlcolordlg)|OCM_CTLCOLORDLG|  
|[WM_CTLCOLORLISTBOX](/windows/desktop/Controls/wm-ctlcolorlistbox)|OCM_CTLCOLORLISTBOX|  
|[WM_CTLCOLORSCROLLBAR](/windows/desktop/Controls/wm-ctlcolorscrollbar)|OCM_CTLCOLORSCROLLBAR|  
|[WM_CTLCOLORSTATIC](/windows/desktop/Controls/wm-ctlcolorstatic)|OCM_CTLCOLORSTATIC|  
|[WM_DRAWITEM](/windows/desktop/Controls/wm-drawitem)|OCM_DRAWITEM|  
|[WM_MEASUREITEM](/windows/desktop/Controls/wm-measureitem)|OCM_MEASUREITEM|  
|[WM_DELETEITEM](/windows/desktop/Controls/wm-deleteitem)|OCM_DELETEITEM|  
|[WM_VKEYTOITEM](/windows/desktop/Controls/wm-vkeytoitem)|OCM_VKEYTOITEM|  
|[WM_CHARTOITEM](/windows/desktop/Controls/wm-chartoitem)|OCM_CHARTOITEM|  
|[WM_COMPAREITEM](/windows/desktop/Controls/wm-compareitem)|OCM_COMPAREITEM|  
|[WM_HSCROLL](/windows/desktop/Controls/wm-hscroll)|OCM_HSCROLL|  
|[WM_VSCROLL](/windows/desktop/Controls/wm-vscroll)|OCM_VSCROLL|  
|[WM_PARENTNOTIFY](/previous-versions/windows/desktop/inputmsg/wm-parentnotify)|OCM_PARENTNOTIFY|  
|[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)|OCM_NOTIFY|  
  
> [!NOTE]
>  Denetim bir Win32 sistemde çalıştırıyorsa, birden fazla WM_CTLCOLOR vardır\* iletileri da alabilirsiniz. Daha fazla bilgi için bkz: WM_CTLCOLORBTN, WM_CTLCOLORDLG, WM_CTLCOLOREDIT, WM_CTLCOLORLISTBOX, WM_CTLCOLORMSGBOX, WM_CTLCOLORSCROLLBAR, WM_CTLCOLORSTATIC.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri: bir Windows denetimini alt sınıf yapma](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)   
 [TN062: Windows Denetimleri için İleti Yansıması](../mfc/tn062-message-reflection-for-windows-controls.md)

