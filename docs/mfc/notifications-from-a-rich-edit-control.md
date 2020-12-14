---
description: 'Daha fazla bilgi edinin: bir zengin düzenleme denetiminden bildirimler'
title: Bir Zengin Düzenleme Denetiminden Bildirim
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: 83f76c2b0bf8c27d30d8c113fc1607f3cbd718fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254800"
---
# <a name="notifications-from-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetiminden Bildirim

Bildirim iletileri bir zengin düzenleme denetimini ([CRichEditCtrl](reference/cricheditctrl-class.md)) etkileyen olayları bildirir. Bunlar, üst pencere veya ileti yansıtma kullanılarak, zengin düzenleme denetiminin kendisi tarafından işlenebilir. Zengin düzenleme denetimleri, düzenleme denetimleriyle birlikte kullanılan tüm bildirim iletilerini ve çeşitli ek olanları destekler. "Olay maskesini" ayarlayarak, bir zengin düzenleme denetiminin üst penceresini göndereceğini belirten bildirim iletilerini belirleyebilirsiniz.

Bir zengin düzenleme denetimine yönelik olay maskesini ayarlamak için [SetEventMask](reference/cricheditctrl-class.md#seteventmask) üye işlevini kullanın. Bir zengin düzenleme denetimi için geçerli olay maskesini [GetEventMask](reference/cricheditctrl-class.md#geteventmask) üye işlevini kullanarak alabilirsiniz.

Aşağıdaki paragraflarda bazı özel bildirimler ve kullanımları listelenmektedir:

- EN_MSGFILTER bildirimini Işleme EN_MSGFILTER, bir sınıfın, zengin düzenleme denetimi veya üst penceresi için tüm klavye ve fare girişini denetime göre filtrelemesine olanak tanır. İşleyici, klavye veya fare iletisinin işlenmesini önleyebilir veya belirtilen [Msgfilter](/windows/win32/api/richedit/ns-richedit-msgfilter) yapısını değiştirerek iletiyi değiştirebilir.

- EN_PROTECTED, kullanıcının korunan metni değiştirmeye ne zaman EN_PROTECTED bildirim iletisini Işlemesini algılar. Bir metin aralığını korumalı olarak işaretlemek için korumalı karakter efektini ayarlayabilirsiniz. Daha fazla bilgi için bkz. [zengin düzenleme denetimlerinde karakter biçimlendirme](character-formatting-in-rich-edit-controls.md).

- EN_DROPFILES, EN_DROPFILES bildirim iletisini işleyerek kullanıcının bir zengin düzenleme denetimine dosya bırakması için izin verebilirsiniz. Belirtilen [Endropfiles](/windows/win32/api/richedit/ns-richedit-endropfiles) yapısı bırakılmakta olan dosyalarla ilgili bilgiler içerir.

- Bir uygulamanın, EN_SELCHANGE bildirim iletisini işleyerek geçerli seçimin ne zaman değiştiğini algılayabilmesi EN_SELCHANGE. Bildirim iletisi, yeni seçim hakkında bilgi içeren bir [SelChange](/windows/win32/api/richedit/ns-richedit-selchange) yapısını belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](using-cricheditctrl.md)<br/>
[Denetimler](controls-mfc.md)
