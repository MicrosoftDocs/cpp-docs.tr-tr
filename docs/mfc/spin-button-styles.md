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
ms.openlocfilehash: 223b7e0875a5382edf5f4d350c9343d117768c41
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953784"
---
# <a name="spin-button-styles"></a>Döndür Düğmesi Stilleri
Değer değiştirme düğmesi ayarlarını birçok ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) stilleri tarafından denetlenir. Kullanarak aşağıdaki stiller ayarlayabilirsiniz **özellikleri** iletişim kutusu Düzenleyicisi penceresinde.  
  
-   **Yönlendirme** dikey veya yatay. Ok düğmelerini yönünü denetler. UDS_HORZ stili ile ilişkilendirilmiş.  
  
-   **Hizalama** eklenmemiş, sol veya sağ biri. Değer değiştirme düğmesi konumunu kontrol eder. Sol ve sağ değer değiştirme düğmesi yanındaki arkadaş penceresi getirin. Değer değiştirme düğmesi uyum sağlayacak şekilde arkadaş penceresinin genişliğini azalır. UDS_ALIGNLEFT ve UDS_ALIGNRIGHT stilleri ile ilişkilendirilmiş.  
  
-   **Arkadaş otomatik** otomatik olarak değer değiştirme düğmesi arkadaş penceresine olarak Z-sırası önceki pencere seçer. Bir iletişim şablonunu, değer değiştirme düğmesi sekme sırası önündeki denetimi budur. UDS_AUTOBUDDY stili ile ilişkilendirilmiş.  
  
-   **Arkadaş tamsayı ayarlamak** artırmak ve geçerli konumu değiştikçe arkadaş penceresinin başlık azaltma döndürme denetimi neden olur. UDS_SETBUDDYINT stili ile ilişkilendirilmiş.  
  
-   **Hiçbir binlerce** binlerce eklemez arkadaş penceresinin başlık değerindeki ayırıcı. UDS_NOTHOUSANDS stili ile ilişkilendirilmiş.  
  
    > [!NOTE]
    >  Arkadaş denetimden tamsayı değeri almak için iletişim kutusu veri değişimi (DDX) kullanmak istiyorsanız, bu stili ayarlayın. `DDX_Text` Katıştırılmış binlik basamak ayırıcıları kabul etmiyor.  
  
-   **Kaydırma** "değer artırılır veya indirildiği denetimi aralığının dışında olduğundan sarmalamak için" konumunu neden olur. UDS_WRAP stili ile ilişkilendirilmiş.  
  
-   **Ok tuşları** artırın veya yukarı ve aşağı ok tuşları basıldığında konumu azaltma değer değiştirme düğmesi neden olur. UDS_ARROWKEYS stili ile ilişkilendirilmiş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSpinButtonCtrl kullanma](../mfc/using-cspinbuttonctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

