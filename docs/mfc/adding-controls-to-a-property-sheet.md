---
title: Özellik sayfasına denetim ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8437fcdaa04ce7dd2b0a214e4bd3a63ca421d014
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341097"
---
# <a name="adding-controls-to-a-property-sheet"></a>Özellik Sayfasına Denetim Ekleme
Varsayılan olarak, bir özellik sayfası özellik sayfaları, sekme dizini ve Uygula Tamam ve İptal düğmeleri penceresi alan ayırır. (Kalıcı olmayan özellik sayfası iptal edin ve düğmeleri uygulamak Tamam yok.) Özellik sayfasını, diğer denetimler ekleyebilirsiniz. Örneğin, kullanıcının geçerli ayarlarının dış nesneye uygulanan gibi görünür göstermek için özellik sayfası alanı sağındaki bir önizleme penceresi ekleyebilirsiniz.  
  
 Özellik sayfası iletişim kutusunda denetimleri ekleyebilirsiniz `OnCreate` işleyicisi. Ek denetimler genellikle kullanılan özellik sayfası iletişim kutusunun boyutunu genişletme gerektirir. Taban sınıfı çağrıldıktan sonra **CPropertySheet::OnCreate**, çağrı [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) genişlik ve yükseklik ayrılmış özellik sayfası penceresinin almak için dikdörtgenin genişletin boyutları ve çağrı [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) özellik sayfası pencere boyutunu değiştirmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)   
 [CPropertyPage sınıfı](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet Sınıfı](../mfc/reference/cpropertysheet-class.md)
