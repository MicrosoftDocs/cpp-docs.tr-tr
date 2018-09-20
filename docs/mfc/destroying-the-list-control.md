---
title: Listesi denetimini yok etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25642357e3dd9117ae2817307ed5fa3c4a0921d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424551"
---
# <a name="destroying-the-list-control"></a>Listesi Denetimini Yok Etme

Eklerseniz, [CListCtrl](../mfc/reference/clistctrl-class.md) bunu edildiğinde sahibi kaldırıldığında görünümü veya iletişim kutusu sınıfı veri üyesi olarak nesnesi. Kullanıyorsanız bir [CListView](../mfc/reference/clistview-class.md), Görünüm yok eder, framework denetim yok eder.

Liste denetimi yerine uygulama depolanacak listesi verilerinizden bazıları için düzenleme, düzenleme, kaldırma için gerekecektir. Daha fazla bilgi için [geri çağrı öğeleri ve geri çağrı maskesi](/windows/desktop/Controls/using-list-view-controls) Windows SDK.

Ayrıca, oluşturduğunuz ve liste denetimi nesneyle ilişkili görüntü listeleri ayırmayı kaldırma için yükümlü olursunuz.

## <a name="see-also"></a>Ayrıca Bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

