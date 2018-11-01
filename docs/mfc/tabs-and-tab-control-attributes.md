---
title: Sekme ve Sekme Denetimi Öznitelikleri
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
ms.openlocfilehash: ba63fdca32af28d0763dd4cf2da3465a99ddeb1f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571996"
---
# <a name="tabs-and-tab-control-attributes"></a>Sekme ve Sekme Denetimi Öznitelikleri

Görünümünü ve davranışını bir sekme denetimini oluşturan sekme üzerinde önemli ölçüde denetiminiz ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). Her sekme bir etiket, simge, öğesi durumu ve ilişkili bir uygulama tanımlı 32-bit değeri olabilir. Her sekme için simgeyi, etiketi veya her ikisini de görüntüleyebilirsiniz.

Ayrıca, her sekme öğesi üç durumda olabilir: basılı basılmamış ya da vurgulanır. Bu durum yalnızca var olan bir sekme öğesi değiştirerek ayarlanabilir. Var olan bir sekme öğesi değiştirmek için bir çağrı ile alma [GetItem](../mfc/reference/ctabctrl-class.md#getitem), değişiklik `TCITEM` yapısı (özellikle *dwState* ve *dwStateMask* veri üyesi ) ve ardından değiştirilmiş dönün `TCITEM` yapısı çağrısıyla [SetItem](../mfc/reference/ctabctrl-class.md#setitem). Tüm sekme öğeleri öğesi durumlarını temizlemek gereken bir `CTabCtrl` nesne, çağrı yapmak [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall). Bu işlev, tüm sekme öğeleri veya şu anda seçili dışındaki tüm öğeleri durumunu sıfırlar.

Aşağıdaki kod tüm sekmesini öğelerinin durumunu temizler ve ardından üçüncü öğe durumunu değiştirir:

[!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]

Sekme öznitelikleri hakkında daha fazla bilgi için bkz: [sekme ve sekme öznitelikleri](/windows/desktop/Controls/tab-controls) Windows SDK. Sekme denetimine sekmeler ekleme hakkında daha fazla bilgi için bkz. [Sekme denetimine sekmeler ekleme](../mfc/adding-tabs-to-a-tab-control.md) bu konuda.

## <a name="see-also"></a>Ayrıca Bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

