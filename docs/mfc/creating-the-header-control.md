---
title: Üstbilgi Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
ms.openlocfilehash: fdb96eee243214d053a8f375f742cf69aa4e512d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568488"
---
# <a name="creating-the-header-control"></a>Üstbilgi Denetimi Oluşturma

Üstbilgi denetimi (bir üstbilgi denetimi içeren bir liste denetimini ekleyebiliyor olmanıza rağmen) doğrudan iletişim kutusu Düzenleyicisi'nde kullanılabilir değil.

### <a name="to-put-a-header-control-in-a-dialog-box"></a>Üstbilgi denetimi bir iletişim kutusuna yerleştirin

1. El ile türündeki üye değişkeni ekleme [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) iletişim sınıfınızdaki.

1. İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), oluşturun ve stillerini ayarlama `CHeaderCtrl`konumlandırın ve görüntüleyin.

1. Üstbilgi denetimine öğe ekleyin.

1. Özellikler penceresinde, herhangi bir üstbilgi denetimi bildirim iletileri için iletişim kutusu sınıfı işleyici işlevleri eşleştirmek için gereken işlemek için kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Üstbilgi denetimi görünümünde (CListView değil) yerleştirmek için

1. Ekleme bir [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) nesnesi, görünüm sınıfı.

1. Stil, konumlandırma ve üst bilgi denetimi penceresi 's görüntülemek [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) üye işlevi.

1. Üstbilgi denetimine öğe ekleyin.

1. Özellikler penceresinde, herhangi bir üstbilgi denetimi bildirim iletileri için Görünüm sınıfı işleyici işlevleri eşleştirmek için gereken işlemek için kullanın (bkz [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md)).

Görünüm veya iletişim nesne oluşturulduğunda, her iki durumda da, katıştırılmış denetime nesnesi oluşturulur. Çağırmalısınız sonra [CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create) denetimi penceresi oluşturmak için. Denetim konumlandırmak için arama [CHeaderCtrl::Layout](../mfc/reference/cheaderctrl-class.md#layout) denetimin ilk boyutunu ve konumunu belirlemek için ve [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) istediğiniz konumu ayarlamak için. Daha sonra açıklandığı gibi öğeleri Ekle [üstbilgi denetimine öğe eklemeyi](../mfc/adding-items-to-the-header-control.md).

Daha fazla bilgi için [üstbilgi denetimi oluşturma](/windows/desktop/Controls/header-controls) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

