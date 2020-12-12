---
description: 'Hakkında daha fazla bilgi: WM_ Ileti Işleyicileri: F-K'
title: 'WM_ İleti İşleyicileri: F - K'
ms.date: 11/27/2018
f1_keywords:
- ON_WM_FONTCHANGE
- ON_WM_ICONERASEBKGND
- ON_WM_KEYDOWN
- ON_WM_GETMINMAXINFO
- ON_WM_KEYUP
- ON_WM_HSCROLL
- ON_WM_KILLFOCUS
- ON_WM_HSCROLLCLIPBOARD
- ON_WM_GETDLGCODE
- ON_WM_HELPINFO
- ON_WM_INITMENUPOPUP
- ON_WM_INITMENU
helpviewer_keywords:
- ON_WM_HELPINFO [MFC]
- ON_WM_KILLFOCUS [MFC]
- ON_WM_GETMINMAXINFO [MFC]
- ON_WM_KEYUP [MFC]
- ON_WM_HSCROLL [MFC]
- ON_WM_INITMENUPOPUP [MFC]
- ON_WM_FONTCHANGE [MFC]
- ON_WM_ICONERASEBKGND [MFC]
- ON_WM_GETDLGCODE [MFC]
- ON_WM_HSCROLLCLIPBOARD [MFC]
- ON_WM_INITMENU [MFC]
- WM_ messages [MFC]
- ON_WM_KEYDOWN [MFC]
ms.assetid: 0e7de191-1499-499f-859c-62742797808e
ms.openlocfilehash: 91fb2448862dd70a852191f021244571813b0102
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218348"
---
# <a name="wm_-message-handlers-f---k"></a>WM_ İleti İşleyicileri: F - K

Sol taraftaki aşağıdaki harita girdileri sağdaki işlev prototiptürlerine karşılık gelir:

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_WM_FONTCHANGE ()|afx_msg void [Onfontchange](../../mfc/reference/cwnd-class.md#onfontchange)();|
|ON_WM_GETDLGCODE ()|afx_msg UINT [Ongetdlcode](../../mfc/reference/cwnd-class.md#ongetdlgcode)();|
|ON_WM_GETMINMAXINFO ()|afx_msg void [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)(MINMAXINFO *);|
|ON_WM_HELPINFO ()|afx_msg BOOL [OnHelpInfo](../../mfc/reference/cwnd-class.md#onhelpinfo)(HELPINFO *);|
|ON_WM_HOTKEY ()|afx_msg void [Onkısayol](../../mfc/reference/cwnd-class.md#onhotkey)(UINT, UINT, uint);|
|ON_WM_HSCROLL ()|afx_msg void [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)(UINT, uint, CWnd *);|
|ON_WM_HSCROLLCLIPBOARD ()|afx_msg void [Onhscrollclipboard](../../mfc/reference/cwnd-class.md#onhscrollclipboard)(CWnd *, UINT, uint);|
|ON_WM_ICONERASEBKGND ()|afx_msg geçersiz [Oniconsilinebilir Sebkplan](../../mfc/reference/cwnd-class.md#oniconerasebkgnd)(CDC *);|
|ON_WM_INITMENU ()|afx_msg void [OnInitMenu](../../mfc/reference/cwnd-class.md#oninitmenu)(CMenu *);|
|ON_WM_INITMENUPOPUP ()|afx_msg void [OnInitMenuPopup](../../mfc/reference/cwnd-class.md#oninitmenupopup)(CMenu *, UINT, bool);|
|ON_WM_INPUT ()|afx_msg void [Onrawinput](../../mfc/reference/cwnd-class.md#onrawinput)(UINT, HRAWINPUT);|
|ON_WM_INPUT_DEVICE_CHANGE ()|afx_msg void [Onınputdevicechange](../../mfc/reference/cwnd-class.md#oninputdevicechange)(işaretsiz Short);|
|ON_WM_INPUTLANGCHANGE ()|afx_msg void [Onınputlangchange](../../mfc/reference/cwnd-class.md#oninputlangchange)(Byte, UINT);|
|ON_WM_INPUTLANGCHANGEREQUEST ()|afx_msg void [Onınputlangchangerequest](../../mfc/reference/cwnd-class.md#oninputlangchangerequest)(UINT, hkl);|
|ON_WM_KEYDOWN ()|afx_msg void [OnKeyDown](../../mfc/reference/cwnd-class.md#onkeydown)(UINT, UINT, uint);|
|ON_WM_KEYUP ()|afx_msg void [OnKeyUp](../../mfc/reference/cwnd-class.md#onkeyup)(UINT, UINT, uint);|
|ON_WM_KILLFOCUS ()|afx_msg void [OnKillFocus](../../mfc/reference/cwnd-class.md#onkillfocus)(CWnd *);|

## <a name="see-also"></a>Ayrıca bkz.

[İleti haritaları](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ Iletileri için işleyiciler](../../mfc/reference/handlers-for-wm-messages.md)
