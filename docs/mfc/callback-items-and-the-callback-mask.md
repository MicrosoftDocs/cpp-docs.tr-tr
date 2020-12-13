---
description: 'Daha fazla bilgi edinin: geri çağırma öğeleri ve geri çağrı maskesi'
title: Geri Çağrı Öğeleri ve Geri Çağrı Maskesi
ms.date: 11/04/2016
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
ms.openlocfilehash: 0740afbee61f3173e2005fd927982c94786f03f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339767"
---
# <a name="callback-items-and-the-callback-mask"></a>Geri Çağrı Öğeleri ve Geri Çağrı Maskesi

Bir liste görünümü denetimi, öğelerinin her biri için genellikle etiket metnini, öğe simgelerinin resim listesi dizinini ve öğenin durumu için bir bit bayrakları kümesini depolar. Tek tek öğeleri geri arama öğesi olarak tanımlayabilir, bu, uygulamanız bir öğe için bazı bilgileri zaten depoladığında yararlı olur.

Bir öğeyi, yapının üyeleri için uygun değerleri belirterek geri çağırma öğesi olarak tanımlarsınız `pszText` `iImage` `LVITEM` (bkz. [Clienstctrl:: GetItem](reference/clistctrl-class.md#getitem)). Uygulama öğenin veya alt öğesinin metnini koruyorsa, üyenin **lpstr_textcallback** değerini belirtin `pszText` . Uygulama, öğe için simgenin izini devam ederse, üyenin **I_IMAGECALLBACK** değerini belirtin `iImage` .

Geri çağırma öğelerini tanımlamaya ek olarak, denetimin geri arama maskesini de değiştirebilirsiniz. Bu maske, uygulamanın denetim yerine geçerli verileri depoladığı öğe durumlarını belirten bir bit bayrakları kümesidir. Geri çağırma maskesi, belirli bir öğe için geçerli olan geri çağırma öğesi atamasının aksine tüm denetim öğeleri için geçerlidir. Geri çağırma maskesi varsayılan olarak sıfırdır, yani denetim tüm öğe durumlarını izler. Bu varsayılan davranışı değiştirmek için maskeyi aşağıdaki değerlerin herhangi bir birleşimine başlatın:

- **LVIS_CUT** Öğe, kes ve yapıştır işlemi için işaretlenir.

- **LVIS_DROPHILITED** Öğe, sürükle ve bırak hedefi olarak vurgulanır.

- **LVIS_FOCUSED** Öğenin odağı vardır.

- **LVIS_SELECTED** Öğe seçildi.

- **LVIS_OVERLAYMASK** Uygulama, her öğe için geçerli kaplama görüntüsünün görüntü listesi dizinini depolar.

- **LVIS_STATEIMAGEMASK** Uygulama, her öğe için geçerli durum görüntüsünün görüntü listesi dizinini depolar.

Bu maskeyi alma ve ayarlama hakkında daha fazla bilgi için, bkz. [CListCtrl:: GetCallbackMask](reference/clistctrl-class.md#getcallbackmask) ve [CListCtrl:: SetCallbackMask](reference/clistctrl-class.md#setcallbackmask).

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
