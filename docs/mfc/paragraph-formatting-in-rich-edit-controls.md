---
title: Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: f2ac69838bf39afb636c3d41c97adc1378463d1b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507984"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme

Paragrafları biçimlendirmek ve biçimlendirme bilgilerini almak için zengin düzenleme denetiminin ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) üye işlevlerini kullanabilirsiniz. Paragraf biçimlendirme öznitelikleri hizalama, sekmeler, girintiler ve numaralandırma içerir.

[SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) üye işlevini kullanarak paragraf biçimlendirme uygulayabilirsiniz. Seçili metin için geçerli paragraf biçimlendirmesini öğrenmek için [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) üye işlevini kullanın. [Paraformat](/windows/win32/api/richedit/ns-richedit-paraformat) yapısı, paragraf özniteliklerini belirtmek için bu üye işlevlerle birlikte kullanılır. **Paraformat** 'ın önemli üyelerinden biri *dwMask*. ' `SetParaFormat`De, *dwMask* bu işlev çağrısı tarafından ayarlanacak paragraf özniteliklerini belirtir. `GetParaFormat`seçimdeki ilk paragrafın özniteliklerini raporlar; *dwMask* seçim boyunca tutarlı olan öznitelikleri belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
