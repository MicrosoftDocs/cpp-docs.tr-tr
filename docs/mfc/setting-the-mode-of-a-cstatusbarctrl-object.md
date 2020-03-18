---
title: CStatusBarCtrl Nesnesinin Modunu Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
ms.openlocfilehash: 79b499533196447898ce62ea9dc86c1674fc0302
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446396"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl Nesnesinin Modunu Ayarlama

`CStatusBarCtrl` nesnesi için iki mod vardır: basit ve basit olmayan. Çoğu durumda, durum çubuğu denetimizin bir veya daha fazla parçaya, metin ve belki de bir simge ya da simgeye sahip olacaktır. Bu, basit olmayan mod olarak adlandırılır. Bu mod hakkında daha fazla bilgi için bkz. [CStatusBarCtrl nesnesinin parçalarını başlatma](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).

Ancak, yalnızca tek satırlık bir metin görüntülemesi gereken durumlar vardır. Bu durumda, basit mod gereksinimleriniz için yeterlidir. `CStatusBarCtrl` nesnesinin modunu basit olarak değiştirmek için [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) üye işlevine bir çağrı yapın. Durum çubuğu denetimi basit moddayken, *nPane* parametresinin değeri olarak 255 geçirerek `SetText` üye işlevini çağırarak metni ayarlayın.

`CStatusBarCtrl` nesnesinin hangi moda olduğunu belirlemek için [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) işlevini kullanabilirsiniz.

> [!NOTE]
>  Durum çubuğu nesnesi basit olmayan veya basit olmayan bir şekilde değiştirilirse, pencere hemen yeniden çizilir ve varsa, tanımlanan tüm parçalar otomatik olarak geri yüklenir.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
