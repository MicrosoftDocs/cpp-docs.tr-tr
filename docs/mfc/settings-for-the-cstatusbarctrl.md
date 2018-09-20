---
title: Cstatusbarctrl ayarları | Microsoft Docs
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
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2411659e6ae33fe9ce81d508d3e7c206b1e5b113
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440036"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl Ayarları

Varsayılan konumu bir [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) durum penceresi, pencerenin üst, ancak ana pencerenin istemci alanının üstünde görünen için CCS_TOP stili belirtebilirsiniz.

Boyutlandırma tutamacı doğru sonuna eklenecek SBARS_SIZEGRIP stili belirtebilirsiniz `CStatusBarCtrl` durum penceresi. Boyutlandırma tutamacı için boyutlandırma kenarlığı benzer. Bu kullanıcı,'a tıklayın ve ana pencereyi yeniden boyutlandırmak için sürükleyin dikdörtgen bir alandır.

> [!NOTE]
>  CCS_TOP ve SBARS_SIZEGRIP stilleri birleştirirseniz, isteğe bağlı olarak bir sistem durumu penceresinde çizer olsa da sonuç boyutlandırma tutamacı çalışmıyor.

Pencere yordamı için durum penceresi otomatik olarak başlangıç boyutu ve denetimi pencerenin konumunu ayarlar. Genişliği ana pencerenin istemci alanının aynıdır. Yükseklik durumu pencere cihaz bağlamına şu anda seçili yazı tipinin ölçümlere ilişkin ve pencerenin kenarlık genişliğini dayanır.

Her bir WM_SIZE ileti aldığında pencere yordamını durum penceresi boyutu otomatik olarak ayarlar. Genellikle, üst pencere boyutu değiştiğinde üst durum penceresi için WM_SIZE ileti gönderir.

Bir durum pencerenin çizim alanının en küçük yüksekliğini çağırarak ayarlayabilirsiniz [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), en küçük yüksekliğini piksel cinsinden belirtme. Çizim alanı pencerenin kenarlık içermez.

Bir durum pencere kenarlıklarını genişliğini çağırarak alma [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Bu üye işlevi, yatay kenarlık, Dikey kenarlık ve dikdörtgenler arasındaki kenarlığın genişliği alan üç öğeli bir dizi işaretçi içerir.

## <a name="see-also"></a>Ayrıca Bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

