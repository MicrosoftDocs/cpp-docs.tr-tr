---
title: Listesi Denetimini Yok Etme
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: 5004026da6bb309cc2c966384724b7b98e254e1d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508704"
---
# <a name="destroying-the-list-control"></a>Listesi Denetimini Yok Etme

[CListCtrl](../mfc/reference/clistctrl-class.md) nesnesini bir görünüm veya iletişim sınıfına ait bir veri üyesi olarak katıştırırsanız, sahibi yok edildiğinde yok edilir. [CListView](../mfc/reference/clistview-class.md)kullanırsanız, çerçeve, görünümü yok eder denetimi yok eder.

Liste denetimi yerine uygulamada depolanacak bazı liste verileri için düzenleme yaparsanız, onun ayırmayı kaldırma için düzenleme yapmanız gerekir. Daha fazla bilgi için bkz. Windows SDK [geri çağırma öğeleri ve geri çağırma maskesi](/windows/win32/Controls/using-list-view-controls) .

Ayrıca, oluşturduğunuz ve liste denetim nesnesiyle ilişkilendirdiğiniz herhangi bir görüntü listesini ayırmayı kaldırmaktan siz sorumlusunuz.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
