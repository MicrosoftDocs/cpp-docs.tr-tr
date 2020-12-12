---
description: 'Daha fazla bilgi edinin: zengin düzenleme denetimlerinde paragraf biçimlendirme'
title: Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: 69c853c6b552b9950769fc9e3509bd4b5e55ea43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205921"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme

Paragrafları biçimlendirmek ve biçimlendirme bilgilerini almak için zengin düzenleme denetiminin ([CRichEditCtrl](reference/cricheditctrl-class.md)) üye işlevlerini kullanabilirsiniz. Paragraf biçimlendirme öznitelikleri hizalama, sekmeler, girintiler ve numaralandırma içerir.

[SetParaFormat](reference/cricheditctrl-class.md#setparaformat) üye işlevini kullanarak paragraf biçimlendirme uygulayabilirsiniz. Seçili metin için geçerli paragraf biçimlendirmesini öğrenmek için [GetParaFormat](reference/cricheditctrl-class.md#getparaformat) üye işlevini kullanın. [Paraformat](/windows/win32/api/richedit/ns-richedit-paraformat) yapısı, paragraf özniteliklerini belirtmek için bu üye işlevlerle birlikte kullanılır. **Paraformat** 'ın önemli üyelerinden biri *dwMask*. ' De `SetParaFormat` , *dwMask* bu işlev çağrısı tarafından ayarlanacak paragraf özniteliklerini belirtir. `GetParaFormat` seçimdeki ilk paragrafın özniteliklerini raporlar; *dwMask* seçim boyunca tutarlı olan öznitelikleri belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](using-cricheditctrl.md)<br/>
[Denetimler](controls-mfc.md)
