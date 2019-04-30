---
title: Tabansız Zengin Düzenleme Denetimleri
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: 6f078680777dcf80a4349ea34e4520cb56031f44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400753"
---
# <a name="bottomless-rich-edit-controls"></a>Tabansız Zengin Düzenleme Denetimleri

Uygulamanızı bir zengin düzenleme denetimi yeniden boyutlandırabilirsiniz ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) her zaman içeriğinin aynı boyutta olması gerektiği gibi. Bir zengin düzenleme denetiminin üst pencereye göndererek bu sözde "sınırsız" işlevi destekler. bir [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize) içeriği boyutu değiştiğinde bildirim iletisi.

İşleme sırasında **EN_REQUESTRESIZE** bildirim iletisi, uygulama denetimi belirtilen boyutlar için yeniden boyutlandırma [REQRESIZE](/windows/desktop/api/richedit/ns-richedit-_reqresize) yapısı. Bir uygulama da denetimin yüksekliği denetimin değişikliği karşılamak için neredeyse tüm bilgileri taşımanız da mümkün olabilir. Denetimi yeniden boyutlandırmak için kullanabilirsiniz `CWnd` işlevi [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).

Gönderilecek tabansız zengin düzenleme denetimi zorlayabilirsiniz bir **EN_REQUESTRESIZE** kullanarak bildirim iletisi [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) üye işlevi. Bu ileti kullanışlı olabilir [nesne yerinde düzenlenirken](../mfc/reference/cwnd-class.md#onsize) işleyici.

Almaya **EN_REQUESTRESIZE** bildirim iletileri kullanarak bildirim etkinleştirmelisiniz `SetEventMask` üye işlevi.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
