---
title: "Bir zengin düzenleme bildirim denetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcfcb2e4fe333db1ed629489b405255d4ab050b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-from-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetiminden Bildirim
Bildirim iletileri bir zengin etkileyen olayları düzenleme denetimi raporu ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). İleti yansıması kullanarak tarafından zengin düzenleme denetiminden kendisini veya üst pencere tarafından işlenebilir. Zengin düzenleme denetimlerinde birkaç ek olanları yanı sıra düzenleme denetimleri ile kullanılan bildirim iletilerinin desteklemez. Bildirim iletileri bir zengin düzenleme denetimine kendi üst penceresi "olay maskesini." ayarlayarak gönderir belirleme  
  
 Bir zengin düzenleme denetiminden için olay maskesi ayarlamak için kullanın [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) üye işlevi. Bir zengin düzenleme denetiminden kullanarak için geçerli olay maskesi alabilirsiniz [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) üye işlevi.  
  
 Aşağıdaki paragraflara birkaç belirli bildirimleri ve kullanımlarının listesi:  
  
-   **EN_MSGFILTER** işleme **EN_MSGFILTER** bildirim sağlayan bir sınıf, ya da zengin denetim veya kendi üst penceresi düzenlemek, filtre tüm klavye ve fare giriş denetimine. İşleyicinin klavye veya fare ileti işlenmekte olan engelleyebilir veya iletinin belirtilen değiştirerek değiştirebilirsiniz [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936) yapısı.  
  
-   **EN_PROTECTED** işlemek **EN_PROTECTED** kullanıcı korumalı metin değiştirmeye çalıştığında algılamak için bildirim iletisi. Bir metin aralığını korumalı olarak işaretlemek için korumalı karakter etkisi ayarlayabilirsiniz. Daha fazla bilgi için bkz: [zengin düzenleme denetimlerinde karakter biçimlendirme](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   **EN_DROPFILES** işleyerek bir zengin düzenleme denetimindeki dosyalarını bırakmaya kullanıcı etkinleştirebilirsiniz **EN_DROPFILES** bildirim iletisi. Belirtilen [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) yapısı bırakılmakta dosyalarıyla ilgili bilgiler içerir.  
  
-   **EN_SELCHANGE** geçerli seçim işleyerek değiştiğinde uygulama algılayabilir **EN_SELCHANGE** bildirim iletisi. Bildirim iletisi belirten bir [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) yeni seçimi hakkında bilgi içeren yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

