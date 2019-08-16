---
title: Ağaç Denetim Öğesi Durumlarına Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
ms.openlocfilehash: bbeabf69f174fcf172808ff71f07ed05f1dc9675
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511045"
---
# <a name="tree-control-item-states-overview"></a>Ağaç Denetim Öğesi Durumlarına Genel Bakış

Ağaç denetimindeki her öğenin ([Ctreeci](../mfc/reference/ctreectrl-class.md)) geçerli bir durumu vardır. Örneğin, bir öğe seçilebilir, devre dışı bırakılabilir, Genişletilebilir, vb. Çoğu bölümde, ağaç denetimi bir öğenin durumunu, bir öğenin seçimi gibi kullanıcı eylemlerini yansıtacak şekilde otomatik olarak ayarlar. Ancak, [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) üye işlevini kullanarak bir öğenin durumunu ayarlayabilir ve [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) üye işlevini kullanarak bir öğenin geçerli durumunu alabilirsiniz. Öğe durumlarının tam listesi için, Windows SDK [ağaç görünümü Denetim sabitleri](/windows/win32/Controls/tree-view-control-item-states) ' ne bakın.

Bir öğenin geçerli durumu *nState* parametresi tarafından belirtilir. Ağaç denetimi bir öğenin durumunu bir kullanıcı eylemini yansıtacak şekilde değiştirebilir (öğeyi seçme veya odağı öğe olarak ayarlama gibi). Ayrıca, bir uygulama öğeyi devre dışı bırakmak veya gizlemek ya da bir kaplama görüntüsü ya da durum görüntüsü belirtmek için bir öğenin durumunu değiştirebilir.

Bir öğenin durumunu belirttiğinizde veya değiştirirken, *nStateMask* parametresi ayarlanacak durum bitlerini belirtir ve *nState* parametresi bu bitlerin yeni değerlerini içerir. Örneğin, aşağıdaki örnek bir `CTreeCtrl` `m_treeCtrl` `TVIS_EXPANDPARTIAL`nesne () içinde bir üst öğenin ( *hparentidıtem*tarafından belirtilen) geçerli durumunu değiştirir:

[!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]

Durumu değiştirmenin başka bir örneği de bir öğenin yer paylaşımı görüntüsünü ayarlamak olacaktır. Bunu gerçekleştirmek için, *nStateMask* `TVIS_OVERLAYMASK` değeri içermelidir ve *nState* [dizintooverlaymask](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask) makrosunu kullanarak sol sekiz biti kaydırılan kaplama resminin tek tabanlı dizinini içermelidir. Dizin, hiçbir kaplama görüntüsü belirtmek için 0 olabilir. Kaplama resminin, bir önceki [CImageList:: SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) işlevine yapılan bir çağrı tarafından ağaç denetiminin kaplama görüntülerinin listesine eklenmiş olması gerekir. İşlevi, eklenecek görüntünün tek tabanlı dizinini belirtir; Bu dizin ıNDEXTOOVERLAYMASK makrosu ile kullanılır. Ağaç denetiminde en fazla dört kaplama görüntüsü bulunabilir.

Bir öğenin durum görüntüsünü ayarlamak için *nStateMask* `TVIS_STATEIMAGEMASK` değeri içermelidir ve *nState* , [INDEXTOSTATEIMAGEMASK](/windows/win32/api/commctrl/nf-commctrl-indextostateimagemask) makrosunu kullanarak sol 12 bite kaydırılan durum görüntüsünün tek tabanlı dizinini içermelidir. Dizin, durum görüntüsü olmadığını belirtmek için 0 olabilir. Kaplama ve durum görüntüleri hakkında daha fazla bilgi için bkz. [Ağaç Denetim görüntü listeleri](../mfc/tree-control-image-lists.md).

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
