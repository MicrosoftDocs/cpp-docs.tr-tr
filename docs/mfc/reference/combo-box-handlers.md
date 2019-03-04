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
ms.openlocfilehash: ed83bcf565ec420d159c73ddfd82827aac88693f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259444"
---
# <a name="combo-box-handlers"></a>Birleşik Giriş Kutusu İşleyicileri

Aşağıdaki eşleme girişleri için işlev prototipleri karşılık gelir.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_CBN_CLOSEUP ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn (.)|
|ON_CBN_DBLCLK( \<id>, \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_DROPDOWN( \<id>, \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_EDITCHANGE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_EDITUPDATE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_ERRSPACE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_CBN_KILLFOCUS( \<id>, \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_SELCHANGE( \<id>, \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_SELENDCANCEL( \<id>, \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_SELENDOK( \<id>, \<memberFxn> )|afx_msg void memberFxn ();|
|ON_CBN_SETFOCUS( \<id>, \<memberFxn> )|afx_msg void memberFxn ();|

## <a name="see-also"></a>Ayrıca bkz.

[İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)
