---
title: Yansımış Pencere İletisi Kimlikleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 6d4ee3483bdfeb88951071bddb748671897a424b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754397"
---
# <a name="reflected-window-message-ids"></a>Yansımış Pencere İletisi Kimlikleri

ActiveX denetimi veya diğer özel denetim oluşturmak için hızlı bir yol, bir pencere alt sınıflamaktır. Daha fazla bilgi için Bkz. [MFC ActiveX Denetimleri: Windows Denetimi'ni alt sınıflandırma.](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)

Denetimin kapsayıcısının alt sınıflı bir Windows denetimi tarafından gönderilen pencere iletilerini almasını önlemek için [COleControl,](../mfc/reference/colecontrol-class.md) belirli pencere iletilerini engellemek ve denetime geri göndermek için bir "yansıtıcı" penceresi oluşturur. Denetim, penceresinde yordamı, daha sonra activex denetimi için uygun eylemleri gerçekleştirerek bu yansıyan iletileri işleyebilir.

Aşağıdaki tablo, ele geçirilen iletileri ve reflektör penceresinin gönderdiği ilgili iletileri gösterir.

|Denetim tarafından gönderilen ileti|Denetime yansıyan ileti|
|---------------------------------|--------------------------------------|
|[Wm_command](/windows/win32/menurc/wm-command)|OCM_COMMAND|
|[WM_CTLCOLORBTN](/windows/win32/Controls/wm-ctlcolorbtn)|OCM_CTLCOLORBTN|
|[WM_CTLCOLOREDIT](/windows/win32/Controls/wm-ctlcoloredit)|OCM_CTLCOLOREDIT|
|[WM_CTLCOLORDLG](/windows/win32/dlgbox/wm-ctlcolordlg)|OCM_CTLCOLORDLG|
|[WM_CTLCOLORLISTBOX](/windows/win32/Controls/wm-ctlcolorlistbox)|OCM_CTLCOLORLISTBOX|
|[WM_CTLCOLORSCROLLBAR](/windows/win32/Controls/wm-ctlcolorscrollbar)|OCM_CTLCOLORSCROLLBAR|
|[WM_CTLCOLORSTATIC](/windows/win32/Controls/wm-ctlcolorstatic)|OCM_CTLCOLORSTATIC|
|[WM_DRAWITEM](/windows/win32/Controls/wm-drawitem)|OCM_DRAWITEM|
|[WM_MEASUREITEM](/windows/win32/Controls/wm-measureitem)|OCM_MEASUREITEM|
|[WM_DELETEITEM](/windows/win32/Controls/wm-deleteitem)|OCM_DELETEITEM|
|[WM_VKEYTOITEM](/windows/win32/Controls/wm-vkeytoitem)|OCM_VKEYTOITEM|
|[WM_CHARTOITEM](/windows/win32/Controls/wm-chartoitem)|OCM_CHARTOITEM|
|[WM_COMPAREITEM](/windows/win32/Controls/wm-compareitem)|OCM_COMPAREITEM|
|[WM_HSCROLL](/windows/win32/Controls/wm-hscroll)|OCM_HSCROLL|
|[WM_VSCROLL](/windows/win32/Controls/wm-vscroll)|OCM_VSCROLL|
|[WM_PARENTNOTIFY](/windows/win32/inputmsg/wm-parentnotify)|OCM_PARENTNOTIFY|
|[Wm_notıfy](/windows/win32/controls/wm-notify)|OCM_NOTIFY|

> [!NOTE]
> Denetim Win32 sisteminde çalışıyorsa, alabileceği çeşitli\* WM_CTLCOLOR iletileri vardır. Daha fazla bilgi için WM_CTLCOLORBTN, WM_CTLCOLORDLG, WM_CTLCOLOREDIT, WM_CTLCOLORLISTBOX, WM_CTLCOLORMSGBOX, WM_CTLCOLORSCROLLBAR, WM_CTLCOLORSTATIC.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri: Bir Windows Denetimini Alt Sınıf Yapma](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)<br/>
[TN062: Windows Denetimleri için İleti Yansıması](../mfc/tn062-message-reflection-for-windows-controls.md)
