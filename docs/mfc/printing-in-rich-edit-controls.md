---
title: Zengin Düzenleme Denetimlerinde Yazdırma
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
ms.openlocfilehash: 2ddc52e43da2e409117ccc5169442002ac27a315
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263513"
---
# <a name="printing-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Yazdırma

Zengin düzenleme denetimi anlayabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) çıktısını bir yazıcı gibi belirtilen bir cihaz için oluşturulacak. Kendisi için bir zengin düzenleme denetiminden çıktı cihazına yazısının biçimler de belirtebilirsiniz.

Belirli bir cihaz için bir zengin düzenleme denetimi içeriğini bir parçası olarak biçimlendirmek için kullanabileceğiniz [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) üye işlevi. [FORMATRANGE](/windows/desktop/api/richedit/ns-richedit-_formatrange) yapısı ile bu işlev kullanılan hedef cihaz için cihaz bağlamı (DC) yanı sıra biçimlendirmek için metin aralığını belirtir.

Bir çıktı cihazına için metin biçimlendirme sonrasında, çıkış cihaza kullanarak gönderebilirsiniz [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) üye işlevi. Tekrar tekrar kullanarak `FormatRange` ve `DisplayBand`, uygulamanın bir zengin düzenleme denetiminin içeriğini yazdırır banding uygulayabilirsiniz. (Bant çıkış bölümü daha küçük parçalara yazdırma amaçları içindir.)

Kullanabileceğiniz [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) üye işlevi bir zengin düzenleme denetimi hedef cihaza belirtmek için metin biçimlendirir. Bu işlev yararlıdır için WYSIWYG (ne şunları elde edersiniz gördüğünüz) biçimlendirme, uygulama ekranının yerine varsayılan yazıcının yazı tipi ölçümleri kullanarak metin yerleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
