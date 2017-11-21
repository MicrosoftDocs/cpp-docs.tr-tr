---
title: "Tabansız zengin düzenleme denetimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e0b86dfa8a5efc5b7bfce7b7e0704dd030b8a937
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bottomless-rich-edit-controls"></a>Tabansız Zengin Düzenleme Denetimleri
Uygulamanızı bir zengin düzenleme denetimine boyutlandırabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) her zaman içeriğinin aynı boyutta olduğundan gerektiği şekilde. Zengin düzenleme denetimine kendi üst penceresi göndererek bu sözde "tabansız" işlevselliği destekler bir [EN_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983) içeriğinin boyutunu değiştiğinde bildirim iletisi.  
  
 İşleme sırasında **EN_REQUESTRESIZE** bildirim iletisi, bir uygulama belirtilen boyutlar denetimine yeniden boyutlandırma [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950) yapısı. Bir uygulamayı yüksekliğini denetimin değişikliği karşılamak için Denetim yakın herhangi bir bilgi de taşımak. Denetim yeniden boyutlandırmak için kullanabileceğiniz `CWnd` işlevi [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).  
  
 Gönderilecek tabansız zengin düzenleme denetimi zorlayabilirsiniz bir **EN_REQUESTRESIZE** kullanarak bildirim iletisi [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) üye işlevi. Bu ileti kullanışlı olabilir [OnSize](../mfc/reference/cwnd-class.md#onsize) işleyicisi.  
  
 Almak için **EN_REQUESTRESIZE** bildirim iletileri kullanarak bildirim etkinleştirmelisiniz `SetEventMask` üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

