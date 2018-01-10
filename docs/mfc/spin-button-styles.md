---
title: "Döndür düğmesi stilleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fa4b2ae42175e2d4fc2ddb3317ef76b6b4dec8d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="spin-button-styles"></a>Döndür Düğmesi Stilleri
Değer değiştirme düğmesi ayarlarını birçok ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) stilleri tarafından denetlenir. Kullanarak aşağıdaki stiller ayarlayabilirsiniz **özellikleri** iletişim kutusu Düzenleyicisi penceresinde.  
  
-   **Yönlendirme** dikey veya yatay. Ok düğmelerini yönünü denetler. İle ilişkili `UDS_HORZ` stili.  
  
-   **Hizalama** eklenmemiş, sol veya sağ biri. Değer değiştirme düğmesi konumunu kontrol eder. Sol ve sağ değer değiştirme düğmesi yanındaki arkadaş penceresi getirin. Değer değiştirme düğmesi uyum sağlayacak şekilde arkadaş penceresinin genişliğini azalır. İle ilişkili `UDS_ALIGNLEFT` ve `UDS_ALIGNRIGHT` stilleri.  
  
-   **Arkadaş otomatik** otomatik olarak değer değiştirme düğmesi arkadaş penceresine olarak Z-sırası önceki pencere seçer. Bir iletişim şablonunu, değer değiştirme düğmesi sekme sırası önündeki denetimi budur. İle ilişkili `UDS_AUTOBUDDY` stili.  
  
-   **Arkadaş tamsayı ayarlamak** artırmak ve geçerli konumu değiştikçe arkadaş penceresinin başlık azaltma döndürme denetimi neden olur. İle ilişkili `UDS_SETBUDDYINT` stili.  
  
-   **Hiçbir binlerce** binlerce eklemez arkadaş penceresinin başlık değerindeki ayırıcı. İle ilişkili `UDS_NOTHOUSANDS` stili.  
  
    > [!NOTE]
    >  Arkadaş denetimden tamsayı değeri almak için iletişim kutusu veri değişimi (DDX) kullanmak istiyorsanız, bu stili ayarlayın. `DDX_Text`Katıştırılmış binlik basamak ayırıcıları kabul etmiyor.  
  
-   **Kaydırma** "değer artırılır veya indirildiği denetimi aralığının dışında olduğundan sarmalamak için" konumunu neden olur. İle ilişkili `UDS_WRAP` stili.  
  
-   **Ok tuşları** artırın veya yukarı ve aşağı ok tuşları basıldığında konumu azaltma değer değiştirme düğmesi neden olur. İle ilişkili `UDS_ARROWKEYS` stili.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSpinButtonCtrl kullanma](../mfc/using-cspinbuttonctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

