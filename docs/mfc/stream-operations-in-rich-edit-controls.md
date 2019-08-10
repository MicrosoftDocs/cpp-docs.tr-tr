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
ms.openlocfilehash: 04bf49371b3ab5eaaad2775b532d8d35bf990ce3
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915287"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Akış İşlemleri

Akışları, bir zengin düzenleme denetimine ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) veri aktarmak için kullanabilirsiniz. Bir akış, bir arabelleği ve uygulama tanımlı geri çağırma işlevini belirten bir [Editstream](/windows/desktop/api/richedit/ns-richedit-editstream) yapısı tarafından tanımlanır.

Verileri bir zengin düzenleme denetimine okumak için (diğer bir deyişle, içindeki verileri akışa alın), [streamin](../mfc/reference/cricheditctrl-class.md#streamin) üye işlevini kullanın. Denetim, her seferinde verilerin bir kısmını arabelleğe aktaran uygulama tanımlı geri çağırma işlevini tekrar tekrar çağırır.

Zengin düzenleme denetiminin içeriğini kaydetmek için (yani, verileri dışarı akışı), [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) üye işlevini kullanabilirsiniz. Denetim, arabelleğe tekrar tekrar yazar ve ardından uygulama tanımlı geri çağırma işlevini çağırır. Her çağrı için, geri çağırma işlevi arabelleğin içeriğini kaydeder.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
