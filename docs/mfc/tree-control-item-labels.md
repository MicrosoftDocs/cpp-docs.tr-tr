---
title: Ağaç denetim öğesi etiketleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f07032a203761e78bd44f40456093eae9a84d07
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399892"
---
# <a name="tree-control-item-labels"></a>Ağaç Denetim Öğesi Etiketleri

Genellikle bir öğenin etiket metnini öğesi ağaç denetimine eklerken belirttiğiniz ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). `InsertItem` Üye işlevine geçirebilirsiniz bir [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) etiketin metni içeren bir dize dahil olmak üzere, öğenin özelliklerini tanımlayan yapısını. `InsertItem` çeşitli birleşimlerini parametreleri ile çağrılabilen birçok aşırı yüklemeye sahip.

Ağaç denetimi, her öğe depolamak için bellek ayırır; öğe etiketleri, metni bu bellek önemli bir kısmını alır. Uygulamanızı ağaç denetimindeki dizelerini kopyasını tutar, belirterek denetimin bellek gereksinimlerini azaltabilirsiniz **LPSTR_TEXTCALLBACK** değerini *pszText* üyesi`TV_ITEM` veya *lpszItem* gerçek dizeleri için ağaç denetimi geçirmek yerine parametre. Kullanarak **LPSTR_TEXTCALLBACK** öğeyi yeniden çizilmesi gerektiğinde uygulamadan bir öğenin etiket metnini almak ağaç denetimi neden olur. Ağaç denetimi metni almak için gönderen bir [TVN_GETDISPINFO](/windows/desktop/Controls/tvn-getdispinfo) adresini içeren bildirim iletisi bir [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) yapısı. Uygun üyeleri dahil yapısı ayarlayarak yanıt vermesi gerekir.

Ağaç denetimi ağaç denetimi oluşturan işlem yığından ayrılan bellek kullanır. Ağaç denetimindeki öğeler sayısı yığında kullanılabilir bellek miktarını temel alır. Her öğe 64 baytın alır.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

