---
description: 'Daha fazla bilgi edinin: sekmeler ve sekme denetimi öznitelikleri'
title: Sekme ve Sekme Denetimi Öznitelikleri
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
ms.openlocfilehash: 9b79e2ae6558d812fa96d0b62c07eb1c41176ee5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216359"
---
# <a name="tabs-and-tab-control-attributes"></a>Sekme ve Sekme Denetimi Öznitelikleri

Sekme denetimi ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) oluşturan sekmelerin görünümü ve davranışı üzerinde önemli bir denetiminiz vardır. Her sekmenin bir etiketi, simge, öğe durumu ve onunla ilişkili uygulama tanımlı 32 bitlik bir değeri olabilir. Her sekme için simgeyi, etiketi veya her ikisini de görüntüleyebilirsiniz.

Ayrıca, her sekme öğesi üç olası duruma sahip olabilir: basıldığında, geri basılmış veya vurgulanmış. Bu durum, yalnızca varolan bir sekme öğesi değiştirilerek ayarlanabilir. Var olan bir sekme öğesini değiştirmek için, bir [GetItem](../mfc/reference/ctabctrl-class.md#getitem)çağrısıyla birlikte alın, `TCITEM` yapıyı değiştirin (özellikle *dwState* ve *dwStateMask* veri üyeleri) ve sonra değiştirilmiş `TCITEM` yapıyı [SetItem](../mfc/reference/ctabctrl-class.md#setitem)çağrısıyla döndürün. Bir nesnedeki tüm sekme öğelerinin öğe durumlarını temizlemeniz gerekiyorsa `CTabCtrl` , [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall)öğesine çağrı yapın. Bu işlev, tüm sekme öğelerinin veya seçili olanı hariç tüm öğelerin durumunu sıfırlar.

Aşağıdaki kod, tüm sekme öğelerinin durumunu temizler ve ardından üçüncü öğenin durumunu değiştirir:

[!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]

Sekme öznitelikleri hakkında daha fazla bilgi için Windows SDK [Sekmeler ve sekme öznitelikleri](/windows/win32/Controls/tab-controls) bölümüne bakın. Sekme denetimine sekmeler ekleme hakkında daha fazla bilgi için, bu konunun ilerleyen kısımlarında [Sekme denetimine sekme ekleme](../mfc/adding-tabs-to-a-tab-control.md) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
