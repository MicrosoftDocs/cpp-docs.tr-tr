---
description: 'Hakkında daha fazla bilgi: WM_ Ileti Işleyicileri: L-M'
title: 'WM_ İleti İşleyicileri: L - M'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_MENUSELECT
- ON_WM_MBUTTONDBLCLK
- ON_WM_MOUSEACTIVATE
- ON_WM_MOUSEMOVE
- ON_WM_MOVING
- ON_WM_LBUTTONUP
- ON_WM_LBUTTONDBLCLK
- ON_WM_MEASUREITEM
- ON_WM_MDIACTIVATE
- ON_WM_MOVE
- ON_WM_LBUTTONDOWN
- ON_WM_MBUTTONDOWN
- ON_WM_MENUCHAR
- ON_WM_MBUTTONUP
helpviewer_keywords:
- ON_WM_MENUSELECT [MFC]
- ON_WM_MBUTTONDBLCLK [MFC]
- ON_WM_MOVE [MFC]
- ON_WM_MOUSEACTIVATE [MFC]
- ON_WM_MBUTTONUP [MFC]
- ON_WM_MOUSEMOVE [MFC]
- ON_WM_MENUCHAR [MFC]
- ON_WM_MBUTTONDOWN [MFC]
- ON_WM_MEASUREITEM [MFC]
- ON_WM_MOVING [MFC]
- ON_WM_LBUTTONDOWN [MFC]
- ON_WM_MDIACTIVATE [MFC]
- ON_WM_LBUTTONDBLCLK [MFC]
- ON_WM_LBUTTONUP [MFC]
- WM_ messages
ms.assetid: 96ecaaf1-6d13-4e12-a454-535635967489
ms.openlocfilehash: 2044f8eeb74c75f92f42c6e0199820528f7c10c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218335"
---
# <a name="wm_-message-handlers-l---m"></a>WM_ İleti İşleyicileri: L - M

Sol taraftaki aşağıdaki harita girdileri sağdaki işlev prototiptürlerine karşılık gelir:

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_WM_LBUTTONDBLCLK ()|afx_msg void [OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk)(UINT, CPoint);|
|ON_WM_LBUTTONDOWN ()|afx_msg void [Onlbuttonazaltma](../../mfc/reference/cwnd-class.md#onlbuttondown)(UINT, CPoint);|
|ON_WM_LBUTTONUP ()|afx_msg void [OnLButtonUp](../../mfc/reference/cwnd-class.md#onlbuttonup)(UINT, CPoint);|
|ON_WM_MBUTTONDBLCLK ()|afx_msg void [OnMButtonDblClk](../../mfc/reference/cwnd-class.md#onmbuttondblclk)(UINT, CPoint);|
|ON_WM_MBUTTONDOWN ()|afx_msg void [Onmbuttonazaltma](../../mfc/reference/cwnd-class.md#onmbuttondown)(UINT, CPoint);|
|ON_WM_MBUTTONUP ()|afx_msg void [Onmbuttonup](../../mfc/reference/cwnd-class.md#onmbuttonup)(UINT, CPoint);|
|ON_WM_MDIACTIVATE ()|afx_msg void [OnMDIActivate](../../mfc/reference/cwnd-class.md#onmdiactivate)(bool, CWnd \* , CWnd \* );|
|ON_WM_MEASUREITEM ()|afx_msg void [OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)(lpMeasureItemStruct);|
|ON_WM_MENUCHAR ()|afx_msg uzun [Onmenuşar](../../mfc/reference/cwnd-class.md#onmenuchar)(UINT, uint, CMenu \* );|
|ON_WM_MENUDRAG ()|afx_msg UINT [Onmenudrag](../../mfc/reference/cwnd-class.md#onmenudrag)(UINT, CMenu \* );|
|ON_WM_MENUGETOBJECT ()|afx_msg UINT [Onmenugetobject](../../mfc/reference/cwnd-class.md#onmenugetobject)(menugetobjectınfo \* );|
|ON_WM_MENURBUTTONUP ()|afx_msg void [Onmenurbuttonup](../../mfc/reference/cwnd-class.md#onmenurbuttonup)(UINT, CMenu \* );|
|ON_WM_MENUSELECT ()|afx_msg void [OnMenuSelect](../../mfc/reference/cwnd-class.md#onmenuselect)(UINT, UINT, HMENU);|
|ON_WM_MOUSEACTIVATE ()|afx_msg int [Onmouseactivate](../../mfc/reference/cwnd-class.md#onmouseactivate)(CWnd \* , uint, uint);|
|ON_WM_MOUSEHOVER ()|afx_msg void [Onmousevurgulu](../../mfc/reference/cwnd-class.md#onmousehover)(UINT, CPoint);|
|ON_WM_MOUSEHWHEEL ()|afx_msg void [Onmousehwheel](../../mfc/reference/cwnd-class.md#onmousehwheel)(UINT, Short, CPoint);|
|ON_WM_MOUSELEAVE ()|afx_msg void [OnMouseLeave](../../mfc/reference/cwnd-class.md#onmouseleave)();|
|ON_WM_MOUSEMOVE ()|afx_msg void [OnMouseMove](../../mfc/reference/cwnd-class.md#onmousemove)(UINT, CPoint);|
|ON_WM_MOUSEWHEEL ()|afx_msg BOOL [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)(UINT, Short, CPoint);|
|ON_WM_MOVE ()|afx_msg void [OnMove](../../mfc/reference/cwnd-class.md#onmove)(int, int);|
|ON_WM_MOVING ()|afx_msg void [Onnakliye](../../mfc/reference/cwnd-class.md#onmoving)(UINT, LPRECT);|

## <a name="see-also"></a>Ayrıca bkz.

[İleti haritaları](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ Iletileri için işleyiciler](../../mfc/reference/handlers-for-wm-messages.md)
