---
title: ATL ileti işleyicisi ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e79598b79ccbad13ad98c7fc1284808fe1b05cfc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354162"
---
# <a name="adding-an-atl-message-handler"></a>ATL ileti işleyicisi ekleme
İleti işleyicisi (Windows iletilerini işleme bir üye fonksiyonu) için bir denetim eklemek için öncelikle Sınıf Görünümü'nde denetimi seçin. Ardından açın **özellikleri** penceresinde, seçin **iletileri** simgesi ve aşağı açılan kontrol gerekli ileti ters kutusunda tıklatın. İleti işleyicisi için bir bildirim bu denetimin üstbilgi dosyası ve denetimin .cpp dosyasındaki işleyicisinin iskelet bir uygulama ekler. Ayrıca ileti eşlemesi eklemek ve işleyici için bir giriş ekleyin.  
  
 ATL içinde bir ileti işleyicisi ekleme bir MFC sınıfı için ileti işleyicisi ekleme ile benzerdir. Bkz: [MFC ileti işleyicisi ekleme](../mfc/reference/adding-an-mfc-message-handler.md) daha fazla bilgi için.  
  
 Yalnızca bir ATL ileti işleyicisi eklemek için aşağıdaki koşullar geçerlidir:  
  
-   İleti işleyicileri MFC olarak aynı adlandırma kuralını izler.  
  
-   Yeni ileti eşleme girdilerini ana ileti eşlemeye eklenir. Sihirbaz, diğer ileti eşlemeleri ve zincirleme tanımıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Uygulama](../atl/implementing-a-window.md)

