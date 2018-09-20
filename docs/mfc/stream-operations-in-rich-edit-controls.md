---
title: Zengin düzenleme denetimlerinde Operations Stream | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f34417d765151adbd7a6c02b7a76ef9d5732994f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441999"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Akış İşlemleri

İçine veya dışına bir zengin düzenleme denetimi ile veri aktarmayı akışları kullanabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Bir akış tarafından tanımlanan bir [EDITSTREAM](/windows/desktop/api/richedit/ns-richedit-_editstream) yapısı, arabellek ve uygulama tanımlı geri çağırma işlevi belirtir.

Verileri bir zengin düzenleme denetimi okumak için (diğer bir deyişle, veriler akışla) kullanan [StreamIn](../mfc/reference/cricheditctrl-class.md#streamin) üye işlevi. Denetim sürekli arabelleğe her zaman verilerin bir kısmını aktaran uygulama tanımlı geri çağırma işlevini çağırır.

Zengin içeriğini düzenleme denetimi kaydetmek için (diğer bir deyişle, çıkış veri akışını) kullanabileceğiniz [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) üye işlevi. Denetim sürekli arabelleğe yazar ve sonra uygulama tanımlı geri çağırma işlevini çağırır. Her çağrı için arabellek içeriği geri çağırma işlevini kaydeder.

## <a name="see-also"></a>Ayrıca Bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

