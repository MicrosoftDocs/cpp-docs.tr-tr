---
title: Bir Zengin Düzenleme Denetiminden Bildirim
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: 87168b6e58264b4257b7adfb32207ec1dd40729e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529213"
---
# <a name="notifications-from-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetiminden Bildirim

Rapor olayları etkileyen bir zengin düzenleme denetimi bildirim iletileri ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). İleti yansıması kullanarak tarafından zengin düzenleme denetiminden kendisini veya ana pencere tarafından işlenebilir. Zengin düzenleme denetimlerinde birkaç bulunmakla yanı sıra düzenleme denetimleri ile kullanılan tüm bildirim iletileri destekler. Bildirim iletileri "olay maskesini." ayarlayarak bir zengin düzenleme denetiminin üst pencereye gönderir belirleyebilirsiniz.

Bir zengin düzenleme denetimi için olay maskeyi ayarlamak için kullanın [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) üye işlevi. Bir zengin düzenleme denetiminden kullanarak için geçerli olay maskesini alabilirsiniz [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) üye işlevi.

Aşağıdaki paragraflara birkaç belirli bildirimleri ve kullanımlarının listesi:

- EN_MSGFILTER EN_MSGFILTER bildirimi bir sınıf ya da zengin düzenleme denetimi veya tüm klavye ve fare girişi denetimi için filtre üst pencereye sağlar. İşleyici klavye veya fare iletisini işlenmekte olan engelleyebilir veya ileti belirtilen değiştirerek değiştirebilirsiniz [MSGFILTER](/windows/desktop/api/richedit/ns-richedit-_msgfilter) yapısı.

- EN_PROTECTED EN_PROTECTED bildirim iletisi, kullanıcı korumalı bir metin değiştirme girişiminde bulunduğunda algılamak için işler. Bir metin aralığını korumalı olarak işaretlemek için korumalı karakter etkisi ayarlayabilirsiniz. Daha fazla bilgi için [zengin düzenleme denetimlerinde karakter biçimlendirme](../mfc/character-formatting-in-rich-edit-controls.md).

- EN_DROPFILES EN_DROPFILES bildirim iletisi işleyerek bir zengin düzenleme denetimindeki dosyalarını bırakmaya kullanıcı etkinleştirebilirsiniz. Belirtilen [ENDROPFILES](/windows/desktop/api/richedit/ns-richedit-_endropfiles) yapısı bırakılmakta dosyalarla ilgili bilgiler içerir.

- Geçerli seçimi EN_SELCHANGE bildirim iletisi işleyerek değiştiğinde EN_SELCHANGE uygulama algılayabilir. Bildirim iletisi belirtir bir [SELCHANGE](/windows/desktop/api/richedit/ns-richedit-_selchange) yeni seçimi hakkında bilgi içeren yapıya.

## <a name="see-also"></a>Ayrıca Bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

