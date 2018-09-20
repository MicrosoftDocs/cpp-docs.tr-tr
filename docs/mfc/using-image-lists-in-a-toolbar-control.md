---
title: Bir araç çubuğu denetiminde görüntü listeleri kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3604de0b3b24b638e549c6823ea6c95036543c1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401777"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

