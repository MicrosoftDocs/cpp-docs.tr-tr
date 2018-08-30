---
title: Zengin düzenleme denetimlerinde paragraf biçimlendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8258ff95fc91f6f29d424e77be95ce1b44f621ac
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215827"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme
Zengin Düzenleme denetiminin üye işlevleri kullanabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) paragraflar biçimlendirmek ve biçimlendirme bilgileri alınamıyor. Hizalama, sekmeler, girintileri ve numaralandırma paragraf biçimlendirme öznitelikleri içerir.  
  
 Paragraf kullanarak biçimlendirme uygulayabilirsiniz [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) üye işlevi. Seçili metin için geçerli paragraf belirlemek için [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) üye işlevi. [PARAFORMAT](/windows/desktop/api/richedit/ns-richedit-_paraformat) yapısı, paragraf öznitelikleri belirtmek için bu üye işlevleri ile kullanılır. Önemli üyelerinden birinde **PARAFORMAT** olduğu *dwMask*. İçinde `SetParaFormat`, *dwMask* paragraf öznitelikleri bu işlev çağrısına göre ayarlanacağını belirtir. `GetParaFormat` Seçimdeki ilk paragrafa özniteliklerini bildirir; *dwMask* seçimi tutarlı öznitelikleri belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

