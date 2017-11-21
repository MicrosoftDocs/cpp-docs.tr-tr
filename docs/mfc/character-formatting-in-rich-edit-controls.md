---
title: "Zengin düzenleme denetimlerinde karakter biçimlendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 86b9686396d8f3bd6abd67f5a1f33be0d20bdc16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="character-formatting-in-rich-edit-controls"></a>Zengin Düzenleme Denetimlerinde Karakter Biçimlendirme
Zengin düzenleme denetimine üye işlevlerini kullanabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) karakter biçimlendirme ve biçimlendirme bilgilerini almak için. Karakterler için yazı tipi, boyut, renk ve kalın, italik gibi efektler belirtebilirsiniz ve korumalı.  
  
 Karakter kullanarak biçimlendirme uygulayabilirsiniz [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat) ve [SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat) üye işlevleri. Seçili metni biçimlendirme geçerli karakteri belirlemek için [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat) üye işlevi. [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) yapısı karakter özniteliklerini belirtmek için bu üye işlevleri ile kullanılır. Önemli üyelerinden birinde **CHARFORMAT** olan **dwMask**. İçinde `SetSelectionCharFormat` ve `SetWordCharFormat`, **dwMask** bu işlev çağrısı tarafından hangi karakter özniteliklerini ayarlanacağını belirtir. `GetSelectionCharFormat`Raporlar seçim içindeki ilk karakter özniteliklerini; **dwMask** seçimi tutarlı özniteliklerini belirtir.  
  
 Ayrıca almak ve "varsayılan karakter biçimlendirme," ayarlamak için daha sonra eklenen tüm karakterleri uygulanan biçimlendirme olduğu. Örneğin, bir uygulamanın varsayılan karakter kalın biçimlendirme ayarlar ve kullanıcı daha sonra bir karakter türleri, bu kalın karakterdir. Alma ve varsayılan karakter biçimlendirme ayarlamak için kullanın [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat) ve [SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat) üye işlevleri.  
  
 "Korumalı" karakter özniteliği metin görünümünü değiştirmez. Kullanıcı korumalı metin değiştirmeye çalışırsa, kendi üst penceresi bir zengin düzenleme denetimine gönderir bir **EN_PROTECTED** izin vermek veya değişiklik önlemek üst pencere izin vererek, bildirim iletisini. Bu bildirim iletisini almak için onu kullanarak etkinleştirmelisiniz [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) üye işlevi. Olay maskesi hakkında daha fazla bilgi için bkz: [bir zengin düzenleme denetiminden bildirim](../mfc/notifications-from-a-rich-edit-control.md), bu konunun devamındaki.  
  
 Ön plan rengini karakter özniteliği, ancak arka plan rengi zengin düzenleme denetimine özelliğidir. Arka plan rengini ayarlamak için kullanın [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

