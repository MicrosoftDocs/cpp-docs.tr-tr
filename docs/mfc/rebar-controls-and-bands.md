---
description: 'Daha fazla bilgi edinin: Rebar denetimleri ve bantları'
title: Rebar Denetimleri ve Bantları
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
ms.openlocfilehash: 27ada3633a560ad8b5852b05bdd6330a0936fb99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248573"
---
# <a name="rebar-controls-and-bands"></a>Rebar Denetimleri ve Bantları

Bir Rebar denetiminin ana amacı, alt pencere, ortak iletişim kutusu denetimleri, menüler, araç çubukları vb. için bir kapsayıcı görevi görür. Bu içerme bir "bant" kavramı tarafından desteklenir. Her bir çubuk bandı bir kavrayıcı çubuğunun, bir bit eşlemin, bir metin etiketinin ve bir alt pencerenin herhangi bir birleşimini içerebilir.

Sınıfında `CReBarCtrl` , belirli bir çubuk bandı için bilgileri almak ve işlemek için kullanabileceğiniz birçok üye işlevi vardır:

- [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) Yeniden çubuk denetimindeki geçerli bantların sayısını alır.

- [Getbanınfo](../mfc/reference/crebarctrl-class.md#getbandinfo) Belirtilen bantdan alınan bilgilerle **Rebarbanınfo** yapısını başlatır. Karşılık gelen bir [Setbanınfo](../mfc/reference/crebarctrl-class.md#setbandinfo) üye işlevi vardır.

- [GetRect](../mfc/reference/crebarctrl-class.md#getrect) Belirtilen bantın sınırlayıcı dikdörtgenini alır.

- [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) Bir Rebar denetimindeki bant satır sayısını alır.

- [Idtoindex](../mfc/reference/crebarctrl-class.md#idtoindex) Belirtilen bir bandın dizinini alır.

- [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) Bir bantın kenarlıklarını alır.

Düzenlemeye ek olarak, belirli bir çubuk bantlarla çalışabilme sağlayan birkaç üye işlevi sağlanır.

[InsertBand](../mfc/reference/crebarctrl-class.md#insertband) ve [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) yeniden çubuk bantları ekleyin ve kaldırın. [Minimum izeband](../mfc/reference/crebarctrl-class.md#minimizeband) ve [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) , belirli bir yeniden çubuk bantın geçerli boyutunu etkiler. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) , belirli bir yeniden çubuk bantın dizinini değiştirir. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) , kullanıcıdan bir çubuk bandı gösterir veya gizler.

Aşağıdaki örnek, varolan bir yeniden çubuk denetimine (*m_wndReBar*) bir araç çubuğu bandı (*m_wndToolBar*) eklemeyi gösterir. Bant, `rbi` yapıyı başlatarak ve ardından `InsertBand` üye işlevi çağırarak açıklanır:

[!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
