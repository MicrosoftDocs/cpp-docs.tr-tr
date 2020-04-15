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
ms.openlocfilehash: e09a7bd274c44df2da48bbc007a95802fadd8cf0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365412"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl Nesnesinin Modunu Ayarlama

Bir `CStatusBarCtrl` nesne için iki mod vardır: basit ve basit olmayan. Çoğu durumda, durum çubuğu denetiminiz, metin ve belki de bir simge veya simgeyle birlikte bir veya daha fazla parçaya sahip olacaktır. Buna basit olmayan mod denir. Bu mod hakkında daha fazla bilgi için [CStatusBarCtrl Nesnesinin Bölümlerini Başlatma](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)konusuna bakın.

Ancak, yalnızca tek bir metin satırı görüntülemeniz gereken durumlar vardır. Bu durumda, basit mod ihtiyaçlarınız için yeterlidir. Nesnenin modunu `CStatusBarCtrl` basit olarak değiştirmek için [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) üye işlevini arayın. Durum çubuğu denetimi basit modda olduğunda, `SetText` metni üye işlevi çağırarak ve *nPane* parametresi değeri olarak 255'i geçerek ayarlayın.

Nesnenin hangi modda olduğunu belirlemek için IsSimple işlevini kullanabilirsiniz. [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) `CStatusBarCtrl`

> [!NOTE]
> Durum çubuğu nesnesi basit olmayandan basite veya tam tersi olarak değiştiriliyorsa, pencere hemen yeniden çizilir ve varsa tanımlı parçalar otomatik olarak geri yüklenir.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
