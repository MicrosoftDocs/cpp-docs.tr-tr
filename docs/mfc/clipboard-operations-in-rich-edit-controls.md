---
description: 'Daha fazla bilgi edinin: zengin düzenleme denetimlerinde Pano Işlemleri'
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
ms.openlocfilehash: 9a9fda9aebe3a749359776c1bc0d41e75deaef76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251212"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Pano İşlemleri

Uygulamanız Pano içeriğini bir zengin düzenleme denetimine ([CRichEditCtrl](reference/cricheditctrl-class.md)) En Iyi kullanılabilir Pano biçimini veya belirli bir Pano biçimini kullanarak yapıştırabilir. Ayrıca, bir zengin düzenleme denetiminin Pano biçimini yapıştırabilme yeteneğine sahip olup olmadığını belirleyebilirsiniz.

[Kopyala](reference/cricheditctrl-class.md#copy) veya [Kes](reference/cricheditctrl-class.md#cut) üye işlevini kullanarak geçerli seçimin içeriğini kopyalayabilir veya kesebilir. Benzer şekilde, [Yapıştırma](reference/cricheditctrl-class.md#paste) üye Işlevini kullanarak panonun içeriğini bir zengin düzenleme denetimine yapıştırabilirsiniz. Denetim, tanıdığı ilk kullanılabilir biçimi yapıştırır, bu, en açıklayıcı biçim olarak kabul edilir.

Belirli bir Pano biçimini yapıştırmak için [PasteSpecial](reference/cricheditctrl-class.md#pastespecial) member işlevini kullanabilirsiniz. Bu işlev, kullanıcının Pano biçimini seçmesini sağlayan özel bir Yapıştır komutu olan uygulamalar için faydalıdır. Belirli bir biçimin denetim tarafından tanınıp tanınmadığını anlamak için [CanPaste](reference/cricheditctrl-class.md#canpaste) üye işlevini kullanabilirsiniz.

`CanPaste`Kullanılabilir herhangi bir pano biçiminin zengin düzenleme denetimi tarafından tanınıp tanınmadığını öğrenmek için de kullanabilirsiniz. Bu işlev, `OnInitMenuPopup` işleyicide yararlıdır. Bir uygulama, denetimin kullanılabilir herhangi bir biçimi yapıştırmasına bağlı olarak yapıştırma komutunu etkinleştirebilir veya gri renkte açabilir.

Zengin düzenleme denetimleri iki Pano biçimini kaydeder: zengin metin biçimi ve RichEdit Metin ve nesneler adlı bir biçim. Bir uygulama, **CF_RTF** ve **CF_RETEXTOBJ** değerlerini belirterek [RegisterClipboardFormat](/windows/win32/api/winuser/nf-winuser-registerclipboardformatw) işlevini kullanarak bu biçimleri kaydedebilir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](using-cricheditctrl.md)<br/>
[Denetimler](controls-mfc.md)
