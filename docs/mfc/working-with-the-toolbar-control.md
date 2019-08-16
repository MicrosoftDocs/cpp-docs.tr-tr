---
title: Araç Çubuğu Denetimiyle Çalışma
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 60cc527493e2a68751c201b998ab171c564d6c1f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510584"
---
# <a name="working-with-the-toolbar-control"></a>Araç Çubuğu Denetimiyle Çalışma

Bu makalede, araç çubuklarınız üzerinde daha fazla denetim için [CToolBar](../mfc/reference/ctoolbar-class.md) 'ı temel alan [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesine nasıl erişebileceğiniz açıklanır. Bu, gelişmiş bir konudur.

## <a name="procedures"></a>Yordamlar

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar nesnenizin temelindeki araç çubuğu ortak denetimine erişmek için

1. [CToolBar:: GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl)çağrısı yapın.

`GetToolBarCtrl`[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesine bir başvuru döndürür. Bu başvuruyu, ToolBar denetim sınıfının üye işlevlerini çağırmak için kullanabilirsiniz.

> [!CAUTION]
>  **Get** işlevlerini `CToolBarCtrl` çağırırken, **set** işlevlerini çağırdığınızda dikkatli olun. Bu, gelişmiş bir konudur. Normalde, temel alınan araç çubuğu denetimine erişmeniz gerekmez.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Denetimler (Windows ortak denetimleri)](../mfc/controls-mfc.md)

- [Araç Çubuğu Temelleri](../mfc/toolbar-fundamentals.md)

- [Yerleştirme ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğunu dinamik olarak yeniden boyutlandırma](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [Durum çubuğu güncelleştirmelerine göre daha fazla](../mfc/toolbar-tool-tips.md)

- [Araç ipucu bildirimlerini işleme](../mfc/handling-tool-tip-notifications.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Özelleştirme bildirimlerini işleme](../mfc/handling-customization-notifications.md)

- [Birden çok araç çubuğu](../mfc/toolbar-fundamentals.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

- [Denetim çubukları](../mfc/control-bars.md)

Windows ortak denetimlerini kullanma hakkında genel bilgi için bkz. [ortak denetimler](/windows/win32/Controls/common-controls-intro).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)
