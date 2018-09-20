---
title: Ağaç denetim öğesi durumlarına genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3c14c24c7dc35ced74d2ae86bae4f19ce331ed1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404905"
---
# <a name="tree-control-item-states-overview"></a>Ağaç Denetim Öğesi Durumlarına Genel Bakış

Ağaç denetimindeki her bir öğe ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) geçerli durumuna sahiptir. Örneğin, bir öğe, devre dışı, genişletilmiş ve bu şekilde seçilebilir. Çoğunlukla, ağaç denetimi, bir öğenin durumu, bir öğenin seçimi gibi kullanıcı eylemlerini yansıtacak şekilde otomatik olarak ayarlar. Ancak, aynı zamanda bir öğenin durumu kullanarak ayarlayabilirsiniz [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) üye işlevine ve Al kullanarak bir öğe geçerli durumunu [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) üye işlevi. Öğesi durumları tam bir listesi için bkz. [ağaç görünümü denetimi sabitleri](/windows/desktop/Controls/tree-view-control-item-states) Windows SDK.

Bir öğenin geçerli durumu tarafından belirtilen *nDurum* parametresi. Ağaç denetimi, bir öğenin durumu öğeyi seçerek veya öğesine odak ayarlama gibi bir kullanıcı eylemi yansıtacak şekilde değiştirebilirsiniz. Ayrıca, bir uygulama, bir öğenin durumu devre dışı bırakın veya öğeyi gizleme veya bir katmana veya durumu görüntüsüne belirtmek için değiştirebilirsiniz.

Belirttiğinizde veya bir öğenin durum değişikliği *nStateMask* parametresinin belirttiği ayarlamak için hangi durumu bitleri ve *nDurum* parametresi bu bitleri için yeni değerler içerir. Örneğin, aşağıdaki örnek, bir üst öğesi geçerli durumunu değiştirir (tarafından belirtilen *hParentItem*) içinde bir `CTreeCtrl` nesne (`m_treeCtrl`) için `TVIS_EXPANDPARTIAL`:

[!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]

Bir öğenin katmana resmi ayarlama durumu değiştirmenin başka bir örnek olacaktır. Bunu gerçekleştirmek için *nStateMask* içermelidir `TVIS_OVERLAYMASK` değeri ve *nDurum* sekiz BITS kullanarak sola bir tabanlı kaydırılacak katmana görüntünün dizinini içermelidir [ INDEXTOOVERLAYMASK](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask) makrosu. Dizin yok katmana görüntüyü belirtmek için 0 olabilir. Katmana görüntü ağaç denetimin katmana görüntüleri listesine önceki bir çağrı tarafından eklenmiş olmanız [CImageList::SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) işlevi. İşlev eklemek için resmi bir tabanlı dizinini belirtir. Bu INDEXTOOVERLAYMASK makro kullanılan dizinidir. Ağaç denetimi en fazla dört katmana görüntüleri olabilir.

Bir öğenin durumu resmi ayarlanacak *nStateMask* içermelidir `TVIS_STATEIMAGEMASK` değeri ve *nDurum* 12 BITS kullanarak sol tabanlı dizin kaydırılacak durum resminin içermelidir [ INDEXTOSTATEIMAGEMASK](/windows/desktop/api/commctrl/nf-commctrl-indextostateimagemask) makrosu. Dizin yok durumu görüntüyü belirtmek için 0 olabilir. Katman ve durum görüntüleri hakkında daha fazla bilgi için bkz. [ağaç denetim görüntü listeleri](../mfc/tree-control-image-lists.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

