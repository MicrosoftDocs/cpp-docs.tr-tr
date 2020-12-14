---
description: 'Daha fazla bilgi edinin: Ağaç Denetim öğesi etiketleri'
title: Ağaç Denetim Öğesi Etiketleri
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
ms.openlocfilehash: 62113a7534bf234ac8dde1154d5732bc29df8387
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264081"
---
# <a name="tree-control-item-labels"></a>Ağaç Denetim Öğesi Etiketleri

Öğeyi ağaç denetimine ([Ctreeck](../mfc/reference/ctreectrl-class.md)) eklerken genellikle bir öğenin etiketinin metnini belirtirsiniz. `InsertItem`Üye işlevi, etiketin metnini içeren bir dize da dahil olmak üzere öğenin özelliklerini tanımlayan bir [Tvidıtem](/windows/win32/api/commctrl/ns-commctrl-tvitemw) yapısını geçirebilir. `InsertItem` , çeşitli parametre birleşimleri ile çağrılabilen birkaç aşırı yükleme içerir.

Ağaç denetimi her öğeyi depolamak için bellek ayırır; öğe etiketlerinin metni, bu belleğin önemli bir bölümünü kaplar. Uygulamanız ağaç denetimindeki dizelerin bir kopyasını koruyorsa, gerçek dizeleri ağaç denetimine geçirmek yerine, ' ın *pszText* üyesinde **lpstr_textcallback** değerini `TV_ITEM` veya *lpszItem* parametresini belirterek denetimin bellek gereksinimlerini azaltabilirsiniz. **Lpstr_textcallback** kullanmak, ağaç denetiminin öğe yeniden çizilmesi gerektiğinde uygulamadan bir öğenin etiketinin metnini almasına neden olur. Ağaç denetimi, metni almak için bir [Nmtvdispınfo](/windows/win32/api/commctrl/ns-commctrl-nmtvdispinfow) yapısının adresini içeren [TVN_GETDISPINFO](/windows/win32/Controls/tvn-getdispinfo) bir bildirim iletisi gönderir. Dahil edilen yapının uygun üyelerini ayarlayarak yanıt vermelisiniz.

Ağaç denetimi, ağaç denetimini oluşturan işlemin yığınından ayrılan belleği kullanır. Bir ağaç denetimindeki en fazla öğe sayısı, yığında kullanılabilir bellek miktarına bağlıdır. Her öğe 64 bayt sürer.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
