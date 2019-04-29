---
title: 'Nasıl yapılır: İleti eşleme çapraz başvurusunu kullanma'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.messages
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
ms.openlocfilehash: 9467dce943da8c5fb447dcd3c83d044218fa183d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322182"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Nasıl yapılır: İleti eşleme çapraz başvurusunu kullanma

Etiketli girdileri \<memberFxn >, kendi üye işlevi için türetilmiş yazma [CWnd](../../mfc/reference/cwnd-class.md) sınıfı. İşlevinizi istediğiniz herhangi bir ad verin. Gibi diğer işlevleri `OnActivate`, sınıfın üye işlevleri `CWnd`. Çağrılırsa, bunlar iletiye geçirmek `DefWindowProc` Windows işlevi. Windows bildirim iletilerini işlemek için karşılık gelen geçersiz kılma `CWnd` türetilmiş sınıfınızın bir işlevde. İşlevinizi geçersiz kılınmış işlev temel sınıf izin vermek için temel sınıfta çağırmalıdır ve Windows iletiye yanıt vermek.

Her durumda, işlev prototipi koymak `CWnd`-türetilmiş sınıf üstbilgi ve kod gösterildiği ileti eşleme girişi.

Aşağıdaki terimler kullanılır:

|Terim|Tanım|
|----------|----------------|
|kimlik|Tüm kullanıcı tanımlı bir menü öğesi kimliği (WM_COMMAND iletileri) veya denetim kimliği (alt pencere bildirim iletisi).|
|"ileti" ve "wNotifyCode"|Windows, WİNDOWS'da tanımlandığı gibi kimlikleri ileti. H|
|nMessageVariable|Dönüş değeri içeren değişkenin adını `RegisterWindowMessage` Windows işlevi.|

## <a name="see-also"></a>Ayrıca bkz.

[İleti eşlemeleri](../../mfc/reference/message-maps-mfc.md)
