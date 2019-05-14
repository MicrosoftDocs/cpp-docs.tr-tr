---
title: Kullanıcı Tanımlı İşleyiciler
ms.date: 11/04/2016
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
ms.openlocfilehash: f39440d333e968c236ae5ccd750cec8854cb0530
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611542"
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
