---
description: 'Daha fazla bilgi edinin: Birleşik giriş kutusu Işleyicileri'
title: Birleşik Giriş Kutusu İşleyicileri
ms.date: 11/04/2016
f1_keywords:
- ON_CBN_KILLFOCUS
- ON_CBN_ERRSPACE
- ON_CBN_EDITCHANGE
- ON_CBN_CLOSEUP
- ON_CBN_DBLCLK
- ON_CBN_EDITUPDATE
- ON_CBN_DROPDOWN
- ON_CBN_SELENDOK
- ON_CBN_SELCHANGE
- ON_CBN_SETFOCUS
- ON_CBN_SELENDCANCEL
helpviewer_keywords:
- ON_CBN_CLOSEUP
- ON_CBN_SETFOCUS
- ON_CBN_DBLCLK
- ON_CBN_SELENDCANCEL
- ON_CBN_DROPDOWN
- ON_CBN_EDITUPDATE
- ON_CBN_KILLFOCUS
- combo boxes [MFC], handlers
- ON_CBN_EDITCHANGE
- ON_CBN_ERRSPACE
- ON_CBN_SELENDOK
- ON_CBN_SELCHANGE
ms.assetid: 7f092412-01b7-4242-95ec-41ba506b9d71
ms.openlocfilehash: 5d15e1db53d48c597ab0f47577746bfbc6790ad3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331372"
---
# <a name="combo-box-handlers"></a>Birleşik Giriş Kutusu İşleyicileri

Aşağıdaki eşleme girdileri işlev prototiptürlerine karşılık gelir.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_CBN_CLOSEUP ( \<id> , \<memberFxn> )|afx_msg void memberFxn ()|
|ON_CBN_DBLCLK ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_DROPDOWN ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_EDITCHANGE ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_EDITUPDATE ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_ERRSPACE ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_KILLFOCUS ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_SELCHANGE ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_SELENDCANCEL ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_SELENDOK ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_SETFOCUS ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|

## <a name="see-also"></a>Ayrıca bkz.

[İleti haritaları](../../mfc/reference/message-maps-mfc.md)
