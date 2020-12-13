---
description: 'Daha fazla bilgi edinin: zengin düzenleme denetimlerinde karakter biçimlendirme'
title: Zengin Düzenleme Denetimlerinde Karakter Biçimlendirme
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: 47d44a7d586d52ba6a83314711af1350d1c2def6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339702"
---
# <a name="character-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Karakter Biçimlendirme

Zengin düzenleme denetiminin ([CRichEditCtrl](reference/cricheditctrl-class.md)) üye işlevlerini karakterleri biçimlendirmek ve biçimlendirme bilgilerini almak için kullanabilirsiniz. Karakterler için yazı tipi, boyut, renk ve kalın, italik ve korumalı gibi etkileri belirtebilirsiniz.

[SetSelectionCharFormat](reference/cricheditctrl-class.md#setselectioncharformat) ve [SetWordCharFormat](reference/cricheditctrl-class.md#setwordcharformat) üye işlevlerini kullanarak karakter biçimlendirmesi uygulayabilirsiniz. Seçili metin için geçerli karakter biçimlendirmesini öğrenmek için [GetSelectionCharFormat](reference/cricheditctrl-class.md#getselectioncharformat) üye işlevini kullanın. [Charformat](/windows/win32/api/richedit/ns-richedit-charformata) yapısı, bu üye işlevlerle karakter özniteliklerini belirtmek için kullanılır. **Charformat** 'ın önemli üyelerinden biri **dwMask**. `SetSelectionCharFormat`Ve `SetWordCharFormat` ' de **dwMask** , bu işlev çağrısı tarafından ayarlanacak karakter özniteliklerinin belirtir. `GetSelectionCharFormat` seçimdeki ilk karakterin özniteliklerini raporlar; **dwMask** seçim boyunca tutarlı olan öznitelikleri belirtir.

Ayrıca, daha sonraki ekli karakterlere uygulanan biçimlendirme olan "varsayılan karakter biçimlendirmesini" alabilir ve ayarlayabilirsiniz. Örneğin, bir uygulama varsayılan karakter biçimlendirmesini kalın olarak ayarlarsa ve Kullanıcı bir karakter yazdığında, bu karakter kalın olur. Varsayılan karakter biçimlendirmesini almak ve ayarlamak için [GetDefaultCharFormat](reference/cricheditctrl-class.md#getdefaultcharformat) ve [SetDefaultCharFormat](reference/cricheditctrl-class.md#setdefaultcharformat) üye işlevlerini kullanın.

"Protected" karakter özniteliği metnin görünümünü değiştirmez. Kullanıcı korumalı metni değiştirmeye çalışırsa, bir zengin düzenleme denetimi üst penceresine bir **EN_PROTECTED** bildirim iletisi gönderir ve üst pencerenin değişikliğe izin vermesini veya engel olmasını sağlar. Bu bildirim iletisini almak için [SetEventMask](reference/cricheditctrl-class.md#seteventmask) üye işlevini kullanarak etkinleştirmeniz gerekir. Olay maskesi hakkında daha fazla bilgi için bu konunun ilerleyen kısımlarında [bir zengin düzenleme denetiminden gelen bildirimler](notifications-from-a-rich-edit-control.md)bölümüne bakın.

Ön plan rengi bir karakter özniteliğidir, ancak arka plan rengi zengin düzenleme denetiminin bir özelliğidir. Arka plan rengini ayarlamak için [SetBackgroundColor](reference/cricheditctrl-class.md#setbackgroundcolor) üye işlevini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](using-cricheditctrl.md)<br/>
[Denetimler](controls-mfc.md)
