---
title: Araç Çubuğu Denetimiyle Çalışma
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 371f1944fae655556bbc9f89d7ffcce7cc326e5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365244"
---
# <a name="working-with-the-toolbar-control"></a>Araç Çubuğu Denetimiyle Çalışma

Bu makalede, araç çubukları üzerinde daha fazla denetim için bir [CToolBar](../mfc/reference/ctoolbar-class.md) altında yatan [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesneye nasıl erişebileceğinizaçıklanmaktadır. Bu gelişmiş bir konudur.

## <a name="procedures"></a>Yordamlar

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar nesnenizin altında yatan araç çubuğu ortak denetimine erişmek için

1. Çağrı [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).

`GetToolBarCtrl`bir [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesine bir başvuru döndürür. Başvuruyu araç çubuğu denetim sınıfının üye işlevlerini aramak için kullanabilirsiniz.

> [!CAUTION]
> `CToolBarCtrl` **İşlevbul'u** aramak güvenlidir, **Set** işlevlerini ararsanız dikkatli olun. Bu gelişmiş bir konudur. Normalde altta yatan araç çubuğu denetimine erişmeniz gerekmez.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Denetimler (Windows ortak denetimleri)](../mfc/controls-mfc.md)

- [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğunu dinamik olarak yeniden boyutlandırma](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [Flyby durum çubuğu güncellemeleri](../mfc/toolbar-tool-tips.md)

- [Kullanım aracı ipucu bildirimleri](../mfc/handling-tool-tip-notifications.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Özelleştirme bildirimlerini işleme](../mfc/handling-customization-notifications.md)

- [Birden çok araç çubuğu](../mfc/toolbar-fundamentals.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

- [Kontrol çubukları](../mfc/control-bars.md)

Windows ortak denetimlerini kullanma hakkında genel bilgi için [Ortak Denetimler'e](/windows/win32/Controls/common-controls-intro)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)
