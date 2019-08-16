---
title: Bir Zengin Düzenleme Denetiminden Bildirim
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: d097996e61a3d461dacd3d30e13b9262c7d32434
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508044"
---
# <a name="notifications-from-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetiminden Bildirim

Bildirim iletileri bir zengin düzenleme denetimini ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) etkileyen olayları bildirir. Bunlar, üst pencere veya ileti yansıtma kullanılarak, zengin düzenleme denetiminin kendisi tarafından işlenebilir. Zengin düzenleme denetimleri, düzenleme denetimleriyle birlikte kullanılan tüm bildirim iletilerini ve çeşitli ek olanları destekler. "Olay maskesini" ayarlayarak, bir zengin düzenleme denetiminin üst penceresini göndereceğini belirten bildirim iletilerini belirleyebilirsiniz.

Bir zengin düzenleme denetimine yönelik olay maskesini ayarlamak için [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) üye işlevini kullanın. Bir zengin düzenleme denetimi için geçerli olay maskesini [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) üye işlevini kullanarak alabilirsiniz.

Aşağıdaki paragraflarda bazı özel bildirimler ve kullanımları listelenmektedir:

- EN_MSGFILTER bildirimini Işleme EN_MSGFILTER, zengin düzenleme denetimi veya üst penceresi olan bir sınıfın tüm klavye ve fare girişini denetime göre filtrelemesine olanak tanır. İşleyici, klavye veya fare iletisinin işlenmesini önleyebilir veya belirtilen [Msgfilter](/windows/win32/api/richedit/ns-richedit-msgfilter) yapısını değiştirerek iletiyi değiştirebilir.

- EN_PROTECTED, kullanıcının korunan metni değiştirme girişiminde bulunduğu zaman algılamak için EN_PROTECTED bildirim iletisini Işleyin. Bir metin aralığını korumalı olarak işaretlemek için korumalı karakter efektini ayarlayabilirsiniz. Daha fazla bilgi için bkz. [zengin düzenleme denetimlerinde karakter biçimlendirme](../mfc/character-formatting-in-rich-edit-controls.md).

- EN_DROPFILES EN_DROPFILES bildirim iletisini işleyerek kullanıcının bir zengin düzenleme denetimine dosya bırakması için izin verebilirsiniz. Belirtilen [Endropfiles](/windows/win32/api/richedit/ns-richedit-endropfiles) yapısı bırakılmakta olan dosyalarla ilgili bilgiler içerir.

- EN_SELCHANGE bir uygulama, EN_SELCHANGE bildirim iletisini işleyerek geçerli seçimin ne zaman değiştiğini algılayabilir. Bildirim iletisi, yeni seçim hakkında bilgi içeren bir [SelChange](/windows/win32/api/richedit/ns-richedit-selchange) yapısını belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
