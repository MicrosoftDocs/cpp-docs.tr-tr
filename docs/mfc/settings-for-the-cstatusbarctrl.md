---
description: 'Hakkında daha fazla bilgi edinin: CStatusBarCtrl için ayarlar'
title: CStatusBarCtrl Ayarları
ms.date: 11/04/2016
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
ms.openlocfilehash: 24790d387dde0ef5f452045cfe91ad2d39d48b35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217100"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl Ayarları

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) durum penceresinin varsayılan konumu üst pencerenin en altında bulunur, ancak CCS_TOP stilini üst pencerenin istemci alanının üst kısmında görünmesini sağlayabilirsiniz.

Durum penceresinin sağ ucuna bir boyutlandırma tutamacı eklemek için SBARS_SIZEGRIP stilini belirtebilirsiniz `CStatusBarCtrl` . Boyutlandırma tutamacı boyutlandırma kenarlığına benzerdir; Bu, kullanıcının üst pencereyi yeniden boyutlandırmak için tıklave sürükleyebilmesini sağlayan dikdörtgen bir alandır.

> [!NOTE]
> CCS_TOP ve SBARS_SIZEGRIP stillerini birleştirirseniz, sistem onu durum penceresine çizse bile, ortaya çıkan boyutlandırma tutamacı işlevsel değildir.

Durum penceresi için pencere yordamı otomatik olarak denetim penceresinin başlangıç boyutunu ve konumunu ayarlar. Genişlik, üst pencerenin istemci alanındayken de aynıdır. Yükseklik, şu anda durum penceresinin cihaz bağlamına ve pencere kenarlıklarının genişliğine seçili olan yazı tipinin ölçümlerine bağlıdır.

Pencere yordamı, her bir WM_SIZE ileti aldığında durum penceresinin boyutunu otomatik olarak ayarlar. Genellikle, ana pencerenin boyutu değiştiğinde, üst öğe durum penceresine bir WM_SIZE iletisi gönderir.

En küçük yüksekliği piksel cinsinden belirterek, bir durum penceresinin çizim alanının minimum yüksekliğini [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight)' ı çağırarak ayarlayabilirsiniz. Çizim alanı pencerenin kenarlıklarını içermez.

[Getkenarlýklarý](../mfc/reference/cstatusbarctrl-class.md#getborders)çağırarak bir durum penceresinin kenarlıklarının genişliklerini alırsınız. Bu üye işlevi, yatay kenarlığın genişliğini, dikey kenarlığı ve dikdörtgenler arasındaki kenarlığı alan üç öğeli bir diziye yönelik işaretçiyi içerir.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
