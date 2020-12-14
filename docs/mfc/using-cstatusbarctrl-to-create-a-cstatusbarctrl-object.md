---
description: 'Hakkında daha fazla bilgi edinin: CStatusBarCtrl nesnesi oluşturmak için CStatusBarCtrl kullanma'
title: CStatusBarCtrl Kullanarak CStatusBarCtrl Nesnesi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
ms.openlocfilehash: 0b76065ce4e90600bdec7e4f4a89ee2c5bb14085
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202385"
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>CStatusBarCtrl Kullanarak CStatusBarCtrl Nesnesi Oluşturma

Tipik bir [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)kullanımı örneği aşağıda verilmiştir:

### <a name="to-use-a-status-bar-control-with-parts"></a>Bir durum çubuğu denetimini bölümlerle birlikte kullanmak için

1. Nesnesini oluşturun `CStatusBarCtrl` .

1. Durum çubuğu denetiminin çizim alanının minimum yüksekliğini ayarlamak istiyorsanız [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) öğesini çağırın.

1. Durum çubuğu denetiminin arka plan rengini ayarlamak için [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) çağırın.

1. Bir durum çubuğu denetimindeki parça sayısını ve her parçanın sağ kenarının koordinatını ayarlamak için [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) öğesini çağırın.

1. Durum çubuğu denetiminin belirli bir bölümünde metni ayarlamak için [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) çağrısı yapın. İleti, denetimin bir sonraki WM_PAINT iletisini aldığı zaman yeni metni görüntülemesine neden olan denetimin bölümünü geçersiz kılar.

Bazı durumlarda, durum çubuğunun yalnızca bir metin satırı görüntülemesi gerekir. Bu durumda, [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)çağrısı yapın. Bu, durum çubuğu denetimini, tek satırlık bir metin görüntüleyen "basit" moda koyar.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
