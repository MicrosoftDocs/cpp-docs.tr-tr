---
title: Bir Zengin Düzenleme Denetimindeki Geçerli Bölüm
ms.date: 11/04/2016
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
ms.openlocfilehash: 43a68d63f7888d762eee031196453eb156ecf105
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508766"
---
# <a name="current-selection-in-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetimindeki Geçerli Bölüm

Kullanıcı, fareyi veya klavyeyi kullanarak bir zengin düzenleme denetimindeki ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) metin seçebilir. Geçerli seçim, seçilen karakterlerin aralığıdır veya hiçbir karakter seçilmezse ekleme noktasının konumudur. Bir uygulama geçerli seçim hakkında bilgi alabilir, geçerli seçimi ayarlayabilir, geçerli seçimin ne zaman değişeni belirleyebilir ve seçim vurgulamasını gösterebilir veya gizleyebilirler.

Bir zengin düzenleme denetimindeki geçerli seçimi öğrenmek için [GetSel](../mfc/reference/cricheditctrl-class.md#getsel) member işlevini kullanın. Geçerli seçimi ayarlamak için [SetSel](../mfc/reference/cricheditctrl-class.md#setsel) üye işlevini kullanın. [Charrange](/windows/win32/api/richedit/ns-richedit-charrange) yapısı, Bu işlevlerle birlikte bir karakter aralığı belirtmek için kullanılır. Geçerli seçimin içeriği hakkında bilgi almak için [GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype) üye işlevini kullanabilirsiniz.

Varsayılan olarak, zengin bir düzenleme denetimi, odak kazanırsa ve kaybettiğinde seçim vurgulamasını gösterir ve gizler. Seçim vurgulamasını dilediğiniz zaman [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) üye işlevini kullanarak gösterebilir veya gizleyebilirsiniz. Örneğin, bir uygulama bir zengin düzenleme denetiminde metin bulmak için bir arama iletişim kutusu sağlayabilir. Uygulama, iletişim kutusunu kapatmadan eşleşen metin seçebilir ve bu durumda seçimi vurgulamak için kullanılması `HideSelection` gerekir.

Seçili metni bir zengin düzenleme denetiminde almak için [GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext) üye işlevini kullanın. Metin, belirtilen karakter dizisine kopyalanır. Dizinin seçili metni tutabilecek kadar büyük ve bir Sonlandırıcı null karakteri içerdiğinden emin olmanız gerekir.

[FindText](../mfc/reference/cricheditctrl-class.md#findtext) üye işlevini kullanarak bir dizeyi zengin düzenleme denetiminde arayabilirsiniz. bu Işlevle kullanılan [findtextex](/windows/win32/api/richedit/ns-richedit-findtextexw) yapısı, arama yapılacak metin aralığını ve aranacak dizeyi belirtir. Ayrıca, aramanın büyük/küçük harfe duyarlı olup olmadığı için bu seçenekleri de belirtebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
