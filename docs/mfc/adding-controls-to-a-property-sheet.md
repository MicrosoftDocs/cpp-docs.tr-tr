---
title: "Özellik sayfasına denetim ekleme | Microsoft Docs"
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
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2acbbed1a253a502aea8b19af6fd16ddb343e3ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-controls-to-a-property-sheet"></a>Özellik Sayfasına Denetim Ekleme
Varsayılan olarak, bir özellik sayfası özellik sayfaları, sekme dizini ve Uygula Tamam ve İptal düğmeleri penceresi alan ayırır. (Kalıcı olmayan özellik sayfası iptal edin ve düğmeleri uygulamak Tamam yok.) Özellik sayfasını, diğer denetimler ekleyebilirsiniz. Örneğin, kullanıcının geçerli ayarlarının dış nesneye uygulanan gibi görünür göstermek için özellik sayfası alanı sağındaki bir önizleme penceresi ekleyebilirsiniz.  
  
 Özellik sayfası iletişim kutusunda denetimleri ekleyebilirsiniz `OnCreate` işleyicisi. Ek denetimler genellikle kullanılan özellik sayfası iletişim kutusunun boyutunu genişletme gerektirir. Taban sınıfı çağrıldıktan sonra **CPropertySheet::OnCreate**, çağrı [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) genişlik ve yükseklik ayrılmış özellik sayfası penceresinin almak için dikdörtgenin genişletin boyutları ve çağrı [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) özellik sayfası pencere boyutunu değiştirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)   
 [CPropertyPage sınıfı](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet Sınıfı](../mfc/reference/cpropertysheet-class.md)
