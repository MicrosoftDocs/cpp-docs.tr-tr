---
title: Bir CStatusBarCtrl Nesnesinin Bölümlerini Başlatma
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
ms.openlocfilehash: a5b65a2bbb68eaa7058f3514bb95a5209a0e5e71
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444455"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinin Bölümlerini Başlatma

Varsayılan olarak, bir durum çubuğunda ayrı bölmeler kullanılarak durum bilgileri görüntülenir. Bu bölmeler (parçalar olarak da adlandırılır) bir metin dizesi, bir simge veya her ikisini de içerebilir.

Durum çubuğunun kaç parçaya ve uzunluğuna sahip olacağını tanımlamak için [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) kullanın. Durum çubuğunun parçalarını oluşturduktan sonra, durum çubuğunun belirli bir bölümü için metin veya simgeyi ayarlamak üzere [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) ve [setIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) çağrıları yapın. Bölüm başarıyla ayarlandıktan sonra Denetim otomatik olarak yeniden çizilir.

Aşağıdaki örnek, dört bölme ile var olan bir `CStatusBarCtrl` nesnesini (`m_StatusBarCtrl`) başlatır ve ardından bir simge (IDI_ICON1) ve ikinci bölümde bir metin belirler.

[!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

`CStatusBarCtrl` nesnesinin modunu basit olarak ayarlama hakkında daha fazla bilgi için, bkz. [CStatusBarCtrl nesnesinin modunu ayarlama](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
