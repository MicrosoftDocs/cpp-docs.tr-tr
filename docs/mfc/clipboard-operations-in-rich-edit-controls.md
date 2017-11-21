---
title: "Pano işlemleri zengin düzenleme denetimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d36daeea830517527ccc4e9db35439dcbe2feed1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Pano İşlemleri
Uygulamanızı bir zengin düzenleme denetimine Pano içeriğini yapıştırın ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) en iyi kullanılabilir Pano biçimi veya belirli bir pano biçimi kullanarak. Ayrıca, bir zengin düzenleme denetimine Pano biçimi yapıştırma uyumlu olup olmadığını belirleyebilirsiniz.  
  
 Kopyalama veya geçerli seçim içeriğini kullanarak kesme [kopya](../mfc/reference/cricheditctrl-class.md#copy) veya [Kes](../mfc/reference/cricheditctrl-class.md#cut) üye işlevi. Zengin düzenleme denetimine kullanarak Pano içeriğini benzer şekilde, yapıştırabilirsiniz [Yapıştır](../mfc/reference/cricheditctrl-class.md#paste) üye işlevi. Denetimi, büyük olasılıkla en açıklayıcı bir biçim olduğu tanıdığı, ilk kullanılabilir biçimi gönderebilir.  
  
 Belirli bir pano biçimi yapıştırmak için kullanabileceğiniz [denetlemeye](../mfc/reference/cricheditctrl-class.md#pastespecial) üye işlevi. Bu işlev, Pano biçimi seçmek kullanıcının sağlayan bir Özel Yapıştır komut olan uygulamalar için kullanışlıdır. Kullanabileceğiniz [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) denetim tarafından verilen bir biçim tanınan olup olmadığını belirlemek için üye işlevi.  
  
 Aynı zamanda `CanPaste` tüm kullanılabilir Pano biçimi bir zengin düzenleme denetimine tanınan olup olmadığını belirlemek için. Bu işlev yararlıdır `OnInitMenuPopup` işleyicisi. Bir uygulama etkinleştirin veya gri denetim kullanılabilir herhangi bir biçimde olup olmadığını yapıştırabilirsiniz bağlı olarak, Yapıştır komutu.  
  
 Zengin düzenleme denetimleri kayıt iki Pano biçimleri: zengin metin biçimi ve RichEdit metin ve nesneleri olarak adlandırılan bir biçimi. Bir uygulama kullanarak bu biçimler kaydedebilirsiniz [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) işlev, belirtme **CF_RTF** ve **CF_RETEXTOBJ** değerleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

