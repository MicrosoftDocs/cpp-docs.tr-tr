---
title: CToolBarCtrl Nesnesi Oluşturma
ms.date: 11/04/2016
f1_keywords:
- CToolBarCtrl
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: ad75f346e21262b894d01efd351e6bb0a3ede3a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564677"
---
# <a name="creating-a-ctoolbarctrl-object"></a>CToolBarCtrl Nesnesi Oluşturma

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesneleri içeren birkaç iç veri yapılarını — listesini düğmesine görüntü bit eşlem düğmesi etiketi dizelerinin listesini ve listesini `TBBUTTON` yapılarına —, görüntü ilişkilendirmek ve/veya konum, stil, durumu, dize ve düğmenin komut kimliği. Bu veri yapılarının öğelerin her biri sıfır tabanlı bir dizin adlandırılır. Kullanabilmeniz için önce bir `CToolBarCtrl` nesnesi, bu veri yapıları ayarlamanız gerekir. Veri yapıları listesi için bkz. [araç çubuğu denetimleri](controls-mfc.md) Windows SDK. Dizeleri listesini yalnızca düğme etiketleri için kullanılabilir; araç çubuğundan dizeleri alınamıyor.

Kullanılacak bir `CToolBarCtrl` nesnesi, genellikle şu adımları izleyin:

### <a name="to-use-a-ctoolbarctrl-object"></a>CToolBarCtrl nesnesi kullanmak için

1. Oluşturmak [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) nesne.

1. Çağrı [Oluştur](../mfc/reference/ctoolbarctrl-class.md#create) Windows araç çubuğu ortak denetim oluşturma ve buna eklemek için `CToolBarCtrl` nesne. Bit eşlem resimleri için düğmeler istiyorsanız, düğme bit eşlemleri araç çubuğuna çağırarak eklemek [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap). Düğmeleri için dize etiketlerini istiyorsanız, dizeleri araç çubuğuna çağırarak eklemek [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) ve/veya [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings). Arama sonra `AddString` ve/veya `AddStrings`, çağırmalısınız [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) dize veya dizeler görünmesini alabilmek için.

1. Düğme yapıları çağırarak araç çubuğuna ekleme [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons).

1. Araç ipuçları istiyorsanız işlemek **TTN_NEEDTEXT** açıklandığı gibi araç çubuğunun sahibi penceresinde iletileri [araç ipucu bildirimlerini işleme](../mfc/handling-tool-tip-notifications.md).

1. Kullanıcı araç çubuğunu özelleştirme yapmak istiyorsanız, sahip penceresine özelleştirme bildirim iletilerini açıklandığı işlemek [özelleştirme bildirimlerini işleme](../mfc/handling-customization-notifications.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

