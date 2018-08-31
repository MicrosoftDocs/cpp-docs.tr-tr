---
title: Tabansız zengin düzenleme denetimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9e3115000b7b45d9b48a1ac0d274eb32c11f4d0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218885"
---
# <a name="bottomless-rich-edit-controls"></a>Tabansız Zengin Düzenleme Denetimleri
Uygulamanızı bir zengin düzenleme denetimi yeniden boyutlandırabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) her zaman içeriğinin aynı boyutta olması gerektiği gibi. Bir zengin düzenleme denetiminin üst pencereye göndererek bu sözde "sınırsız" işlevi destekler. bir [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize) içeriği boyutu değiştiğinde bildirim iletisi.  
  
 İşleme sırasında **EN_REQUESTRESIZE** bildirim iletisi, uygulama denetimi belirtilen boyutlar için yeniden boyutlandırma [REQRESIZE](/windows/desktop/api/richedit/ns-richedit-_reqresize) yapısı. Bir uygulama da denetimin yüksekliği denetimin değişikliği karşılamak için neredeyse tüm bilgileri taşımanız da mümkün olabilir. Denetimi yeniden boyutlandırmak için kullanabilirsiniz `CWnd` işlevi [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).  
  
 Gönderilecek tabansız zengin düzenleme denetimi zorlayabilirsiniz bir **EN_REQUESTRESIZE** kullanarak bildirim iletisi [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) üye işlevi. Bu ileti kullanışlı olabilir [nesne yerinde düzenlenirken](../mfc/reference/cwnd-class.md#onsize) işleyici.  
  
 Almaya **EN_REQUESTRESIZE** bildirim iletileri kullanarak bildirim etkinleştirmelisiniz `SetEventMask` üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRichEditCtrl kullanma](../mfc/using-cricheditctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

