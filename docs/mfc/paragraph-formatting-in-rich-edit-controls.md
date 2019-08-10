---
title: Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: 0988e7940c8d8947b86e97a35d71586f8f5c316a
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916370"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme

Paragrafları biçimlendirmek ve biçimlendirme bilgilerini almak için zengin düzenleme denetiminin ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) üye işlevlerini kullanabilirsiniz. Paragraf biçimlendirme öznitelikleri hizalama, sekmeler, girintiler ve numaralandırma içerir.

[SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) üye işlevini kullanarak paragraf biçimlendirme uygulayabilirsiniz. Seçili metin için geçerli paragraf biçimlendirmesini öğrenmek için [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) üye işlevini kullanın. [Paraformat](/windows/desktop/api/richedit/ns-richedit-paraformat) yapısı, paragraf özniteliklerini belirtmek için bu üye işlevlerle birlikte kullanılır. **Paraformat** 'ın önemli üyelerinden biri *dwMask*. ' `SetParaFormat`De, *dwMask* bu işlev çağrısı tarafından ayarlanacak paragraf özniteliklerini belirtir. `GetParaFormat`seçimdeki ilk paragrafın özniteliklerini raporlar; *dwMask* seçim boyunca tutarlı olan öznitelikleri belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
