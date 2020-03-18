---
title: CStatusBarCtrl Ayarları
ms.date: 11/04/2016
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
ms.openlocfilehash: 18c4c780ecf7865d8d648bfa4c54961bbffe7b18
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446392"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl Ayarları

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) durum penceresinin varsayılan konumu üst pencerenin en altında bulunur, ancak CCS_TOP stilini üst pencerenin istemci alanının üst kısmında görünmesini sağlayabilirsiniz.

`CStatusBarCtrl` durum penceresinin sağ ucuna bir boyutlandırma tutamacı eklemek için SBARS_SIZEGRIP stilini belirtebilirsiniz. Boyutlandırma tutamacı boyutlandırma kenarlığına benzerdir; Bu, kullanıcının üst pencereyi yeniden boyutlandırmak için tıklave sürükleyebilmesini sağlayan dikdörtgen bir alandır.

> [!NOTE]
>  CCS_TOP ve SBARS_SIZEGRIP stillerini birleştirirseniz, sistem onu durum penceresine çizse bile, ortaya çıkan boyutlandırma tutamacı işlevsel değildir.

Durum penceresi için pencere yordamı otomatik olarak denetim penceresinin başlangıç boyutunu ve konumunu ayarlar. Genişlik, üst pencerenin istemci alanındayken de aynıdır. Yükseklik, şu anda durum penceresinin cihaz bağlamına ve pencere kenarlıklarının genişliğine seçili olan yazı tipinin ölçümlerine bağlıdır.

Pencere yordamı, her bir WM_SIZE ileti aldığında durum penceresinin boyutunu otomatik olarak ayarlar. Genellikle, ana pencerenin boyutu değiştiğinde, üst öğe durum penceresine bir WM_SIZE iletisi gönderir.

En küçük yüksekliği piksel cinsinden belirterek, bir durum penceresinin çizim alanının minimum yüksekliğini [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight)' ı çağırarak ayarlayabilirsiniz. Çizim alanı pencerenin kenarlıklarını içermez.

[Getkenarlýklarý](../mfc/reference/cstatusbarctrl-class.md#getborders)çağırarak bir durum penceresinin kenarlıklarının genişliklerini alırsınız. Bu üye işlevi, yatay kenarlığın genişliğini, dikey kenarlığı ve dikdörtgenler arasındaki kenarlığı alan üç öğeli bir diziye yönelik işaretçiyi içerir.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
