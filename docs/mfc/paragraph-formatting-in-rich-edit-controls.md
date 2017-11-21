---
title: "Zengin düzenleme denetimlerinde paragraf biçimlendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e65611c915bfdaf5b8a0e03e2fb44804e65f904f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Paragraf Biçimlendirme
Zengin düzenleme denetimine üye işlevlerini kullanabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) paragraf biçimlendirme ve biçimlendirme bilgilerini almak için. Paragraf biçimlendirme öznitelikleri hizalama, sekmeler, girintileri ve numaralandırma içerir.  
  
 Paragraf kullanarak biçimlendirme uygulayabilirsiniz [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) üye işlevi. Seçili metni geçerli paragraf belirlemek için [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) üye işlevi. [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) yapısı paragraf özniteliklerini belirtmek için bu üye işlevleri ile kullanılır. Önemli üyelerinden birinde **PARAFORMAT** olan **dwMask**. İçinde `SetParaFormat`, **dwMask** bu işlev çağrısı tarafından hangi paragraf özniteliklerin ayarlanacağını belirtir. `GetParaFormat`Seçim ilk paragrafa özniteliklerini raporları; **dwMask** seçimi tutarlı özniteliklerini belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

