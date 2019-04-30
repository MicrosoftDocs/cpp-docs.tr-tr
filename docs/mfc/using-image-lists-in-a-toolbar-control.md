---
title: Bir Araç Çubuğu Denetiminde Görüntü Listeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: d027f7834c67ad0ed51d1b7fda5b2704972efe38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411571"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminde Görüntü Listeleri Kullanma

Varsayılan olarak, bir toolbar denetimine düğme tarafından kullanılan görüntülerin tek bir bit eşlem olarak depolanır. Ancak, düğme resimlerini de görüntü listeleri kümesi içinde depolayabilirsiniz. Araç çubuğu denetim nesnesi, en fazla üç ayrı bir görüntü listeleri kullanabilirsiniz:

- Görüntü listesi içerir görüntüler şu anda etkin araç çubuğu düğmeleri için etkin.

- Görüntü listesi içerir görüntüler şu anda devre dışı bırakılmış bir araç çubuğu düğmeleri için devre dışı.

- Görüntü listesi içerir görüntüler şu anda vurgulanır araç çubuğu düğmeleri için vurgulanır. Bu görüntü listesi araç çubuğu TBSTYLE_FLAT stili kullandığında kullanılır.

Bu görüntü listeleri araç çubuğu denetimi tarafından kullanılan bunlarla ilişkilendirdiğinizde `CToolBarCtrl` nesne. Bu ilişkilendirmeyi çağrı yaparak gerçekleştirilir [CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), ve [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist).

Varsayılan olarak, bir MFC kullanmadığı `CToolBar` MFC Uygulama araç çubukları uygulamak için sınıfı. Ancak, `GetToolBarCtrl` üye işlevi, katıştırılmış almak için kullanılabilir `CToolBarCtrl` nesne. Daha sonra çağrı yapabilirsiniz `CToolBarCtrl` üye işlevlerini kullanarak döndürülen nesne.

Aşağıdaki örnek, etkin bir atayarak bu tekniği gösterir (`m_ToolBarImages`) ve devre dışı bırakıldı (`m_ToolBarDisabledImages`) için resim listesi bir `CToolBarCtrl` nesne (`m_ToolBarCtrl`).

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
>  Görüntü listelerini araç çubuğu nesnesi tarafından kullanılan kalıcı nesneler olması gerekir. Bu nedenle, genellikle bir MFC sınıfı veri üyesi olduğu; Bu örnekte, ana çerçeve penceresi sınıfı.

Görüntü listelerini ilişkili sonra `CToolBarCtrl` nesne framework otomatik olarak uygun düğme resminin görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
