---
description: 'Hakkında daha fazla bilgi edinin: bir araç çubuğu denetiminde görüntü listeleri kullanma'
title: Bir Araç Çubuğu Denetiminde Görüntü Listeleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: dbdac26f1d17997e14ed4ba16875ef3794e46a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154441"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminde Görüntü Listeleri Kullanma

Varsayılan olarak, bir araç çubuğu denetimindeki düğmeler tarafından kullanılan görüntüler tek bir bit eşlem olarak depolanır. Ancak, düğme görüntülerini bir dizi görüntü listesinde de saklayabilirsiniz. ToolBar denetim nesnesi en fazla üç ayrı görüntü listesi kullanabilir:

- Etkin görüntü listesi etkin olan araç çubuğu düğmelerinin görüntülerini Içerir.

- Devre dışı bırakılmış görüntü listesi, şu anda devre dışı bırakılmış araç çubuğu düğmelerinin görüntülerini Içerir.

- Vurgulanan görüntü listesi, vurgulanmış olan araç çubuğu düğmelerinin görüntülerini Içerir. Bu görüntü listesi yalnızca araç çubuğu TBSTYLE_FLAT stilini kullandığında kullanılır.

Bu görüntü listeleri, nesne ile ilişkilendirdiğinizde araç çubuğu denetimi tarafından kullanılır `CToolBarCtrl` . Bu ilişki [CToolBarCtrl:: SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)ve [sethotimagelist](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)çağrıları yapılarak gerçekleştirilir.

Varsayılan olarak, MFC `CToolBar` MFC uygulama araç çubuklarını uygulamak için sınıfını kullanır. Ancak, `GetToolBarCtrl` üye işlevi katıştırılmış nesneyi almak için kullanılabilir `CToolBarCtrl` . Ardından `CToolBarCtrl` döndürülen nesneyi kullanarak üye işlevlerine çağrılar yapabilirsiniz.

Aşağıdaki örnek, `m_ToolBarImages` bir nesnesine () etkin () ve devre dışı ( `m_ToolBarDisabledImages` ) görüntü listesi atayarak bu tekniği gösterir `CToolBarCtrl` `m_ToolBarCtrl` .

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
> Araç çubuğu nesnesi tarafından kullanılan görüntü listeleri kalıcı nesneler olmalıdır. Bu nedenle, genellikle MFC sınıfının veri üyeleridir; Bu örnekte, ana çerçeve pencere sınıfı.

Görüntü listeleri `CToolBarCtrl` nesneyle ilişkilendirildiğinde, çerçeve otomatik olarak uygun düğme görüntüsünü görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
