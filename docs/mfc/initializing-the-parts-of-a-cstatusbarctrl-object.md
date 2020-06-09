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
ms.openlocfilehash: bd099a67d9f11cc3657a91b4141d3f18c6fa719d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621647"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>Bir CStatusBarCtrl Nesnesinin Bölümlerini Başlatma

Varsayılan olarak, bir durum çubuğunda ayrı bölmeler kullanılarak durum bilgileri görüntülenir. Bu bölmeler (parçalar olarak da adlandırılır) bir metin dizesi, bir simge veya her ikisini de içerebilir.

Durum çubuğunun kaç parçaya ve uzunluğuna sahip olacağını tanımlamak için [SetParts](reference/cstatusbarctrl-class.md#setparts) kullanın. Durum çubuğunun parçalarını oluşturduktan sonra, durum çubuğunun belirli bir bölümü için metin veya simgeyi ayarlamak üzere [SetText](reference/cstatusbarctrl-class.md#settext) ve [setIcon](reference/cstatusbarctrl-class.md#seticon) çağrıları yapın. Bölüm başarıyla ayarlandıktan sonra Denetim otomatik olarak yeniden çizilir.

Aşağıdaki örnek, `CStatusBarCtrl` dört bölme ile var olan bir nesneyi ( `m_StatusBarCtrl` ) başlatır ve ardından bir simge (IDI_ICON1) ve ikinci bölümde bazı metinleri ayarlar.

[!code-cpp[NVC_MFCControlLadenDialog#31](codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]

Bir nesnenin modunu basit olarak ayarlama hakkında daha fazla bilgi için `CStatusBarCtrl` , bkz. [CStatusBarCtrl nesnesinin modunu ayarlama](setting-the-mode-of-a-cstatusbarctrl-object.md).

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](using-cstatusbarctrl.md)<br/>
[Denetimler](controls-mfc.md)
