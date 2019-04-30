---
title: Zengin Düzenleme Denetimlerinde Karakter Biçimlendirme
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: a7467f9cd6a14dc6dfc2c03b6eb35f71802454fb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344293"
---
# <a name="character-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Karakter Biçimlendirme

Zengin Düzenleme denetiminin üye işlevleri kullanabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) karakterleri biçimlendirmek ve biçimlendirme bilgileri alınamıyor. Karakterler için yazı tipini, boyutunu, rengini ve etkileri kalın, italik gibi belirtebilirsiniz ve korumalı.

Karakter kullanarak biçimlendirme uygulayabilirsiniz [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) ve [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) üye işlevleri. Seçili metin için biçimlendirme geçerli karakteri belirlemek için [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) üye işlevi. [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat) yapısı, karakter özniteliklerini belirtmek için bu üye işlevleri ile kullanılır. Önemli üyelerinden birinde **CHARFORMAT** olduğu **dwMask**. İçinde `SetSelectionCharFormat` ve `SetWordCharFormat`, **dwMask** hangi karakter nitelikleri, bu işlev çağrısına göre ayarlanacağını belirtir. `GetSelectionCharFormat` Seçimdeki ilk karakterin öznitelikleri bildirir; **dwMask** seçimi tutarlı öznitelikleri belirtir.

Ayrıca Al ve Ayarla "varsayılan karakter biçimlendirme" biçimlendirme sonradan eklenen herhangi bir karakter uygulanmış olan. Örneğin, bir uygulamanın varsayılan karakter kalın biçimlendirme ve kullanıcı sonra bir karakter yazar, kalın karakterdir. Almak ve varsayılan karakter biçimlendirme ayarlamak için kullanın [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) ve [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) üye işlevleri.

"Korumalı" karakter öznitelik metin görünümünü değiştirmez. Kullanıcı, korumalı metin değiştirme girişiminde bulunursa bir zengin düzenleme denetiminin üst pencereye gönderir. bir **EN_PROTECTED** bildirim iletisi, ana pencereyi izin vermek veya değişiklik önlemek izin verme. Bu bildirim iletisini almak için onu kullanarak etkinleştirmelisiniz [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) üye işlevi. Olay maskesini hakkında daha fazla bilgi için bkz: [bir zengin düzenleme denetiminden bildirim](../mfc/notifications-from-a-rich-edit-control.md), bu konunun devamındaki.

Ön plan rengi, bir karakter özniteliğini olmakla birlikte bir özelliktir zengin düzenleme denetiminin arka plan rengi. Arka plan rengini ayarlamak için kullanın [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) üye işlevi.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
