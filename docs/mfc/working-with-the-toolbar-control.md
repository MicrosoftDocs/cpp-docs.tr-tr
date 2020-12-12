---
description: 'Hakkında daha fazla bilgi edinin: araç çubuğu denetimiyle çalışma'
title: Araç Çubuğu Denetimiyle Çalışma
ms.date: 11/04/2016
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
ms.openlocfilehash: bb5b14b35deeff515468a16c82a606704300a395
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197471"
---
# <a name="working-with-the-toolbar-control"></a>Araç Çubuğu Denetimiyle Çalışma

Bu makalede, araç çubuklarınız üzerinde daha fazla denetim için [CToolBar](../mfc/reference/ctoolbar-class.md) 'ı temel alan [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesine nasıl erişebileceğiniz açıklanır. Bu, gelişmiş bir konudur.

## <a name="procedures"></a>Yordamlar

#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar nesnenizin temelindeki araç çubuğu ortak denetimine erişmek için

1. [CToolBar:: GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl)çağrısı yapın.

`GetToolBarCtrl`[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesnesine bir başvuru döndürür. Bu başvuruyu, ToolBar denetim sınıfının üye işlevlerini çağırmak için kullanabilirsiniz.

> [!CAUTION]
> `CToolBarCtrl` **Get** Işlevlerini çağırırken, **set** işlevlerini çağırdığınızda dikkatli olun. Bu, gelişmiş bir konudur. Normalde, temel alınan araç çubuğu denetimine erişmeniz gerekmez.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Denetimler (Windows ortak denetimleri)](../mfc/controls-mfc.md)

- [Araç çubuğu temelleri](../mfc/toolbar-fundamentals.md)

- [Yerleşen ve kayan araç çubukları](../mfc/docking-and-floating-toolbars.md)

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

[MFC araç çubuğu uygulama](../mfc/mfc-toolbar-implementation.md)
