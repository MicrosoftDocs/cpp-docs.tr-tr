---
title: Geri çağrı öğeleri ve geri çağrı maskesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0711fccb142d9774c37f2cb2d8f576bf7fddd128
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422850"
---
# <a name="callback-items-and-the-callback-mask"></a>Geri Çağrı Öğeleri ve Geri Çağrı Maskesi

Her alt öğeleri için bir liste görünümü denetimi etiket metni, öğenin simgeler, görüntü listesi dizinini genellikle depolar ve öğenin durumu için bir dizi bit bayrakları. Uygulamanız zaten bazı öğenin bilgileri depoluyorsa yararlı olan geri çağrı öğeleri olarak tek tek öğeleri tanımlayabilirsiniz.

Bir öğe için uygun değerleri belirtilerek bir geri çağırma öğesi olarak tanımlamak `pszText` ve `iImage` üyeleri **LV_ITEM** yapısı (bkz [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)). Uygulama öğenin veya alt'ın metin tutuyorsa belirtin **LPSTR_TEXTCALLBACK** değerini `pszText` üyesi. Uygulamanın öğe için simge izler belirtebilmeniz **I_IMAGECALLBACK** değerini `iImage` üyesi.

Geri çağrı öğeleri tanımlanmasına ek olarak, denetimin geri çağrı maskesi de değiştirebilirsiniz. Bu maskesi için denetimi yerine, uygulamanın geçerli verileri depolayan öğesi durumları belirtin bit bayrakları kümesidir. Geri çağrı maskesi, belirli bir ögeye uygulanan geri çağırma öğesi atamasını aksine denetimin öğelerin tümünü uygular. Geri çağrı maskesi varsayılan olarak denetim tüm öğesi durumları izler anlamına gelen sıfırdır. Bu varsayılan davranışı değiştirmek için aşağıdaki değerlerden herhangi bir birleşimini maskeye başlatın:

- **LVIS_CUT** öğe kesme ve yapıştırma işlemi için işaretlenmiş.

- **LVIS_DROPHILITED** öğenin bir sürükleme ve bırakma hedefi olarak vurgulanır.

- **LVIS_FOCUSED** öğenin odağa sahip.

- **LVIS_SELECTED** öğe seçilir.

- **LVIS_OVERLAYMASK** uygulamayı her öğe için geçerli kaplama görüntünün görüntü listesi dizini depolar.

- **LVIS_STATEIMAGEMASK** uygulamayı geçerli durumu görüntünün her öğe için resim listesi dizinini depolar.

Alınıyor ve bu maskesini ayarlama hakkında daha fazla bilgi için bkz. [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) ve [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask).

## <a name="see-also"></a>Ayrıca Bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

