---
description: 'Hakkında daha fazla bilgi edinin: zengin düzenleme denetimlerinde yazdırma'
title: Zengin Düzenleme Denetimlerinde Yazdırma
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
ms.openlocfilehash: 9b5c272df36c6a4472c82cc4b0655b1d9626c2ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205739"
---
# <a name="printing-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Yazdırma

Bir yazıcı gibi belirli bir cihaz için çıkışını işlemek üzere bir zengin düzenleme denetimine ([CRichEditCtrl](reference/cricheditctrl-class.md)) söyleyebilirsiniz. Ayrıca, bir zengin düzenleme denetiminin metnini biçimlendiren çıkış cihazını belirtebilirsiniz.

Belirli bir cihaz için bir zengin düzenleme denetimi içeriğinin bir kısmını biçimlendirmek için [FormatRange](reference/cricheditctrl-class.md#formatrange) member işlevini kullanabilirsiniz. Bu işlevle kullanılan [FormatRange](/windows/win32/api/richedit/ns-richedit-formatrange) yapısı, biçimlendirme için metin aralığını ve hedef cihazın cihaz BAĞLAMıNı (DC) belirtir.

Bir çıkış aygıtı için metin biçimlendirmeden sonra, [DisplayBand](reference/cricheditctrl-class.md#displayband) üye işlevini kullanarak çıktıyı cihaza gönderebilirsiniz. `FormatRange`Ve kullanarak `DisplayBand` , bir zengin düzenleme denetiminin içeriğini yazdıran bir uygulama, bant uygulayabilir. (Bant oluşturma, çıktının yazdırma amacıyla daha küçük parçalara bölümüdür.)

Bir zengin düzenleme denetiminin metnini biçimlendiren hedef cihazı belirtmek için [SetTargetDevice](reference/cricheditctrl-class.md#settargetdevice) üye işlevini kullanabilirsiniz. Bu işlev, bir uygulamanın, ekranın kendisi yerine varsayılan yazıcının yazı tipi ölçümlerini kullanarak metin konumuyla, WYSıWYG (ne görmeleridir) biçimlendirme için faydalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](using-cricheditctrl.md)<br/>
[Denetimler](controls-mfc.md)
