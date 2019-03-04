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
ms.openlocfilehash: 0f00aee03a74799bf14563653b50c487ff001d02
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264345"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinin Bölümlerini Başlatma

Varsayılan olarak, bir durum çubuğu ayrı bölmelerini kullanarak durum bilgilerini görüntüler. Bunlardan (parçaları olarak da bilinir), bir metin dizesi, bir simge ya da her ikisi de içerebilir.

Kullanım [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) kaç bölümleri ve uzunluğu tanımlamak için durum çubuğunu olacaktır. Durum çubuğu bölümlerini oluşturduktan sonra çağrı yapmak [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) ve [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) metin veya simge özel bir durum çubuğu bölümü için ayarlanacak. Denetim bölümü başarıyla ayarladıktan sonra otomatik olarak yeniden çizilir.

Aşağıdaki örnekte mevcut bir başlatır `CStatusBarCtrl` nesne (`m_StatusBarCtrl`) ile dört bölmeleri ve ardından ikinci bölümünde bir simge (IDI_ICON1) ve bazı metin ayarlar.

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

Modunu ayarlama hakkında daha fazla bilgi için bir `CStatusBarCtrl` basit, bkz: nesnesine [CStatusBarCtrl nesnesinin modunu ayarlama](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
