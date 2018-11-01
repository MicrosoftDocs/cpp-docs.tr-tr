---
title: Bir CStatusBarCtrl Nesnesinin Bölümlerini Başlatma
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
ms.openlocfilehash: c813ef53f94fb773b62f102a484eed2be859772e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662169"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinin Bölümlerini Başlatma

Varsayılan olarak, bir durum çubuğu ayrı bölmelerini kullanarak durum bilgilerini görüntüler. Bunlardan (parçaları olarak da bilinir), bir metin dizesi, bir simge ya da her ikisi de içerebilir.

Kullanım [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) kaç bölümleri ve uzunluğu tanımlamak için durum çubuğunu olacaktır. Durum çubuğu bölümlerini oluşturduktan sonra çağrı yapmak [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) ve [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) metin veya simge özel bir durum çubuğu bölümü için ayarlanacak. Denetim bölümü başarıyla ayarladıktan sonra otomatik olarak yeniden çizilir.

Aşağıdaki örnekte mevcut bir başlatır `CStatusBarCtrl` nesne (`m_StatusBarCtrl`) ile dört bölmeleri ve ardından ikinci bölümünde bir simge (IDI_ICON1) ve bazı metin ayarlar.

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

Modunu ayarlama hakkında daha fazla bilgi için bir `CStatusBarCtrl` basit, bkz: nesnesine [CStatusBarCtrl nesnesinin modunu ayarlama](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

