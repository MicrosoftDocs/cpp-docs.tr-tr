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
ms.openlocfilehash: 0be7a3da4582a80f3001a9bc951276c955191850
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957292"
---
# <a name="tree-control-item-states-overview"></a>Ağaç Denetim Öğesi Durumlarına Genel Bakış
Ağaç denetimi her öğe ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) geçerli durumuna sahiptir. Örneğin, bir öğe, devre dışı, genişletilmiş ve vb. seçilebilir. Çoğunlukla, ağaç denetimi otomatik olarak bir öğenin seçimini gibi kullanıcı eylemlerini yansıtacak şekilde öğenin durumunu ayarlar. Ancak, ayrıca bir öğenin durumu kullanarak ayarlayabilirsiniz [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) üye işlevini ve alma kullanarak bir öğe geçerli durumunu [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) üye işlevi. Öğesi durumları tam bir listesi için bkz: [ağaç görünümü denetim sabitleri](http://msdn.microsoft.com/library/windows/desktop/bb759985) Windows SDK'sındaki.  
  
 Bir öğenin geçerli durumu tarafından belirtilen *nDurum* parametresi. Ağaç denetimi, bir öğenin durumu öğeyi seçerek veya öğeye odak ayarlama gibi bir kullanıcı eylemi yansıtacak şekilde değiştirebilirsiniz. Ayrıca, bir uygulama, bir öğenin durumu öğesini gizlemek veya devre dışı bırakmak veya bir katmana veya durumu görüntüsüne belirtmek için değiştirebilirsiniz.  
  
 Belirttiğinizde veya öğenin durumunu değiştirme *nStateMask* parametresi, hangi durumunu ayarlamak için BITS belirtir ve *nDurum* parametresi bitlerinin için yeni değerleri içerir. Örneğin, aşağıdaki örnekte bir üst öğesi geçerli durumunu değiştirir (tarafından belirtilen *hParentItem*) içinde bir `CTreeCtrl` nesne (`m_treeCtrl`) için `TVIS_EXPANDPARTIAL`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]  
  
 Durumu değişikliğinin başka bir örnek, bir öğenin katmana resmi ayarlamak için olabilir. Bunu başarmak için *nStateMask* içermelidir `TVIS_OVERLAYMASK` değeri ve *nDurum* sekiz BITS kullanarak sol tabanlı gölgeye katmana görüntünün dizinini içermelidir [ INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) makrosu. Dizin yok katmana görüntüyü belirtmek için 0 olabilir. Katmana görüntü ağaç denetimin katmana görüntüleri listesine önceki bir çağrı tarafından eklenmiş olması gerekir [CImageList::SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) işlevi. İşlev eklemek için görüntü tabanlı dizinini belirtir; Bu INDEXTOOVERLAYMASK makrosu ile kullanılan dizindir. Ağaç denetimi en fazla dört katmana görüntüleri olabilir.  
  
 Bir öğenin durumu resmi ayarlamak için *nStateMask* içermelidir `TVIS_STATEIMAGEMASK` değeri ve *nDurum* 12 BITS kullanarak sol tabanlı gölgeye durumu görüntünün dizinini içermelidir [ INDEXTOSTATEIMAGEMASK](http://msdn.microsoft.com/library/windows/desktop/bb775597) makrosu. Dizin yok durumu görüntüyü belirtmek için 0 olabilir. Bir katmana ve durum görüntüleri hakkında daha fazla bilgi için bkz: [ağaç denetim görüntü listeleri](../mfc/tree-control-image-lists.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

