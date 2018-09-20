---
title: Birleşik giriş kutusu işleyicileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5751fbdd4bff0cf3d42231ad00bef0c3483ccfb9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424267"
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

