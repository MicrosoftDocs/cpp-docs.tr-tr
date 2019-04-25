---
title: Bir Zengin Düzenleme Denetimindeki Geçerli Bölüm
ms.date: 11/04/2016
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
ms.openlocfilehash: 4516c4506419169ac3ab284e6c59cae71595be59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241812"
---
# <a name="current-selection-in-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetimindeki Geçerli Bölüm

Kullanıcı bir zengin düzenleme denetiminde metin seçebilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) klavye veya fare kullanarak. Geçerli seçimi seçili karakter aralığı veya herhangi bir karakter, ekleme noktasını konumunu seçilir. Uygulamanın geçerli seçimi hakkında bilgi edinin, geçerli seçimi ayarla, ne zaman geçerli seçimi değişiklikleri ve Göster veya gizle seçimi vurgulayın belirleyin.

Bir zengin düzenleme denetimindeki geçerli bölüm belirlemek için [GetSel](../mfc/reference/cricheditctrl-class.md#getsel) üye işlevi. Geçerli seçimi ayarlamak için kullanın [SetSel](../mfc/reference/cricheditctrl-class.md#setsel) üye işlevi. [CHARRANGE](/windows/desktop/api/richedit/ns-richedit-_charrange) yapısına sahip bu işlevlerin da karakter aralığını belirtmek için kullanılır. Geçerli seçimin içeriğine hakkında bilgi almak için kullanabileceğiniz [GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype) üye işlevi.

Varsayılan olarak, bir zengin düzenleme denetimi gösterir ve seçim Vurgusu kazanır ve odağı kaybettiğinde gizler. Göstermek veya seçim Vurgusu kullanarak herhangi bir zamanda Gizle [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) üye işlevi. Örneğin, bir uygulama bir zengin düzenleme denetiminde metni bulmak için arama iletişim kutusu sağlayabilirsiniz. Uygulama iletişim kutusunu kapatmadan eşleşen metin seçebilirsiniz, bu durumda kullanmanız gerekir `HideSelection` seçimi vurgulayın.

Seçili metnin bir zengin düzenleme denetimini almak için kullanın [GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext) üye işlevi. Metnin belirtilen karakter dizisine kopyalanır. Dizisinin seçili metni artı bir sonlandırıcı null karakteri alacak kadar büyük olduğundan emin olmanız gerekir.

Bir zengin düzenleme denetimindeki bir dize kullanarak arayabilirsiniz [FindText](../mfc/reference/cricheditctrl-class.md#findtext) üye işlevi [FINDTEXTEX](/windows/desktop/api/richedit/ns-richedit-_findtextexa) bu işlevle kullanılan yapısı metin aralığı arama yapma ve aranacak dizeyi belirtir. Bu seçenekler ayrıca arama büyük/küçük harfe olup olarak da belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
