---
title: Tabansız Zengin Düzenleme Denetimleri
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: 4affdbeed723ea83beda785116dc4c45771073b2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509154"
---
# <a name="bottomless-rich-edit-controls"></a>Tabansız Zengin Düzenleme Denetimleri

Uygulamanız, her zaman içeriğiyle aynı boyutta olacak şekilde, bir zengin düzenleme denetimini ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) gerektiği gibi yeniden boyutlandırabilir. Zengin düzenleme denetimi bu şekilde "bottomless" işlevselliğini destekler. bu nedenle, içeriğinin boyutu değiştiğinde üst pencere bir [EN_REQUESTRESIZE](/windows/win32/Controls/en-requestresize) bildirim iletisi gönderir.

**EN_REQUESTRESIZE** bildirim iletisi işlenirken bir uygulama, denetimi belirtilen [reqresize](/windows/win32/api/richedit/ns-richedit-reqresize) yapısındaki boyutlara yeniden boyutlandırmalıdır. Bir uygulama, denetimin yakınlarındaki değişikliği yapmak için denetimin yakınındaki tüm bilgileri de taşıyabilir. Denetimi yeniden boyutlandırmak için `CWnd` [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)işlevini kullanabilirsiniz.

Daha az zengin bir zengin düzenleme denetimini [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) üye işlevini kullanarak bir **EN_REQUESTRESIZE** bildirim iletisi gönderecek şekilde zorlayabilirsiniz. Bu ileti [OnSize](../mfc/reference/cwnd-class.md#onsize) işleyicisinde yararlı olabilir.

**EN_REQUESTRESIZE** bildirim iletilerini almak için, `SetEventMask` üye işlevini kullanarak bildirimi etkinleştirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](../mfc/using-cricheditctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
