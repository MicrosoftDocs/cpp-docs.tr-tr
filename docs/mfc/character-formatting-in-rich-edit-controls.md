---
title: Zengin Düzenleme Denetimlerinde Karakter Biçimlendirme
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: 4ac996c1cb018a29137e37d9603016dc1c151c58
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508983"
---
# <a name="character-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Karakter Biçimlendirme

Zengin düzenleme denetiminin ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) üye işlevlerini karakterleri biçimlendirmek ve biçimlendirme bilgilerini almak için kullanabilirsiniz. Karakterler için yazı tipi, boyut, renk ve kalın, italik ve korumalı gibi etkileri belirtebilirsiniz.

[SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) ve [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) üye işlevlerini kullanarak karakter biçimlendirmesi uygulayabilirsiniz. Seçili metin için geçerli karakter biçimlendirmesini öğrenmek için [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) üye işlevini kullanın. [Charformat](/windows/win32/api/richedit/ns-richedit-_charformat) yapısı, bu üye işlevlerle karakter özniteliklerini belirtmek için kullanılır. **Charformat** 'ın önemli üyelerinden biri **dwMask**. `SetSelectionCharFormat` Ve`SetWordCharFormat`' de **dwMask** , bu işlev çağrısı tarafından ayarlanacak karakter özniteliklerinin belirtir. `GetSelectionCharFormat`seçimdeki ilk karakterin özniteliklerini raporlar; **dwMask** seçim boyunca tutarlı olan öznitelikleri belirtir.

Ayrıca, daha sonraki ekli karakterlere uygulanan biçimlendirme olan "varsayılan karakter biçimlendirmesini" alabilir ve ayarlayabilirsiniz. Örneğin, bir uygulama varsayılan karakter biçimlendirmesini kalın olarak ayarlarsa ve Kullanıcı bir karakter yazdığında, bu karakter kalın olur. Varsayılan karakter biçimlendirmesini almak ve ayarlamak için [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) ve [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) üye işlevlerini kullanın.

"Protected" karakter özniteliği metnin görünümünü değiştirmez. Kullanıcı, korumalı metni değiştirmeye çalışırsa, bir zengin düzenleme denetimi üst penceresine bir **EN_PROTECTED** bildirim iletisi gönderir ve üst pencerenin değişikliğe izin vermesini veya engel olmasını sağlar. Bu bildirim iletisini almak için [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) üye işlevini kullanarak etkinleştirmeniz gerekir. Olay maskesi hakkında daha fazla bilgi için bu konunun ilerleyen kısımlarında [bir zengin düzenleme denetiminden gelen bildirimler](../mfc/notifications-from-a-rich-edit-control.md)bölümüne bakın.

Ön plan rengi bir karakter özniteliğidir, ancak arka plan rengi zengin düzenleme denetiminin bir özelliğidir. Arka plan rengini ayarlamak için [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) üye işlevini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
