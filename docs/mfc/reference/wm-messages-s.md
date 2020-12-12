---
description: 'Hakkında daha fazla bilgi edinin: WM_ Iletiler: S'
title: 'WM_ İletileri: S'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_SYSDEADCHAR
- ON_WM_SYSKEYDOWN
- ON_WM_STYLECHANGING
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCHAR
- ON_WM_SETFOCUS
- ON_WM_SIZE
- ON_WM_SIZING
- ON_WM_SETCURSOR
- ON_WM_SYSCOMMAND
- ON_WM_SETTINGCHANGE
- ON_WM_SHOWWINDOW
- ON_WM_SYSKEYUP
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSCOLORCHANGE
helpviewer_keywords:
- ON_WM_SIZE [MFC]
- ON_WM_SETFOCUS [MFC]
- ON_WM_SIZING [MFC]
- ON_WM_SYSCHAR [MFC]
- ON_WM_SETTINGCHANGE [MFC]
- ON_WM_SYSDEADCHAR [MFC]
- ON_WM_SHOWWINDOW [MFC]
- ON_WM_STYLECHANGING [MFC]
- ON_WM_SYSCOMMAND [MFC]
- ON_WM_STYLECHANGED [MFC]
- ON_WM_SPOOLERSTATUS [MFC]
- ON_WM_SYSCOLORCHANGE [MFC]
- ON_WM_SETCURSOR [MFC]
- ON_WM_SIZECLIPBOARD [MFC]
- ON_WM_SYSKEYUP [MFC]
- ON_WM_SYSKEYDOWN [MFC]
- WM_ messages
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
ms.openlocfilehash: 6fc1f193569d912e438b19646cd1bb4573855346
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218296"
---
# <a name="wm_-messages-s"></a>WM_ İletileri: S

Aşağıdaki eşleme girdileri işlev prototiptürlerine karşılık gelir.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_WM_SETCURSOR ()|afx_msg BOOL [OnSetCursor](../../mfc/reference/cwnd-class.md#onsetcursor)(CWnd *, UINT, uint);|
|ON_WM_SETFOCUS ()|afx_msg void [OnSetFocus](../../mfc/reference/cwnd-class.md#onsetfocus)(CWnd *);|
|ON_WM_SETTINGCHANGE ()|afx_msg void [Onsettingchange](../../mfc/reference/cwnd-class.md#onsettingchange)(UINT uFlags, LPCTSTR lpszSection);|
|ON_WM_SHOWWINDOW ()|afx_msg void [OnShowWindow](../../mfc/reference/cwnd-class.md#onshowwindow)(bool, UINT);|
|ON_WM_SIZE ()|afx_msg void [OnSize](../../mfc/reference/cwnd-class.md#onsize)(UINT, int, int);|
|ON_WM_SIZECLIPBOARD ()|afx_msg void [OnSizeClipboard](../../mfc/reference/cwnd-class.md#onsizeclipboard)(CWnd *, tanıtıcı);|
|ON_WM_SIZING ()|afx_msg void [Onboyutlandırmayı](../../mfc/reference/cwnd-class.md#onsizing)(UINT, LPRECT);|
|ON_WM_SPOOLERSTATUS ()|afx_msg void [Onspoolerstatus](../../mfc/reference/cwnd-class.md#onspoolerstatus)(UINT, uint);|
|ON_WM_STYLECHANGED ()|afx_msg void [OnStyleChanged](../../mfc/reference/cwnd-class.md#onstylechanged)(Int, LPSTYLESTRUCT);|
|ON_WM_STYLECHANGING ()|afx_msg void [Onstylechanging](../../mfc/reference/cwnd-class.md#onstylechanging)(Int, LPSTYLESTRUCT);|
|ON_WM_SYSCHAR ()|afx_msg void [Onsyschar](../../mfc/reference/cwnd-class.md#onsyschar)(UINT, UINT, uint);|
|ON_WM_SYSCOLORCHANGE ()|afx_msg void [OnSysColorChange](../../mfc/reference/cwnd-class.md#onsyscolorchange)();|
|ON_WM_SYSCOMMAND ()|afx_msg void [OnSysCommand](../../mfc/reference/cwnd-class.md#onsyscommand)(UINT, Long);|
|ON_WM_SYSDEADCHAR ()|afx_msg void [Onsysdeadchar](../../mfc/reference/cwnd-class.md#onsysdeadchar)(UINT, UINT, uint);|
|ON_WM_SYSKEYDOWN ()|afx_msg void [OnSysKeyDown](../../mfc/reference/cwnd-class.md#onsyskeydown)(UINT, UINT, uint);|
|ON_WM_SYSKEYUP ()|afx_msg void [OnSysKeyUp](../../mfc/reference/cwnd-class.md#onsyskeyup)(UINT, UINT, uint);|

## <a name="see-also"></a>Ayrıca bkz.

[İleti haritaları](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ Iletileri için işleyiciler](../../mfc/reference/handlers-for-wm-messages.md)
