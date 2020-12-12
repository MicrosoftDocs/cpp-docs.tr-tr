---
description: 'Hakkında daha fazla bilgi edinin: liste denetimini yok etme'
title: Listesi Denetimini Yok Etme
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: b909889a6365de639f67359859641af6e2bc6525
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327828"
---
# <a name="destroying-the-list-control"></a>Listesi Denetimini Yok Etme

[CListCtrl](reference/clistctrl-class.md) nesnesini bir görünüm veya iletişim sınıfına ait bir veri üyesi olarak katıştırırsanız, sahibi yok edildiğinde yok edilir. [CListView](reference/clistview-class.md)kullanırsanız, çerçeve, görünümü yok eder denetimi yok eder.

Liste denetimi yerine uygulamada depolanacak bazı liste verileri için düzenleme yaparsanız, onun ayırmayı kaldırma için düzenleme yapmanız gerekir. Daha fazla bilgi için bkz. Windows SDK [geri çağırma öğeleri ve geri çağırma maskesi](/windows/win32/Controls/using-list-view-controls) .

Ayrıca, oluşturduğunuz ve liste denetim nesnesiyle ilişkilendirdiğiniz herhangi bir görüntü listesini ayırmayı kaldırmaktan siz sorumlusunuz.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
