---
title: "Özellik sayfasına denetim ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5623f95a77710e0ffbfa8a444de6f569f24105e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-controls-to-a-property-sheet"></a>Özellik Sayfasına Denetim Ekleme
Varsayılan olarak, bir özellik sayfası özellik sayfaları, sekme dizini ve Uygula Tamam ve İptal düğmeleri penceresi alan ayırır. (Kalıcı olmayan özellik sayfası iptal edin ve düğmeleri uygulamak Tamam yok.) Özellik sayfasını, diğer denetimler ekleyebilirsiniz. Örneğin, kullanıcının geçerli ayarlarının dış nesneye uygulanan gibi görünür göstermek için özellik sayfası alanı sağındaki bir önizleme penceresi ekleyebilirsiniz.  
  
 Özellik sayfası iletişim kutusunda denetimleri ekleyebilirsiniz `OnCreate` işleyicisi. Ek denetimler genellikle kullanılan özellik sayfası iletişim kutusunun boyutunu genişletme gerektirir. Taban sınıfı çağrıldıktan sonra **CPropertySheet::OnCreate**, çağrı [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) genişlik ve yükseklik ayrılmış özellik sayfası penceresinin almak için dikdörtgenin genişletin boyutları ve çağrı [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) özellik sayfası pencere boyutunu değiştirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)   
 [CPropertyPage sınıfı](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet sınıfı](../mfc/reference/cpropertysheet-class.md)
