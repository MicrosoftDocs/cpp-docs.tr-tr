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
ms.openlocfilehash: 73277f59dc0ad4dfe21d481d0b893903ed407ea9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512946"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Akış İşlemleri

Akışları, bir zengin düzenleme denetimine ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) veri aktarmak için kullanabilirsiniz. Bir akış, bir arabelleği ve uygulama tanımlı geri çağırma işlevini belirten bir [Editstream](/windows/win32/api/richedit/ns-richedit-editstream) yapısı tarafından tanımlanır.

Verileri bir zengin düzenleme denetimine okumak için (diğer bir deyişle, içindeki verileri akışa alın), [streamin](../mfc/reference/cricheditctrl-class.md#streamin) üye işlevini kullanın. Denetim, her seferinde verilerin bir kısmını arabelleğe aktaran uygulama tanımlı geri çağırma işlevini tekrar tekrar çağırır.

Zengin düzenleme denetiminin içeriğini kaydetmek için (yani, verileri dışarı akışı), [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) üye işlevini kullanabilirsiniz. Denetim, arabelleğe tekrar tekrar yazar ve ardından uygulama tanımlı geri çağırma işlevini çağırır. Her çağrı için, geri çağırma işlevi arabelleğin içeriğini kaydeder.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
