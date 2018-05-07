---
title: Zengin düzenleme denetimlerinde yazdırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23b958e6c770260082af069544480102f6d79926
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="printing-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Yazdırma
Bir zengin düzenleme denetimi anlayabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) çıktısını yazıcısı gibi belirtilen bir aygıt için oluşturulacak. Kendisi için bir zengin düzenleme denetiminden çıkış aygıtı kendi metin biçimleri de belirtebilirsiniz.  
  
 Belirli bir aygıt için bir zengin düzenleme denetimi içeriğini parçası biçimlendirmek için kullanabileceğiniz [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) üye işlevi. [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) bu işlev ile kullanılan yapısı hedef cihaz için cihaz bağlamı (DC) yanı sıra biçimlendirmek için metin aralığını belirtir.  
  
 Bir çıkış aygıtı için metin biçimlendirme sonrasında, çıktı cihaza kullanarak gönderebilirsiniz [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) üye işlevi. Art arda kullanarak `FormatRange` ve `DisplayBand`, bir zengin düzenleme denetimine içeriğini yazdırır uygulamanın bant uygulayabilirsiniz. (Bant çıkış bölme daha küçük parçalara yazdırma amacıyla kullanılır.)  
  
 Kullanabileceğiniz [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) üye işlevi bir zengin düzenleme denetimi hedef aygıt belirtmek için metin biçimlendirir. Bu işlev için WYSIWYG yararlı (olduğu ne alacaksınız gördüğünüz) biçimlendirme, uygulama ekran yerine varsayılan yazıcının yazı tipi ölçümleri kullanarak metin yerleştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

