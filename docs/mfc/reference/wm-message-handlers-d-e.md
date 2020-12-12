---
description: 'Hakkında daha fazla bilgi: WM_ Ileti Işleyicileri: D-E'
title: 'WM_ İleti İşleyicileri: D - E'
ms.date: 11/04/2016
f1_keywords:
- ON_WM_ERASEBKGND
- ON_WM_DEVICECHANGE
- ON_WM_ENTERIDLE
- ON_WM_DESTROYCLIPBOARD
- ON_WM_DESTROY
- ON_WM_DEADCHAR
- ON_WM_DELETEITEM
- ON_WM_DROPFILES
- ON_WM_DEVMODECHANGE
- ON_WM_ENDSESSION
- ON_WM_ENABLE
- ON_WM_DRAWITEM
- ON_WM_DRAWCLIPBOARD
helpviewer_keywords:
- ON_WM_ENTERIDLE [MFC]
- ON_WM_DESTROYCLIPBOARD [MFC]
- ON_WM_DEADCHAR [MFC]
- ON_WM_DEVMODECHANGE [MFC]
- ON_WM_ERASEBKGND [MFC]
- ON_WM_DESTROY [MFC]
- ON_WM_DRAWCLIPBOARD [MFC]
- ON_WM_ENDSESSION [MFC]
- ON_WM_DRAWITEM [MFC]
- ON_WM_ENABLE [MFC]
- ON_WM_DROPFILES [MFC]
- ON_WM_DELETEITEM [MFC]
- ON_WM_DEVICECHANGE [MFC]
- WM_ messages [MFC]
ms.assetid: 56fb89c8-68a8-4adf-883e-a9f63bf677e9
ms.openlocfilehash: fc9de81127e008eb69a57b39bd66907214b48f89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218491"
---
# <a name="wm_-message-handlers-d---e"></a>WM_ İleti İşleyicileri: D - E

Sol taraftaki aşağıdaki harita girdileri sağdaki işlev prototiptürlerine karşılık gelir:

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_WM_DEADCHAR ()|afx_msg void [OnDeadChar](../../mfc/reference/cwnd-class.md#ondeadchar)(UINT, UINT, uint);|
|ON_WM_DELETEITEM ()|afx_msg void [OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)(Int, LPDELETEıTEMSTRUCT);|
|ON_WM_DESTROY ()|afx_msg void [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)();|
|ON_WM_DESTROYCLIPBOARD ()|afx_msg void [Ondestroyıclipboard](../../mfc/reference/cwnd-class.md#ondestroyclipboard)();|
|ON_WM_DEVICECHANGE ()|afx_msg void [Ondevicechange](../../mfc/reference/cwnd-class.md#ondevicechange)(UINT, DWORD);|
|ON_WM_DEVMODECHANGE ()|afx_msg void [Ondevmodechange](../../mfc/reference/cwnd-class.md#ondevmodechange)(LPSTR);|
|ON_WM_DRAWCLIPBOARD ()|afx_msg void [OnDrawClipboard](../../mfc/reference/cwnd-class.md#ondrawclipboard)();|
|ON_WM_DRAWITEM ()|afx_msg void [OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)(lpdrawitemstruct);|
|ON_WM_DROPFILES ()|afx_msg void [Ondropfiles](../../mfc/reference/cwnd-class.md#ondropfiles)(HDROP);|
|ON_WM_DWMCOLORIZATIONCOLORCHANGED ()|afx_msg void [Oncolorizationcolorchanged](../../mfc/reference/cwnd-class.md#oncolorizationcolorchanged)(DWORD, bool);|
|ON_WM_DWMCOMPOSITIONCHANGED ()|afx_msg void [Onkompozisyontionchanged](../../mfc/reference/cwnd-class.md#oncompositionchanged)();|
|ON_WM_DWMNCRENDERINGCHANGED ()|afx_msg void [Onncrenderingchanged](../../mfc/reference/cwnd-class.md#onncrenderingchanged)(bool);|
|ON_WM_DWMWINDOWMAXIMIZEDCHANGE ()|afx_msg void [Onwindowmaximizedchanged](../../mfc/reference/cwnd-class.md#onwindowmaximizedchanged)(bool);|
|ON_WM_ENABLE ()|afx_msg void [OnEnable](../../mfc/reference/cwnd-class.md#onenable)(bool);|
|ON_WM_ENDSESSION ()|afx_msg void [OnEndSession](../../mfc/reference/cwnd-class.md#onendsession)(bool);|
|ON_WM_ENTERIDLE ()|afx_msg void [Onenterıdle](../../mfc/reference/cwnd-class.md#onenteridle)(UINT, CWnd *);|
|ON_WM_ENTERSIZEMOVE ()|afx_msg void [Onentersizemove](../../mfc/reference/cwnd-class.md#onentersizemove)();|
|ON_WM_ERASEBKGND ()|afx_msg BOOL [Onsilinebilir Sebkplan](../../mfc/reference/cwnd-class.md#onerasebkgnd)(CDC *);|
|ON_WM_EXITSIZEMOVE ()|afx_msg void [Onexitsizemove](../../mfc/reference/cwnd-class.md#onexitsizemove)();|

## <a name="see-also"></a>Ayrıca bkz.

[İleti haritaları](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ Iletileri için işleyiciler](../../mfc/reference/handlers-for-wm-messages.md)
