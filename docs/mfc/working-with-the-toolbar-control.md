---
title: Araç Çubuğu Denetimiyle Çalışma
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: 88c00bf60f2ce1fccecd757d13b2f814e3a18be4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260510"
---
# <a name="working-with-the-toolbar-control"></a>Araç Çubuğu Denetimiyle Çalışma

Bu makalede nasıl erişebileceğinizi açıklanmaktadır [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesinin altındaki bir [CToolBar](../mfc/reference/ctoolbar-class.md) çubuklarınızı üzerinde daha fazla denetime. Bu gelişmiş bir konudur.

## <a name="procedures"></a>Yordamlar

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar nesnenizin temel araç çubuğu ortak denetim erişmek için

1. Çağrı [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl).

`GetToolBarCtrl` bir başvuru döndürür bir [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesne. Araç çubuğu denetimi sınıfın üye işlevleri çağırmak için bir başvuru kullanabilirsiniz.

> [!CAUTION]
>  Çağrılırken `CToolBarCtrl` **alma** işlevleri, güvenli, çağırırsanız dikkatli **ayarlamak** işlevleri. Bu gelişmiş bir konudur. Normalde temel alınan araç çubuğu denetimi erişimi gerekmez.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Denetimler (Windows ortak denetimleri)](../mfc/controls-mfc.md)

- [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğunda dinamik olarak yeniden boyutlandırma](../mfc/docking-and-floating-toolbars.md)

- [Araç çubuğu araç ipuçları](../mfc/toolbar-tool-tips.md)

- [Flyby durum çubuğu güncelleştirmeleri](../mfc/toolbar-tool-tips.md)

- [Araç İpucu bildirimlerini işleme](../mfc/handling-tool-tip-notifications.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) sınıfları

- [Özelleştirme bildirimlerini işleme](../mfc/handling-customization-notifications.md)

- [Birden çok araç çubukları](../mfc/toolbar-fundamentals.md)

- [Eski araç çubuklarınızı kullanma](../mfc/using-your-old-toolbars.md)

- [Denetim çubukları](../mfc/control-bars.md)

Windows ortak denetimleri kullanma hakkında genel bilgi için bkz: [ortak denetimleri](/windows/desktop/Controls/common-controls-intro).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Araç Çubuğu Uygulaması](../mfc/mfc-toolbar-implementation.md)
