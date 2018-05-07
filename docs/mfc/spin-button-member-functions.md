---
title: Döndür düğmesi üye işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 524863b816c62903cb610b57a6e3275bcdf6a3d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="spin-button-member-functions"></a>Döndür Düğmesi Üye İşlevleri
Birden fazla üye işlevleri döndürme denetimi için kullanılabilir ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Değer değiştirme düğmesi aşağıdaki özniteliklerini değiştirmek için bu işlevler kullanın.  
  
-   **Hızlandırma** aktarılma konumunu değiştirir kullanıcı aşağı ok düğmesi tuttuğunda hızını ayarlayabilirsiniz. Hızlandırma ile çalışmak için kullanın [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) ve [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) üye işlevleri.  
  
-   **Temel** arkadaş penceresinin başlık içindeki konumunu göstermek için kullanılan base (10 veya 16) değiştirebilirsiniz. Base ile çalışmak için kullanın [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) ve [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) üye işlevleri.  
  
-   **Dost penceresi** arkadaş penceresi dinamik olarak ayarlayabilirsiniz. Sorgu veya denetleyen arkadaş penceredir değiştirmek için kullanın [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) ve [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) üye işlevleri.  
  
-   **Konum** sorgulamak ve konumunu değiştirir. Doğrudan konumu ile çalışmak için kullanın [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) ve [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) üye işlevleri. Arkadaş denetimi resim yazısını (arkadaş düzenleme denetimi olduğunu örneğin durumda) değişmiş olabilir beri `GetPos` geçerli resim yazısını alır ve buna göre konumunu ayarlar.  
  
-   **Aralık** değer değiştirme düğmesi için maksimum ve minimum konumlarını değiştirebilirsiniz. Varsayılan olarak, en fazla 0 olarak ayarlayın ve en az 100'e ayarlayın. Varsayılan üst sınır en düşük varsayılan değerinden olduğundan, ok düğmelerini Eylemler counter-intuitive kalır. Genellikle, aralık kullanılarak ayarlanan [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) üye işlevi. Aralık kullanım sorgulamak için [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSpinButtonCtrl kullanma](../mfc/using-cspinbuttonctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

