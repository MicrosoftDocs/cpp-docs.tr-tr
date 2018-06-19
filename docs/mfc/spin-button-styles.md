---
title: Döndür düğmesi stilleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96b559fcda4825aec71ba4b5c1dd8c3cd319b83d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380103"
---
# <a name="spin-button-styles"></a>Döndür Düğmesi Stilleri
Değer değiştirme düğmesi ayarlarını birçok ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) stilleri tarafından denetlenir. Kullanarak aşağıdaki stiller ayarlayabilirsiniz **özellikleri** iletişim kutusu Düzenleyicisi penceresinde.  
  
-   **Yönlendirme** dikey veya yatay. Ok düğmelerini yönünü denetler. İle ilişkili `UDS_HORZ` stili.  
  
-   **Hizalama** eklenmemiş, sol veya sağ biri. Değer değiştirme düğmesi konumunu kontrol eder. Sol ve sağ değer değiştirme düğmesi yanındaki arkadaş penceresi getirin. Değer değiştirme düğmesi uyum sağlayacak şekilde arkadaş penceresinin genişliğini azalır. İle ilişkili `UDS_ALIGNLEFT` ve `UDS_ALIGNRIGHT` stilleri.  
  
-   **Arkadaş otomatik** otomatik olarak değer değiştirme düğmesi arkadaş penceresine olarak Z-sırası önceki pencere seçer. Bir iletişim şablonunu, değer değiştirme düğmesi sekme sırası önündeki denetimi budur. İle ilişkili `UDS_AUTOBUDDY` stili.  
  
-   **Arkadaş tamsayı ayarlamak** artırmak ve geçerli konumu değiştikçe arkadaş penceresinin başlık azaltma döndürme denetimi neden olur. İle ilişkili `UDS_SETBUDDYINT` stili.  
  
-   **Hiçbir binlerce** binlerce eklemez arkadaş penceresinin başlık değerindeki ayırıcı. İle ilişkili `UDS_NOTHOUSANDS` stili.  
  
    > [!NOTE]
    >  Arkadaş denetimden tamsayı değeri almak için iletişim kutusu veri değişimi (DDX) kullanmak istiyorsanız, bu stili ayarlayın. `DDX_Text` Katıştırılmış binlik basamak ayırıcıları kabul etmiyor.  
  
-   **Kaydırma** "değer artırılır veya indirildiği denetimi aralığının dışında olduğundan sarmalamak için" konumunu neden olur. İle ilişkili `UDS_WRAP` stili.  
  
-   **Ok tuşları** artırın veya yukarı ve aşağı ok tuşları basıldığında konumu azaltma değer değiştirme düğmesi neden olur. İle ilişkili `UDS_ARROWKEYS` stili.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSpinButtonCtrl kullanma](../mfc/using-cspinbuttonctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

