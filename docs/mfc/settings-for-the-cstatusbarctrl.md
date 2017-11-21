---
title: "CStatusBarCtrl ayarları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CStatusBarCtrl
dev_langs: C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a7065d234fa9d57d1a4b3f97f38464b530b0561f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl Ayarları
Varsayılan konumu bir [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) durum penceredir pencerenin üst ancak belirtebilirsiniz `CCS_TOP` üst pencerenin istemci alanının üstünde görünür için stili.  
  
 Belirleyebileceğiniz **SBARS_SIZEGRIP** sağ ucunda boyutlandırma tutamacı dahil etmek için stil `CStatusBarCtrl` durum penceresi. Boyutlandırma tutamacı boyutlandırma kenarlık benzer; Bu, kullanıcı tıklayın ve ana pencereyi yeniden boyutlandırmak için sürükleyin dikdörtgen bir alandır.  
  
> [!NOTE]
>  Birleştiriyorsanız `CCS_TOP` ve **SBARS_SIZEGRIP** stiller, sonuçta elde edilen boyutlandırma tutamacı işlevsel değildir rağmen isteğe bağlı olarak sistem durumu penceresinde çizer.  
  
 Pencere yordamı durum penceresi için ilk boyutunu ve konumunu denetimi penceresi otomatik olarak ayarlar. Genişliği üst pencerenin istemci alanının aynıdır. Yükseklik durum pencerenin cihaz bağlamına seçili yazı tipi ölçümleri ve pencere kenarlık genişliğini temel alır.  
  
 Pencere yordamı aldığı zaman, otomatik olarak durum penceresi boyutunu ayarlar bir `WM_SIZE` ileti. Genellikle, üst pencere boyutunu değiştiğinde, üst gönderir bir `WM_SIZE` durum penceresi ileti.  
  
 Bir durum pencere çizim alanının en küçük yüksekliğini çağırarak ayarlayabileceğiniz [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), en küçük yükseklik piksel cinsinden belirtme. Çizim alanı pencerenin Kenarlıklar içermez.  
  
 Bir durum pencere kenarlık genişliklerini çağırarak alma [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Bu üye işlevi yatay kenarlık, Dikey kenarlık ve dikdörtgenler arasındaki kenarlığın genişliğini alır üç öğeli bir dizi işaretçisine içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

