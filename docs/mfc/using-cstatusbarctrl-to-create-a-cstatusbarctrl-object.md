---
title: CStatusBarCtrl kullanarak CStatusBarCtrl nesnesi oluşturma | Microsoft Docs
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
- status bar controls [MFC], creating
- CStatusBarCtrl class [MFC], creating
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b7f322003a36d89927930c0a57fd060078755f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383025"
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
 [Denetimler](../mfc/controls-mfc.md)

