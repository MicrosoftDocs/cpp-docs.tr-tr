---
description: 'Daha fazla bilgi edinin: Bottomless zengin düzenleme denetimleri'
title: Tabansız Zengin Düzenleme Denetimleri
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: ad3f78fb4a5e172c16faf3421b6a9da91d422888
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339819"
---
# <a name="bottomless-rich-edit-controls"></a>Tabansız Zengin Düzenleme Denetimleri

Uygulamanız, her zaman içeriğiyle aynı boyutta olacak şekilde, bir zengin düzenleme denetimini ([CRichEditCtrl](reference/cricheditctrl-class.md)) gerektiği gibi yeniden boyutlandırabilir. Zengin düzenleme denetimi bu şekilde "bottomless" işlevselliğini destekleyerek, içeriğinin boyutu değiştiğinde üst penceresine bir [EN_REQUESTRESIZE](/windows/win32/Controls/en-requestresize) bildirim iletisi gönderir.

**EN_REQUESTRESIZE** bildirim iletisi işlenirken bir uygulama, denetimi belirtilen [reqresize](/windows/win32/api/richedit/ns-richedit-reqresize) yapısındaki boyutlara yeniden boyutlandırmalıdır. Bir uygulama, denetimin yakınlarındaki değişikliği yapmak için denetimin yakınındaki tüm bilgileri de taşıyabilir. Denetimi yeniden boyutlandırmak için `CWnd` [SetWindowPos](reference/cwnd-class.md#setwindowpos)işlevini kullanabilirsiniz.

Gereksiz bir zengin düzenleme denetimini [RequestResize](reference/cricheditctrl-class.md#requestresize) üye işlevini kullanarak **EN_REQUESTRESIZE** bildirim iletisi gönderecek şekilde zorlayabilirsiniz. Bu ileti [OnSize](reference/cwnd-class.md#onsize) işleyicisinde yararlı olabilir.

**EN_REQUESTRESIZE** bildirim iletilerini almak için, üye işlevini kullanarak bildirimi etkinleştirmeniz gerekir `SetEventMask` .

## <a name="see-also"></a>Ayrıca bkz.

[CRichEditCtrl Kullanma](using-cricheditctrl.md)<br/>
[Denetimler](controls-mfc.md)
