---
title: CStatusBarCtrl Ayarları
ms.date: 11/04/2016
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
ms.openlocfilehash: dd7c68d6721c48f751c04437e43c8770f6ec5736
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365372"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl Ayarları

[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) durum penceresinin varsayılan konumu üst pencerenin alt kısmındadır, ancak üst pencerenin istemci alanının üst kısmında görünmesi için CCS_TOP stilini belirtebilirsiniz.

`CStatusBarCtrl` Durum penceresinin sağ ucunda boyutlandırma kavrama eklemek için SBARS_SIZEGRIP stilini belirtebilirsiniz. Boyutlandırma kavrama, boyutlandırma sınırına benzer; kullanıcının üst pencereyi yeniden boyutlandırmak için tıklatıp sürükleyebileceği dikdörtgen bir alandır.

> [!NOTE]
> CCS_TOP ve SBARS_SIZEGRIP stilleri birleştirirseniz, sistem durum penceresinde çizer olsa bile ortaya çıkan boyutlandırma kavrama işlevsel değildir.

Durum penceresi için pencere yordamı, denetim penceresinin başlangıç boyutunu ve konumunu otomatik olarak ayarlar. Genişlik, üst pencerenin istemci alanıyla aynıdır. Yükseklik, durum penceresinin aygıt bağlamında ve pencerenin kenarlıklarının genişliğinde şu anda seçilen yazı tipinin ölçümlerine dayanır.

Pencere yordamı, WM_SIZE iletisi aldığında durum penceresinin boyutunu otomatik olarak ayarlar. Genellikle, üst pencerenin boyutu değiştiğinde, üst öğe durum penceresine WM_SIZE bir ileti gönderir.

Durum penceresinin çizim alanının minimum yüksekliğini, piksellerde minimum yüksekliği belirterek [SetMinHeight'ı](../mfc/reference/cstatusbarctrl-class.md#setminheight)arayarak ayarlayabilirsiniz. Çizim alanı pencerenin kenarlıklarını içermez.

GetBorders'ı arayarak durum penceresinin kenarlıklarının genişliklerini [alırsınız.](../mfc/reference/cstatusbarctrl-class.md#getborders) Bu üye işlev, yatay kenarlık, dikey kenarlık genişliği ve dikdörtgenler arasındaki kenarlık alan üç öğeli bir dizi işaretçiiçerir.

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
