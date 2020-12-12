---
description: 'Hakkında daha fazla bilgi edinin: CStatusBarCtrl nesnesinin modunu ayarlama'
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
ms.openlocfilehash: 46a87c17c68059e1d12476f4963f159cd2915824
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217113"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl Nesnesinin Modunu Ayarlama

Bir nesne için iki mod vardır `CStatusBarCtrl` : basit ve basit olmayan. Çoğu durumda, durum çubuğu denetimizin bir veya daha fazla parçaya, metin ve belki de bir simge ya da simgeye sahip olacaktır. Bu, basit olmayan mod olarak adlandırılır. Bu mod hakkında daha fazla bilgi için bkz. [CStatusBarCtrl nesnesinin parçalarını başlatma](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md).

Ancak, yalnızca tek satırlık bir metin görüntülemesi gereken durumlar vardır. Bu durumda, basit mod gereksinimleriniz için yeterlidir. Nesnenin modunu basit olarak değiştirmek için `CStatusBarCtrl` [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) üye işlevine bir çağrı yapın. Durum çubuğu denetimi basit moddayken, `SetText` *nPane* parametresinin değeri olarak 255 geçirerek üye işlevini çağırarak metni ayarlayın.

Nesnenin hangi moda olduğunu belirlemek için [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) işlevini kullanabilirsiniz `CStatusBarCtrl` .

> [!NOTE]
> Durum çubuğu nesnesi basit olmayan veya basit olmayan bir şekilde değiştirilirse, pencere hemen yeniden çizilir ve varsa, tanımlanan tüm parçalar otomatik olarak geri yüklenir.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
