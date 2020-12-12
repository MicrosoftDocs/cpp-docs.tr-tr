---
description: 'Hakkında daha fazla bilgi: WM_ Ileti Işleyicileri: N-O'
title: 'WM_ İleti İşleyicileri: N - O'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_NCHITTEST
- ON_WM_NCLBUTTONDOWN
- ON_WM_NCCALCSIZE
- ON_WM_NCLBUTTONUP
- ON_WM_NCPAINT
- ON_WM_NCMBUTTONUP
- ON_WM_NCCREATE
- ON_WM_NCACTIVATE
- ON_WM_NCMOUSEMOVE
- ON_WM_NCRBUTTONDBLCLK
- ON_WM_NCLBUTTONDBLCLK
- ON_WM_NCDESTROY
- ON_WM_NCMBUTTONDBLCLK
- ON_WM_NCRBUTTONDOWN
- ON_WM_NCRBUTTONUP
- ON_WM_NCMBUTTONDOWN
helpviewer_keywords:
- ON_WM_NCCALCSIZE [MFC]
- ON_WM_NCMBUTTONDOWN [MFC]
- ON_WM_NCRBUTTONDBLCLK [MFC]
- ON_WM_NCMBUTTONDBLCLK [MFC]
- ON_WM_NCLBUTTONDBLCLK [MFC]
- ON_WM_NCDESTROY [MFC]
- ON_WM_NCRBUTTONDOWN [MFC]
- ON_WM_NCLBUTTONDOWN [MFC]
- ON_WM_NCCREATE [MFC]
- ON_WM_NCRBUTTONUP [MFC]
- ON_WM_NCLBUTTONUP [MFC]
- ON_WM_NCPAINT [MFC]
- ON_WM_NCACTIVATE [MFC]
- ON_WM_NCHITTEST [MFC]
- ON_WM_NCMOUSEMOVE [MFC]
- ON_WM_NCMBUTTONUP [MFC]
- WM_ messages
ms.assetid: 4efd1cda-b642-4e8b-89e8-73255fa70d77
ms.openlocfilehash: 2f70bd0d019b4cdc9557c87c3ae0bb51e330723f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218322"
---
# <a name="wm_-message-handlers-n---o"></a>WM_ İleti İşleyicileri: N - O

Sol taraftaki aşağıdaki harita girdileri sağdaki işlev prototiptürlerine karşılık gelir:

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_WM_NCACTIVATE ()|afx_msg BOOL [Onncacer](../../mfc/reference/cwnd-class.md#onncactivate)(bool);|
|ON_WM_NCCALCSIZE ()|afx_msg void [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)(BOOL, NCCALCSIZE_PARAMS far *);|
|ON_WM_NCCREATE ()|afx_msg BOOL [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)(lpcreatestruct);|
|ON_WM_NCDESTROY ()|afx_msg void [OnNcDestroy](../../mfc/reference/cwnd-class.md#onncdestroy)();|
|ON_WM_NCHITTEST ()|afx_msg LRESULT [OnNcHitTest](../../mfc/reference/cwnd-class.md#onnchittest)(CPoint);|
|ON_WM_NCLBUTTONDBLCLK ()|void afx_msg [Onnclbuttondblclk](../../mfc/reference/cwnd-class.md#onnclbuttondblclk)(UINT, CPoint);|
|ON_WM_NCLBUTTONDOWN ()|afx_msg void [Onnclbuttonazaltma](../../mfc/reference/cwnd-class.md#onnclbuttondown)(UINT, CPoint);|
|ON_WM_NCLBUTTONUP ()|afx_msg void [Onnclbuttonup](../../mfc/reference/cwnd-class.md#onnclbuttonup)(UINT, CPoint);|
|ON_WM_NCMBUTTONDBLCLK ()|afx_msg void [Onncmbuttondblclk](../../mfc/reference/cwnd-class.md#onncmbuttondblclk)(UINT, CPoint);|
|ON_WM_NCMBUTTONDOWN ()|afx_msg void [Onncmbuttonazaltma](../../mfc/reference/cwnd-class.md#onncmbuttondown)(UINT, CPoint);|
|ON_WM_NCMBUTTONUP ()|afx_msg void [Onncmbuttonup](../../mfc/reference/cwnd-class.md#onncmbuttonup)(UINT, CPoint);|
|ON_WM_NCMOUSEHOVER ()|afx_msg void [Onncmousevurgulu](../../mfc/reference/cwnd-class.md#onncmousehover)(UINT, CPoint);|
|ON_WM_NCMOUSELEAVE ()|afx_msg void [OnNcMouseLeave](../../mfc/reference/cwnd-class.md#onncmouseleave)();|
|ON_WM_NCMOUSEMOVE ()|afx_msg void [Onncmousemove](../../mfc/reference/cwnd-class.md#onncmousemove)(UINT, CPoint);|
|ON_WM_NCPAINT ()|afx_msg void [OnNcPaint](../../mfc/reference/cwnd-class.md#onncpaint)();|
|ON_WM_NCRBUTTONDBLCLK ()|afx_msg void [Onncrbuttondblclk](../../mfc/reference/cwnd-class.md#onncrbuttondblclk)(UINT, CPoint);|
|ON_WM_NCRBUTTONDOWN ()|afx_msg void [Onncrbuttonazaltma](../../mfc/reference/cwnd-class.md#onncrbuttondown)(UINT, CPoint);|
|ON_WM_NCRBUTTONUP ()|afx_msg void [Onncrbuttonup](../../mfc/reference/cwnd-class.md#onncrbuttonup)(UINT, CPoint);|
|ON_WM_NCXBUTTONDBLCLK ()|void [Onncxbuttondblclk](../../mfc/reference/cwnd-class.md#onncxbuttondblclk)(Short, UINT, CPoint);|
|ON_WM_NCXBUTTONDOWN ()|afx_msg void [Onncxbuttonazaltma](../../mfc/reference/cwnd-class.md#onncxbuttondown)(Short, UINT, CPoint);|
|ON_WM_NCXBUTTONUP ()|afx_msg void [Onncxbuttonup](../../mfc/reference/cwnd-class.md#onncxbuttonup)(Short, UINT, CPoint);|
|ON_WM_NEXTMENU ()|afx_msg void [Onnextmenu](../../mfc/reference/cwnd-class.md#onnextmenu)(UINT, LPMDıNEXTMENU);|
|ON_WM_NOTIFYFORMAT ()|afx_msg UINT [Onnotifyformat](../../mfc/reference/cwnd-class.md#onnotifyformat)(CWnd *, UINT);|

## <a name="see-also"></a>Ayrıca bkz.

[İleti haritaları](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ Iletileri için işleyiciler](../../mfc/reference/handlers-for-wm-messages.md)
