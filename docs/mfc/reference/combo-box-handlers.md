---
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
ms.openlocfilehash: 44fbf74174df833badd18ee29416ed936ea69293
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438135"
---
# <a name="combo-box-handlers"></a>Birleşik Giriş Kutusu İşleyicileri

Aşağıdaki eşleme girişleri için işlev prototipleri karşılık gelir.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_CBN_CLOSEUP ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn (.)|
|ON_CBN_DBLCLK ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_DROPDOWN ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_EDITCHANGE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_EDITUPDATE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_ERRSPACE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_KILLFOCUS ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_SELCHANGE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_SELENDCANCEL ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_SELENDOK ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_SETFOCUS ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|

## <a name="see-also"></a>Ayrıca Bkz.

[İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)

