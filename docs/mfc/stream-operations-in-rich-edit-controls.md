---
title: Zengin Düzenleme Denetimlerinde Akış İşlemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
ms.openlocfilehash: 04cf0b06773937bf66defccbb0e5e880c06e8d88
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306687"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Akış İşlemleri

İçine veya dışına bir zengin düzenleme denetimi ile veri aktarmayı akışları kullanabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir akış tarafından tanımlanan bir [EDITSTREAM](/windows/desktop/api/richedit/ns-richedit-_editstream) yapısı, arabellek ve uygulama tanımlı geri çağırma işlevi belirtir.

Verileri bir zengin düzenleme denetimi okumak için (diğer bir deyişle, veriler akışla) kullanan [StreamIn](../mfc/reference/cricheditctrl-class.md#streamin) üye işlevi. Denetim sürekli arabelleğe her zaman verilerin bir kısmını aktaran uygulama tanımlı geri çağırma işlevini çağırır.

Zengin içeriğini düzenleme denetimi kaydetmek için (diğer bir deyişle, çıkış veri akışını) kullanabileceğiniz [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) üye işlevi. Denetim sürekli arabelleğe yazar ve sonra uygulama tanımlı geri çağırma işlevini çağırır. Her çağrı için arabellek içeriği geri çağırma işlevini kaydeder.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
