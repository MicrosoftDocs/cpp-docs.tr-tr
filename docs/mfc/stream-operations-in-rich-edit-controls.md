---
description: 'Daha fazla bilgi edinin: zengin düzenleme denetimlerinde akış Işlemleri'
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
ms.openlocfilehash: 3f9dcfb837d9a4f26454a597507712293d3d895c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216489"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Akış İşlemleri

Akışları, bir zengin düzenleme denetimine ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) veri aktarmak için kullanabilirsiniz. Bir akış, bir arabelleği ve uygulama tanımlı geri çağırma işlevini belirten bir [Editstream](/windows/win32/api/richedit/ns-richedit-editstream) yapısı tarafından tanımlanır.

Verileri bir zengin düzenleme denetimine okumak için (diğer bir deyişle, içindeki verileri akışa alın), [streamin](../mfc/reference/cricheditctrl-class.md#streamin) üye işlevini kullanın. Denetim, her seferinde verilerin bir kısmını arabelleğe aktaran uygulama tanımlı geri çağırma işlevini tekrar tekrar çağırır.

Zengin düzenleme denetiminin içeriğini kaydetmek için (yani, verileri dışarı akışı), [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) üye işlevini kullanabilirsiniz. Denetim, arabelleğe tekrar tekrar yazar ve ardından uygulama tanımlı geri çağırma işlevini çağırır. Her çağrı için, geri çağırma işlevi arabelleğin içeriğini kaydeder.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
