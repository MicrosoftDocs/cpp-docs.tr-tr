---
title: Zengin Düzenleme Denetimlerinde Pano İşlemleri
ms.date: 11/04/2016
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
ms.openlocfilehash: 882c589d0d25b54650affa7fd41f916ecf6097d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327112"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Pano İşlemleri

Uygulamanızı Pano içeriğini bir zengin düzenleme denetimine yapıştırabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) en iyi kullanılabilir Pano biçimi veya belirli bir pano biçimi kullanarak. Ayrıca, bir zengin düzenleme denetimine bir pano biçimi yapıştırarak özelliğine sahip olup olmadığını belirleyebilirsiniz.

Kopyalayın veya içeriği geçerli seçimi kullanarak Kes [kopyalama](../mfc/reference/cricheditctrl-class.md#copy) veya [Kes](../mfc/reference/cricheditctrl-class.md#cut) üye işlevi. Bir zengin düzenleme denetimine kullanarak Pano içeriğini benzer şekilde, yapıştırabilirsiniz [yapıştırın](../mfc/reference/cricheditctrl-class.md#paste) üye işlevi. Denetim, büyük olasılıkla en açıklayıcı bir biçim olduğu tanıdığı, ilk kullanılabilir biçimi yapıştırır.

Belirli bir pano biçimi yapıştırmak için kullanabileceğiniz [denetlemeye](../mfc/reference/cricheditctrl-class.md#pastespecial) üye işlevi. Bu işlev, Pano biçimi seçmesini sağlayan bir Özel Yapıştır komut olan uygulamalar için yararlıdır. Kullanabileceğiniz [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) verilen biçimini denetim tarafından tanınan olup olmadığını belirlemek için üye işlevi.

Ayrıca `CanPaste` kullanılabilir tüm Pano biçimlerini bir zengin düzenleme denetimi tarafından tanınan olup olmadığını belirlemek için. Bu işlev yararlıdır `OnInitMenuPopup` işleyici. Bir uygulama etkinleştirin veya gri denetim kullanılabilir herhangi bir biçimde olup olmadığını yapıştırabilirsiniz bağlı olarak kendi Paste komutu.

Zengin düzenleme denetimleri Kaydet iki Pano biçimleri: zengin metin biçimi ve RichEdit metin ve nesneleri adlı biçimi. Bir uygulamayı kullanarak bu biçimler kaydedebilirsiniz [RegisterClipboardFormat](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata) belirterek işlev **CF_RTF** ve **CF_RETEXTOBJ** değerleri.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
