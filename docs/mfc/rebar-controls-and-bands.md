---
title: Rebar Denetimleri ve Bantları
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
ms.openlocfilehash: 4bb7b4aeab1478138aa2b52649f41ca943b5daa4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276071"
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

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
