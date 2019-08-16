---
title: Zengin Düzenleme Denetimlerinde Yazdırma
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
ms.openlocfilehash: 671aec27584af975ce1635793ae80879e7208d4b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508008"
---
# <a name="printing-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Yazdırma

Bir yazıcı gibi belirli bir cihaz için çıkışını işlemek üzere bir zengin düzenleme denetimine ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) söyleyebilirsiniz. Ayrıca, bir zengin düzenleme denetiminin metnini biçimlendiren çıkış cihazını belirtebilirsiniz.

Belirli bir cihaz için bir zengin düzenleme denetimi içeriğinin bir kısmını biçimlendirmek için [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) member işlevini kullanabilirsiniz. Bu işlevle kullanılan [FormatRange](/windows/win32/api/richedit/ns-richedit-formatrange) yapısı, biçimlendirme için metin aralığını ve hedef cihazın cihaz BAĞLAMıNı (DC) belirtir.

Bir çıkış aygıtı için metin biçimlendirmeden sonra, [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) üye işlevini kullanarak çıktıyı cihaza gönderebilirsiniz. `FormatRange` Ve`DisplayBand`kullanarak, bir zengin düzenleme denetiminin içeriğini yazdıran bir uygulama, bant uygulayabilir. (Bant oluşturma, çıktının yazdırma amacıyla daha küçük parçalara bölümüdür.)

Bir zengin düzenleme denetiminin metnini biçimlendiren hedef cihazı belirtmek için [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) üye işlevini kullanabilirsiniz. Bu işlev, bir uygulamanın, ekranın kendisi yerine varsayılan yazıcının yazı tipi ölçümlerini kullanarak metin konumuyla, WYSıWYG (ne görmeleridir) biçimlendirme için faydalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
