---
title: "ATL ileti işleyicisi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4358dc54589971c559bec48adf77252d4f4cda28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-message-handler"></a>ATL ileti işleyicisi ekleme
İleti işleyicisi (Windows iletilerini işleme bir üye fonksiyonu) için bir denetim eklemek için öncelikle Sınıf Görünümü'nde denetimi seçin. Ardından açın **özellikleri** penceresinde, seçin **iletileri** simgesi ve aşağı açılan kontrol gerekli ileti ters kutusunda tıklatın. İleti işleyicisi için bir bildirim bu denetimin üstbilgi dosyası ve denetimin .cpp dosyasındaki işleyicisinin iskelet bir uygulama ekler. Ayrıca ileti eşlemesi eklemek ve işleyici için bir giriş ekleyin.  
  
 ATL içinde bir ileti işleyicisi ekleme bir MFC sınıfı için ileti işleyicisi ekleme ile benzerdir. Bkz: [MFC ileti işleyicisi ekleme](../mfc/reference/adding-an-mfc-message-handler.md) daha fazla bilgi için.  
  
 Yalnızca bir ATL ileti işleyicisi eklemek için aşağıdaki koşullar geçerlidir:  
  
-   İleti işleyicileri MFC olarak aynı adlandırma kuralını izler.  
  
-   Yeni ileti eşleme girdilerini ana ileti eşlemeye eklenir. Sihirbaz, diğer ileti eşlemeleri ve zincirleme tanımıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Uygulama](../atl/implementing-a-window.md)

