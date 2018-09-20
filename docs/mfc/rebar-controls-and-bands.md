---
title: Rebar denetimleri ve bantları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 988b16bb58462b42b8d4412a821cfc3fac5b4878
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443988"
---
# <a name="rebar-controls-and-bands"></a>Rebar Denetimleri ve Bantları

Rebar denetimiyle ana amacı, alt pencereler, ortak iletişim kutusu denetimleri, menüler, araç çubukları ve benzeri için kapsayıcı olarak davranır sağlamaktır. Bu kapsama bir "bant." kavramı tarafından desteklenir Her çubuk barınağı bant kavrayıcı çubuğu, bir bit eşlem, bir metin etiketi ve alt pencere herhangi bir birleşimini içerebilir.

Sınıf `CReBarCtrl` almak için kullanın ve işlemek, bilgi belirli çubuk barınağı bant için birçok üye işlevleri vardır:

- [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) rebar denetiminde geçerli bantları sayısını alır.

- [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) başlatan bir **REBARBANDINFO** belirtilen bant bilgileriyle yapısı. Var olan bir karşılık gelen [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) üye işlevi.

- [GetRect](../mfc/reference/crebarctrl-class.md#getrect) belirtilen bant sınırlayıcı dikdörtgenini alır.

- [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) bir rebar denetiminde bant satır sayısını alır.

- [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) belirtilen bant dizinini alır.

- [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) bir bant kenarlıklarını alır.

İşleme ek olarak, belirli rebar bantları üzerinde çalışmasına izin veren çeşitli üye işlevleri sağlanır.

[InsertBand](../mfc/reference/crebarctrl-class.md#insertband) ve [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) ekleyip rebar bantları kaldırabilirsiniz. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) ve [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) belirli çubuk barınağı bant geçerli boyutunu etkiler. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) belirli çubuk barınağı bant dizinini değiştirir. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) gösterir veya gizler kullanıcıdan bir çubuk barınağı bant.

Aşağıdaki örnek, bir araç çubuğu bant ekleme gösterir (*m_wndToolBar*) var olan bir çubuk barınağı denetimi (*m_wndReBar*). Bant başlatarak açıklanan `rbi` yapısı ve ardından arama `InsertBand` üye işlevi:

[!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

