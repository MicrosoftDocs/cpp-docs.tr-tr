---
title: Bir zengin düzenleme bildirim denetimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928728093ff6e2150578c4ba48f2d8081620a48d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931150"
---
# <a name="notifications-from-a-rich-edit-control"></a>Bir Zengin Düzenleme Denetiminden Bildirim
Bildirim iletileri bir zengin etkileyen olayları düzenleme denetimi raporu ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). İleti yansıması kullanarak tarafından zengin düzenleme denetiminden kendisini veya üst pencere tarafından işlenebilir. Zengin düzenleme denetimlerinde birkaç ek olanları yanı sıra düzenleme denetimleri ile kullanılan bildirim iletilerinin desteklemez. Bildirim iletileri bir zengin düzenleme denetimine kendi üst penceresi "olay maskesini." ayarlayarak gönderir belirleme  
  
 Bir zengin düzenleme denetiminden için olay maskesi ayarlamak için kullanın [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) üye işlevi. Bir zengin düzenleme denetiminden kullanarak için geçerli olay maskesi alabilirsiniz [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) üye işlevi.  
  
 Aşağıdaki paragraflara birkaç belirli bildirimleri ve kullanımlarının listesi:  
  
-   EN_MSGFILTER işleme EN_MSGFILTER bildirim bir sınıf ya da zengin düzenleme denetimine veya tüm klavye ve fare denetime giriş filtre kendi üst penceresi sağlar. İşleyicinin klavye veya fare ileti işlenmekte olan engelleyebilir veya iletinin belirtilen değiştirerek değiştirebilirsiniz [MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936) yapısı.  
  
-   EN_PROTECTED kullanıcı korumalı metin değiştirmeye çalıştığında algılamak için EN_PROTECTED bildirim iletisini işler. Bir metin aralığını korumalı olarak işaretlemek için korumalı karakter etkisi ayarlayabilirsiniz. Daha fazla bilgi için bkz: [zengin düzenleme denetimlerinde karakter biçimlendirme](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   EN_DROPFILES EN_DROPFILES bildirim iletisi işleyerek bir zengin düzenleme denetimindeki dosyalarını bırakmaya kullanıcı etkinleştirebilirsiniz. Belirtilen [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) yapısı bırakılmakta dosyalarıyla ilgili bilgiler içerir.  
  
-   Geçerli seçim EN_SELCHANGE bildirim iletisi işleyerek değiştiğinde EN_SELCHANGE uygulamanın algılayabilir. Bildirim iletisi belirten bir [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) yeni seçimi hakkında bilgi içeren yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

