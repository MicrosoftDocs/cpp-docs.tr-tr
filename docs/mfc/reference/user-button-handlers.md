---
description: 'Daha fazla bilgi edinin: Kullanıcı düğmesi Işleyicileri'
title: Kullanıcı Düğmesi İşleyicileri
ms.date: 11/04/2016
f1_keywords:
- ON_BN_HILITE
- ON_BN_DOUBLECLICKED
- ON_BN_CLICKED
- ON_BN_PAINT
- ON_BN_DISABLE
- ON_BN_UNHILITE
helpviewer_keywords:
- ON_BN_PAINT
- user buttons [MFC]
- ON_BN_DOUBLECLICKED [MFC]
- ON_BN_DISABLE [MFC]
- ON_BN_UNHILITE [MFC]
- ON_BN_HILITE [MFC]
- ON_BN_CLICKED [MFC]
ms.assetid: 410ea968-478f-4806-b7b8-5d7c8dc2bf42
ms.openlocfilehash: 944ded857062979e4de4141275a1a80564f8df9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218595"
---
# <a name="user-button-handlers"></a>Kullanıcı Düğmesi İşleyicileri

Aşağıdaki eşleme girdileri işlev prototiptürlerine karşılık gelir.

|Eşleme girişi|İşlev prototipi|
|---------------|------------------------|
|ON_BN_CLICKED ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_BN_DISABLE ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_BN_DOUBLECLICKED ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_BN_HILITE ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_BN_PAINT ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|
|ON_BN_UNHILITE ( \<id> , \<memberFxn> )|afx_msg void memberFxn ();|

## <a name="see-also"></a>Ayrıca bkz.

[İleti haritaları](../../mfc/reference/message-maps-mfc.md)
