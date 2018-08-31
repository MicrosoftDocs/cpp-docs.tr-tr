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
ms.openlocfilehash: 882ed020b37ec60c072c8983c61bbe564bb74b04
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217694"
---
# <a name="printing-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Yazdırma
Zengin düzenleme denetimi anlayabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) çıktısını bir yazıcı gibi belirtilen bir cihaz için oluşturulacak. Kendisi için bir zengin düzenleme denetiminden çıktı cihazına yazısının biçimler de belirtebilirsiniz.  
  
 Belirli bir cihaz için bir zengin düzenleme denetimi içeriğini bir parçası olarak biçimlendirmek için kullanabileceğiniz [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) üye işlevi. [FORMATRANGE](/windows/desktop/api/richedit/ns-richedit-_formatrange) yapısı ile bu işlev kullanılan hedef cihaz için cihaz bağlamı (DC) yanı sıra biçimlendirmek için metin aralığını belirtir.  
  
 Bir çıktı cihazına için metin biçimlendirme sonrasında, çıkış cihaza kullanarak gönderebilirsiniz [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) üye işlevi. Tekrar tekrar kullanarak `FormatRange` ve `DisplayBand`, uygulamanın bir zengin düzenleme denetiminin içeriğini yazdırır banding uygulayabilirsiniz. (Bant çıkış bölümü daha küçük parçalara yazdırma amaçları içindir.)  
  
 Kullanabileceğiniz [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) üye işlevi bir zengin düzenleme denetimi hedef cihaza belirtmek için metin biçimlendirir. Bu işlev yararlıdır için WYSIWYG (ne şunları elde edersiniz gördüğünüz) biçimlendirme, uygulama ekranının yerine varsayılan yazıcının yazı tipi ölçümleri kullanarak metin yerleştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

