---
title: "CStatusBarCtrl kullanarak CStatusBarCtrl nesnesi oluşturma | Microsoft Docs"
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
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cf62df91b2952240e460c722c46c0221fb491227
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-cstatusbarctrl-to-create-a-cstatusbarctrl-object"></a>CStatusBarCtrl Kullanarak CStatusBarCtrl Nesnesi Oluşturma
İşte bir örnek, tipik kullanımını [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### <a name="to-use-a-status-bar-control-with-parts"></a>Durum çubuğu denetimi bölümleri ile kullanmak için  
  
1.  Oluşturmak `CStatusBarCtrl` nesnesi.  
  
2.  Çağrı [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight) durum çubuğu denetimi için en küçük yükseklik ayarlamak istiyorsanız alanı çizim.  
  
3.  Çağrı [SetBkColor](../mfc/reference/cstatusbarctrl-class.md#setbkcolor) durum çubuğu denetim arka plan rengini ayarlamak için.  
  
4.  Çağrı [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) durum çubuğu denetim ve her bölümü sağ köşesine koordinatını bölümlerinin sayısını ayarlamak için.  
  
5.  Çağrı [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) metnini durum çubuğu denetimi belirli bir parçası ayarlamak için. İleti, yeni metin denetimi sonraki aldığında görüntülemek için neden değiştiğini denetim kısmı geçersiz kılar `WM_PAINT` ileti.  
  
 Bazı durumlarda, durum çubuğu, bir metin satırında görüntülemek yeterlidir. Bu durumda, çağırmaya [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple). Bu durum çubuğu denetimi tek satırlık metin görüntüler, "Basit" moduna geçirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

