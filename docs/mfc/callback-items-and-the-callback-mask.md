---
title: Geri Çağrı Öğeleri ve Geri Çağrı Maskesi
ms.date: 11/04/2016
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
ms.openlocfilehash: 5c326d8498ea297936254a8650f666103ea3c772
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509142"
---
# <a name="callback-items-and-the-callback-mask"></a>Geri Çağrı Öğeleri ve Geri Çağrı Maskesi

Bir liste görünümü denetimi, öğelerinin her biri için genellikle etiket metnini, öğe simgelerinin resim listesi dizinini ve öğenin durumu için bir bit bayrakları kümesini depolar. Tek tek öğeleri geri arama öğesi olarak tanımlayabilir, bu, uygulamanız bir öğe için bazı bilgileri zaten depoladığında yararlı olur.

Bir `pszText` öğeyi, `iImage` `LVITEM` yapının üyeleri için uygun değerleri belirterek geri çağırma öğesi olarak tanımlarsınız (bkz. [clienstctrl:: GetItem](../mfc/reference/clistctrl-class.md#getitem)). Uygulama öğenin veya alt öğesinin metnini koruyorsa, `pszText` üye için **lpstr_textcallback** değerini belirtin. Uygulama, öğe için simgenin izini devam ederse, `iImage` üye için **I_IMAGECALLBACK** değerini belirtin.

Geri çağırma öğelerini tanımlamaya ek olarak, denetimin geri arama maskesini de değiştirebilirsiniz. Bu maske, uygulamanın denetim yerine geçerli verileri depoladığı öğe durumlarını belirten bir bit bayrakları kümesidir. Geri çağırma maskesi, belirli bir öğe için geçerli olan geri çağırma öğesi atamasının aksine tüm denetim öğeleri için geçerlidir. Geri çağırma maskesi varsayılan olarak sıfırdır, yani denetim tüm öğe durumlarını izler. Bu varsayılan davranışı değiştirmek için maskeyi aşağıdaki değerlerin herhangi bir birleşimine başlatın:

- **LVIS_CUT** Öğe, kes ve yapıştır işlemi için işaretlenir.

- **LVIS_DROPHILITED** Öğe, sürükle ve bırak hedefi olarak vurgulanır.

- **LVIS_FOCUSED** Öğenin odağı vardır.

- **LVIS_SELECTED** Öğe seçildi.

- **LVIS_OVERLAYMASK** Uygulama, her öğe için geçerli kaplama görüntüsünün görüntü listesi dizinini depolar.

- **LVIS_STATEIMAGEMASK** Uygulama, her öğe için geçerli durum görüntüsünün görüntü listesi dizinini depolar.

Bu maskeyi alma ve ayarlama hakkında daha fazla bilgi için, bkz. [CListCtrl:: GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) ve [CListCtrl:: SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
