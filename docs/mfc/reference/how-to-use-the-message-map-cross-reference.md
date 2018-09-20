---
title: 'Nasıl yapılır: ileti eşleme çapraz başvurusunu kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fccdf620cbdaeffc7fb201e014edc4c7c1dddc83
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434459"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Nasıl yapılır: İleti Eşleme Çapraz Başvurusunu Kullanma

Etiketli girdileri \<memberFxn >, kendi üye işlevi için türetilmiş yazma [CWnd](../../mfc/reference/cwnd-class.md) sınıfı. İşlevinizi istediğiniz herhangi bir ad verin. Gibi diğer işlevleri `OnActivate`, sınıfın üye işlevleri `CWnd`. Çağrılırsa, bunlar iletiye geçirmek `DefWindowProc` Windows işlevi. Windows bildirim iletilerini işlemek için karşılık gelen geçersiz kılma `CWnd` türetilmiş sınıfınızın bir işlevde. İşlevinizi geçersiz kılınmış işlev temel sınıf izin vermek için temel sınıfta çağırmalıdır ve Windows iletiye yanıt vermek.

Her durumda, işlev prototipi koymak `CWnd`-türetilmiş sınıf üstbilgi ve kod gösterildiği ileti eşleme girişi.

Aşağıdaki terimler kullanılır:

|Terim|Tanım|
|----------|----------------|
|kimlik|Tüm kullanıcı tanımlı bir menü öğesi kimliği (WM_COMMAND iletileri) veya denetim kimliği (alt pencere bildirim iletisi).|
|"ileti" ve "wNotifyCode"|Windows, WİNDOWS'da tanımlandığı gibi kimlikleri ileti. H|
|nMessageVariable|Dönüş değeri içeren değişkenin adını `RegisterWindowMessage` Windows işlevi.|

## <a name="see-also"></a>Ayrıca Bkz.

[İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)

