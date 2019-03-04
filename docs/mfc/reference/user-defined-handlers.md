---
title: Kullanıcı Tanımlı İşleyiciler
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.handlers
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
ms.openlocfilehash: d7c735531e4e2bd4da37ef7ba89cc9c4f9222b47
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262018"
---
# <a name="user-defined-handlers"></a>Kullanıcı Tanımlı İşleyiciler

Aşağıdaki eşleme girişleri için işlev prototipleri karşılık gelir.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_MESSAGE ( \<ileti >, \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM, LPARAM);|
|On_regıstered_message ( \<nMessageVariable >, \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM, LPARAM);|
|ON_THREAD_MESSAGE ( \<ileti >, \<memberFxn >)|afx_msg void memberFxn (WPARAM, LPARAM);|
|On_regıstered_thread_message ( \<nMessageVariable >, \<memberFxn >)|afx_msg void memberFxn (WPARAM, LPARAM);|

## <a name="see-also"></a>Ayrıca bkz.

[İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ İletileri için İşleyiciler](../../mfc/reference/handlers-for-wm-messages.md)
