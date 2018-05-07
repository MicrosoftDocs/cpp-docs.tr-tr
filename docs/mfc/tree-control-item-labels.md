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
ms.openlocfilehash: 598dca9f0d5f394a8e742c1b886588eab3518bf4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-labels"></a>Ağaç Denetim Öğesi Etiketleri
Genellikle bir öğenin etiket metnini ağaç denetim öğesi eklerken, belirttiğiniz ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). `InsertItem` Üye işlevi iletebilir bir [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) etiket metnini içeren bir dize gibi öğenin özelliklerini tanımlayan yapısı. `InsertItem` parametre çeşitli birleşimleri çağrılabilir birçok aşırı yüklemeye sahip.  
  
 Ağaç denetimi her öğe depolamak için bellek ayırır; öğe etiketleri metin bu bellek önemli bir kısmını alır. Uygulamanızı bir kopyasını ağaç denetimi dizelerde koruyorsa, belirterek denetimi bellek gereksinimlerini düşürebilir **LPSTR_TEXTCALLBACK** değeri **pszText** üyesi`TV_ITEM` veya `lpszItem` gerçek dizeleri ağaç denetimi geçirme yerine parametre. Kullanarak **LPSTR_TEXTCALLBACK** öğe çizilmesi gerektiğinde uygulamadan öğenin etiket metnini almak ağaç denetimi neden olur. Ağaç denetimi metni almak gönderir bir [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) adresini içeren bildirim iletisi bir [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) yapısı. Dahil edilen yapısı uygun üyeleri ayarlayarak yanıtlaması gerekir.  
  
 Ağaç denetimi ağaç denetimi oluşturur işlem yığınından ayrılan bellek kullanır. Ağaç denetimindeki öğeleri sayısının yığınında kullanılabilir bellek miktarını temel alır. Her öğe 64 bayt alır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

