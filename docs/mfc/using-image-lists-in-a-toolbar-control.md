---
title: Bir Araç Çubuğu Denetiminde Görüntü Listeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: 81468528c15300a7e9ace6b20fd9fb34818f1928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366493"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminde Görüntü Listeleri Kullanma

Varsayılan olarak, araç çubuğu denetimindeki düğmeler tarafından kullanılan görüntüler tek bir bit eşlemi olarak depolanır. Ancak, düğme görüntülerini bir dizi resim listesinde de depolayabilirsiniz. Araç çubuğu denetim nesnesi en fazla üç ayrı resim listesi kullanabilir:

- Etkinleştirilmiş resim listesi Şu anda etkin olan araç çubuğu düğmeleri için görüntüler içerir.

- Devre dışı bırakılmış resim listesi Şu anda devre dışı bırakılan araç çubuğu düğmeleri için görüntüler içerir.

- Vurgulanan resim listesi Şu anda vurgulanan araç çubuğu düğmeleri için görüntüler içerir. Bu resim listesi yalnızca araç çubuğu TBSTYLE_FLAT stilini kullandığında kullanılır.

Bu resim listeleri, `CToolBarCtrl` nesneyle ilişkilendirdiğinizde araç çubuğu denetimi tarafından kullanılır. Bu ilişkilendirme [CToolBarCtrl::SetImageList,](../mfc/reference/ctoolbarctrl-class.md#setimagelist) [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)ve [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)aramaları yaparak gerçekleştirilir.

Varsayılan olarak, MFC `CToolBar` MFC uygulama araç çubuklarını uygulamak için sınıfı kullanır. Ancak, `GetToolBarCtrl` üye işlev katıştan katılmış `CToolBarCtrl` nesneyi almak için kullanılabilir. Daha sonra döndürülen `CToolBarCtrl` nesneyi kullanarak üye işlevlere çağrı yapabilirsiniz.

Aşağıdaki örnek, etkin leştirilmiş (`m_ToolBarImages`) ve devre`m_ToolBarDisabledImages`dışı bırakılmış ( `CToolBarCtrl` )`m_ToolBarCtrl`görüntü listesini bir nesneye ( ) atayarak bu tekniği gösterir.

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
> Araç çubuğu nesnesi tarafından kullanılan görüntü listeleri kalıcı nesneler olmalıdır. Bu nedenle, genellikle bir MFC sınıfının veri üyeleridir; Bu örnekte, ana çerçeve pencere sınıfı.

Görüntü listeleri `CToolBarCtrl` nesneyle ilişkilendirildikten sonra, çerçeve uygun düğme görüntüsünü otomatik olarak görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
