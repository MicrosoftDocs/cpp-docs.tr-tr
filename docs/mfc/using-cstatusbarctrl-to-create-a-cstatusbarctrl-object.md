---
title: CStatusBarCtrl kullanarak CStatusBarCtrl nesnesi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c68603eff0393d76af4e0617548e5bf1dd4aa63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413698"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>CStatusBarCtrl Kullanarak CStatusBarCtrl Nesnesi Oluşturma

İşte bir örnek tipik bir kullanımı [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):

### <a name="to-use-a-status-bar-control-with-parts"></a>Durum çubuğu denetimi bölümleri ile kullanmak için

1. Oluşturmak `CStatusBarCtrl` nesne.

1. Çağrı [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) alan çizim durum çubuğu denetimi için en küçük yükseklik ayarlamak istiyorsanız.

1. Çağrı [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) durum çubuğu denetiminin arka plan rengini ayarlamak için.

1. Çağrı [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) durum çubuğu denetimi ve her parça öğenin sağ kenarı koordinatını bölümlerinin sayısını ayarlamak için.

1. Çağrı [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) belirli bir durum çubuğu denetimi parçası metnini ayarlamak için. İleti, Denetim sonraki WM_PAINT iletisini aldığında, yeni metin görüntülemek için neden değiştiğini denetim bölümünü geçersiz kılar.

Bazı durumlarda, durum çubuğunda metin satırı görüntülemek yeterlidir. Bu durumda, çağrı yapmak [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple). Bu durum çubuğu denetimi tek satırlık metin görüntüleyen "Basit" moduna geçirir.

## <a name="see-also"></a>Ayrıca Bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

