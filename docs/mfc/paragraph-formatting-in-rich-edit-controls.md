---
title: Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: f79d9a97554e2f73b42746c9e9094b07a37513d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581980"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme

Zengin Düzenleme denetiminin üye işlevleri kullanabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) paragraflar biçimlendirmek ve biçimlendirme bilgileri alınamıyor. Hizalama, sekmeler, girintileri ve numaralandırma paragraf biçimlendirme öznitelikleri içerir.

Paragraf kullanarak biçimlendirme uygulayabilirsiniz [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) üye işlevi. Seçili metin için geçerli paragraf belirlemek için [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) üye işlevi. [PARAFORMAT](/windows/desktop/api/richedit/ns-richedit-_paraformat) yapısı, paragraf öznitelikleri belirtmek için bu üye işlevleri ile kullanılır. Önemli üyelerinden birinde **PARAFORMAT** olduğu *dwMask*. İçinde `SetParaFormat`, *dwMask* paragraf öznitelikleri bu işlev çağrısına göre ayarlanacağını belirtir. `GetParaFormat` Seçimdeki ilk paragrafa özniteliklerini bildirir; *dwMask* seçimi tutarlı öznitelikleri belirtir.

## <a name="see-also"></a>Ayrıca Bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

