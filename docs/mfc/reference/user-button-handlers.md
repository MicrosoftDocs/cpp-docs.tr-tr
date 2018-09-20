---
title: Kullanıcı düğmesi işleyicileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_BN_HILITE
- ON_BN_DOUBLECLICKED
- ON_BN_CLICKED
- ON_BN_PAINT
- ON_BN_DISABLE
- ON_BN_UNHILITE
dev_langs:
- C++
helpviewer_keywords:
- ON_BN_PAINT
- user buttons [MFC]
- ON_BN_DOUBLECLICKED [MFC]
- ON_BN_DISABLE [MFC]
- ON_BN_UNHILITE [MFC]
- ON_BN_HILITE [MFC]
- ON_BN_CLICKED [MFC]
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5b7a93afaee003f093e479cbdf9c9e14731cef7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447322"
---
# <a name="user-button-handlers"></a>Kullanıcı Düğmesi İşleyicileri

Aşağıdaki eşleme girişleri için işlev prototipleri karşılık gelir.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_BN_CLICKED ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_BN_DISABLE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_BN_DOUBLECLICKED ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_BN_HILITE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_BN_PAINT ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|
|ON_BN_UNHILITE ( \<kimliği >, \<memberFxn >)|afx_msg void memberFxn ();|

## <a name="see-also"></a>Ayrıca Bkz.

[İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)

