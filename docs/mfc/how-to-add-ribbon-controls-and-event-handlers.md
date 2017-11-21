---
title: "Nasıl yapılır: Şerit denetimleri ve olay işleyicileri ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7623a254e26cd7f1d09d7906fb4a9b192f46183e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme
Şerit denetimleri, düğmeler ve bölmeleri eklediğiniz birleşik giriş kutuları gibi öğelerdir. Paneller ilgili denetimleri bir grup görüntüleyen Şerit çubuğunun alanlarıdır.  
  
 Bu konuda, Şerit Tasarımcısı'nı açın, düğme ekleme ve "Hello World iletisini" gösteren bir olay bağlayın.  
  
### <a name="to-open-the-ribbon-designer"></a>Şerit Tasarımcısı açmak için  
  
1.  Visual Studio'da üzerinde **Görünüm** menüsünde tıklatın **kaynak görünümü**.  
  
2.  İçinde **kaynak görünümü**, tasarım yüzeyine görüntülemek için Şerit kaynağı çift tıklatın.  
  
### <a name="to-add-a-button-and-an-event-handler"></a>Bir düğmesi ve olay işleyicisi ekleme  
  
1.  Gelen **araç**, tıklatın **düğmesini** ve tasarım yüzeyine panelinde açın sürükleyin.  
  
2.  Düğmesine sağ tıklayın ve **olay işleyicisi ekleme**.  
  
3.  İçinde **olay işleyici Sihirbazı**, varsayılan ayarları onaylayın ve tıklatın **ekleme ve düzenleme**. Daha fazla bilgi için bkz: [olay işleyici Sihirbazı](../ide/event-handler-wizard.md).  
  
4.  Kod Düzenleyicisi'nde işleyici işlevdeki aşağıdaki kodu ekleyin:  
  
 ```  
    MessageBox((LPCTSTR)L"Hello World");

 ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [RibbonGadgets örnek: Şerit araçları uygulama](../visual-cpp-samples.md)   
 [Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

