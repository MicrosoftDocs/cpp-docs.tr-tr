---
title: CStatusBarCtrl ayarları | Microsoft Docs
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
ms.openlocfilehash: 1dde1f005e53aff7ebe505d1ce619bf5c94410f8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955462"
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl Ayarları
Varsayılan konumu bir [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) durum penceresi penceresinin alt kısmındaki üst olmakla birlikte, üst pencerenin istemci alanının üstünde görünür için CCS_TOP stili belirtebilirsiniz.  
  
 Boyutlandırma tutamacı sağ ucunda içerecek şekilde SBARS_SIZEGRIP stili belirtebilirsiniz `CStatusBarCtrl` durum penceresi. Boyutlandırma tutamacı boyutlandırma kenarlık benzer; Bu, kullanıcı tıklayın ve ana pencereyi yeniden boyutlandırmak için sürükleyin dikdörtgen bir alandır.  
  
> [!NOTE]
>  CCS_TOP ve SBARS_SIZEGRIP stilleri birleştiriyorsanız, isteğe bağlı olarak sistem durumu penceresinde çizer olsa bile ortaya çıkan boyutlandırma tutamacı işlevsel değildir.  
  
 Pencere yordamı durum penceresi için ilk boyutunu ve konumunu denetimi penceresi otomatik olarak ayarlar. Genişliği üst pencerenin istemci alanının aynıdır. Yükseklik durum pencerenin cihaz bağlamına seçili yazı tipi ölçümleri ve pencere kenarlık genişliğini temel alır.  
  
 Bir WM_SIZE mesaj aldığı zaman pencere yordamı durum penceresi boyutunu otomatik olarak ayarlar. Genellikle, üst pencere boyutunu değiştiğinde üst durum penceresi WM_SIZE ileti gönderir.  
  
 Bir durum pencere çizim alanının en küçük yüksekliğini çağırarak ayarlayabileceğiniz [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), en küçük yükseklik piksel cinsinden belirtme. Çizim alanı pencerenin Kenarlıklar içermez.  
  
 Bir durum pencere kenarlık genişliklerini çağırarak alma [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Bu üye işlevi yatay kenarlık, Dikey kenarlık ve dikdörtgenler arasındaki kenarlığın genişliğini alır üç öğeli bir dizi işaretçisine içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

