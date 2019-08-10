---
title: Bir Zengin Düzenleme Denetiminden Bildirim
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: bc4c027ff26df89539b22c6d04f1d1dc95fc459a
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916394"
---
# <a name="notifications-from-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetiminden Bildirim

Bildirim iletileri bir zengin düzenleme denetimini ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) etkileyen olayları bildirir. Bunlar, üst pencere veya ileti yansıtma kullanılarak, zengin düzenleme denetiminin kendisi tarafından işlenebilir. Zengin düzenleme denetimleri, düzenleme denetimleriyle birlikte kullanılan tüm bildirim iletilerini ve çeşitli ek olanları destekler. "Olay maskesini" ayarlayarak, bir zengin düzenleme denetiminin üst penceresini göndereceğini belirten bildirim iletilerini belirleyebilirsiniz.

Bir zengin düzenleme denetimine yönelik olay maskesini ayarlamak için [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) üye işlevini kullanın. Bir zengin düzenleme denetimi için geçerli olay maskesini [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) üye işlevini kullanarak alabilirsiniz.

Aşağıdaki paragraflarda bazı özel bildirimler ve kullanımları listelenmektedir:

- EN_MSGFILTER bildirimini Işleme EN_MSGFILTER, zengin düzenleme denetimi veya üst penceresi olan bir sınıfın tüm klavye ve fare girişini denetime göre filtrelemesine olanak tanır. İşleyici, klavye veya fare iletisinin işlenmesini önleyebilir veya belirtilen [Msgfilter](/windows/desktop/api/richedit/ns-richedit-msgfilter) yapısını değiştirerek iletiyi değiştirebilir.

- EN_PROTECTED, kullanıcının korunan metni değiştirme girişiminde bulunduğu zaman algılamak için EN_PROTECTED bildirim iletisini Işleyin. Bir metin aralığını korumalı olarak işaretlemek için korumalı karakter efektini ayarlayabilirsiniz. Daha fazla bilgi için bkz. [zengin düzenleme denetimlerinde karakter biçimlendirme](../mfc/character-formatting-in-rich-edit-controls.md).

- EN_DROPFILES EN_DROPFILES bildirim iletisini işleyerek kullanıcının bir zengin düzenleme denetimine dosya bırakması için izin verebilirsiniz. Belirtilen [Endropfiles](/windows/desktop/api/richedit/ns-richedit-endropfiles) yapısı bırakılmakta olan dosyalarla ilgili bilgiler içerir.

- EN_SELCHANGE bir uygulama, EN_SELCHANGE bildirim iletisini işleyerek geçerli seçimin ne zaman değiştiğini algılayabilir. Bildirim iletisi, yeni seçim hakkında bilgi içeren bir [SelChange](/windows/desktop/api/richedit/ns-richedit-selchange) yapısını belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
