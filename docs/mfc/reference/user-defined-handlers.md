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
ms.openlocfilehash: 4d2102668b7cc964e6fe3bffdcc6931a2961a737
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562259"
---
# <a name="user-defined-handlers"></a>Kullanıcı Tanımlı İşleyiciler

Aşağıdaki eşleme girişleri için işlev prototipleri karşılık gelir.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_MESSAGE ( \<ileti >, \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM, LPARAM);|
|On_regıstered_message ( \<nMessageVariable >, \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM, LPARAM);|
|ON_THREAD_MESSAGE ( \<ileti >, \<memberFxn >)|afx_msg void memberFxn (WPARAM, LPARAM);|
|On_regıstered_thread_message ( \<nMessageVariable >, \<memberFxn >)|afx_msg void memberFxn (WPARAM, LPARAM);|

## <a name="see-also"></a>Ayrıca Bkz.

[İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ İletileri için İşleyiciler](../../mfc/reference/handlers-for-wm-messages.md)

