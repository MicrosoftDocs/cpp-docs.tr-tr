---
title: Ağaç Denetim Öğesi Etiketleri
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
ms.openlocfilehash: d1f7fb8b558ff4726f7787cbf355a059fbcce8b5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513383"
---
# <a name="tree-control-item-labels"></a>Ağaç Denetim Öğesi Etiketleri

Öğeyi ağaç denetimine ([Ctreeck](../mfc/reference/ctreectrl-class.md)) eklerken genellikle bir öğenin etiketinin metnini belirtirsiniz. Üye işlevi, etiketin metnini içeren bir dize da dahil olmak üzere öğenin özelliklerini tanımlayan bir [tvidıtem](/windows/win32/api/commctrl/ns-commctrl-tvitemw) yapısını geçirebilir. `InsertItem` `InsertItem`, çeşitli parametre birleşimleri ile çağrılabilen birkaç aşırı yükleme içerir.

Ağaç denetimi her öğeyi depolamak için bellek ayırır; öğe etiketlerinin metni, bu belleğin önemli bir bölümünü kaplar. Uygulamanız, ağaç denetimindeki dizelerin bir kopyasını koruyorsa, **lpstr_textcallback** değerini ya da *lpszItem* ' nin `TV_ITEM` *pszText* üyesinde belirterek denetimin bellek gereksinimlerini azaltabilirsiniz. gerçek dizeleri ağaç denetimine geçirmek yerine parametresi. **Lpstr_textcallback** kullanmak, ağaç denetiminin öğe yeniden çizilmesi gerektiğinde uygulamadan bir öğenin etiketinin metnini almasına neden olur. Metin almak için ağaç denetimi bir [Nmtvdispınfo](/windows/win32/api/commctrl/ns-commctrl-tvdispinfow) yapısının adresini Içeren bir [TVN_GETDISPINFO](/windows/win32/Controls/tvn-getdispinfo) bildirim iletisi gönderir. Dahil edilen yapının uygun üyelerini ayarlayarak yanıt vermelisiniz.

Ağaç denetimi, ağaç denetimini oluşturan işlemin yığınından ayrılan belleği kullanır. Bir ağaç denetimindeki en fazla öğe sayısı, yığında kullanılabilir bellek miktarına bağlıdır. Her öğe 64 bayt sürer.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
