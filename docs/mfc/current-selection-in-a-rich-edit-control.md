---
title: Zengin düzenleme denetimindeki geçerli bölüm | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 782984bc53bc16f8dc89e4e705811fef24b8931e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="current-selection-in-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetimindeki Geçerli Bölüm
Kullanıcı bir zengin düzenleme denetimine metin seçebilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) fare veya klavyeyi kullanarak. Geçerli seçim seçili karakter aralığı veya ekleme noktasını hiçbir karakter varsa konumunu seçilir. Uygulamanın geçerli seçim hakkında bilgi almak, geçerli seçim ayarlayın, geçerli seçim değişiklikleri ve Göster veya gizle seçim zaman vurgulayın belirleyin.  
  
 Zengin düzenleme denetimindeki geçerli bölüm belirlemek için [GetSel](../mfc/reference/cricheditctrl-class.md#getsel) üye işlevi. Geçerli seçim ayarlamak için kullanın [SetSel](../mfc/reference/cricheditctrl-class.md#setsel) üye işlevi. [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) yapısı karakter aralığı belirtmek için bu işlevleri ile kullanılır. Geçerli seçimin içeriğine hakkında bilgi almak için kullanabileceğiniz [GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype) üye işlevi.  
  
 Varsayılan olarak, bir zengin düzenleme denetimine gösterir ve kazanır ve odağı kaybettiğinde seçim Vurgusu gizler. Göster veya kullanarak herhangi bir zamanda seçim Vurgusu Gizle [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) üye işlevi. Örneğin, bir uygulama bir zengin düzenleme denetimine metin bulmak için arama iletişim kutusu sağlayabilir. Uygulama iletişim kutusunu kapatmadan eşleşen metin seçebilirsiniz, bu durumda kullanmanız gerekir `HideSelection` seçimi vurgulayın.  
  
 Seçili metni bir zengin düzenleme denetimine almak için [GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext) üye işlevi. Metnin belirtilen karakter dizisine kopyalanır. Dizi seçili metni artı sonlandırma bir null karakter tutmak için yeterince büyük olduğundan emin olmanız gerekir.  
  
 Bir zengin düzenleme denetimindeki bir dize kullanarak arayabilirsiniz [FindText](../mfc/reference/cricheditctrl-class.md#findtext) üye işlevi [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) bu işlev ile kullanılan yapısı aramak ve aranacak dizeyi metin aralığını belirtir. Bu seçenekler ayrıca arama büyük küçük harfe duyarlı olup olarak da belirtebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

