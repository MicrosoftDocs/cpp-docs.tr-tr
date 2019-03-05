---
title: Listesi Denetimini Yok Etme
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
ms.openlocfilehash: 963da9e6db2f0fe063dee1ca19ab23f545ed5e76
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326718"
---
# <a name="destroying-the-list-control"></a>Listesi Denetimini Yok Etme

Eklerseniz, [CListCtrl](../mfc/reference/clistctrl-class.md) bunu edildiğinde sahibi kaldırıldığında görünümü veya iletişim kutusu sınıfı veri üyesi olarak nesnesi. Kullanıyorsanız bir [CListView](../mfc/reference/clistview-class.md), Görünüm yok eder, framework denetim yok eder.

Liste denetimi yerine uygulama depolanacak listesi verilerinizden bazıları için düzenleme, düzenleme, kaldırma için gerekecektir. Daha fazla bilgi için [geri çağrı öğeleri ve geri çağrı maskesi](/windows/desktop/Controls/using-list-view-controls) Windows SDK.

Ayrıca, oluşturduğunuz ve liste denetimi nesneyle ilişkili görüntü listeleri ayırmayı kaldırma için yükümlü olursunuz.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
