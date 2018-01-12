---
title: "İlerleme denetimi için stiller | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6186372dc3ac8bc1000a71706971c9ff72078c5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="styles-for-the-progress-control"></a>İlerleme Denetimi için Stiller
Başlangıçta oluşturduğunuzda ilerleme durumu denetimini ([CProgressCtrl::Create](../mfc/reference/cprogressctrl-class.md#create)), kullanın `dwStyle` ilerleme durumunu denetlemek için istenen pencere stilleri belirtmek için parametre. Aşağıdaki listede, geçerli pencere stilleri Ayrıntılar verilmiştir. Burada listelenen dışındaki herhangi bir pencere stili denetimi yoksayar. Her zaman denetim iletişim kutusunun üst öğesi, genellikle alt pencere olarak oluşturmanız gerekir.  
  
|Pencere stili|Efekt|  
|------------------|------------|  
|`WS_BORDER`|Pencerenin çevresinde kenarlık oluşturur.|  
|**WS_CHILD**|Alt pencere oluşturur (her zaman için kullanılması gereken `CProgressCtrl`).|  
|**WS_CLIPCHILDREN**|Üst pencereye çizerken alt windows tarafından kapladığı alanı dışlar. Üst pencere oluşturduğunuzda kullanılır.|  
|**WS_CLIPSIBLINGS**|Alt pencereler birbirine kırpar.|  
|**WS_DISABLED**|Başlangıçta devre dışı bir pencere oluşturur.|  
|**WS_VISIBLE**|Başlangıçta görünür bir pencere oluşturur.|  
|**WS_TABSTOP**|Kullanıcı için taşımak için SEKME tuşuna bastığında denetimi odağı alabilir belirtir.|  
  
 Ayrıca, yalnızca ilerleme denetimi için geçerli iki stili belirtebilirsiniz `PBS_VERTICAL` ve `PBS_SMOOTH`.  
  
 Kullanım `PBS_VERTICAL` denetimi dikey yerine yatay olarak yönlendirmek için. Kullanım `PBS_SMOOTH` denetimi artımlı olarak doldurun küçük sonuçları kareler görüntüleme yerine denetimi tamamen doldurmak için.  
  
 Olmadan `PBS_SMOOTH` stili:  
  
 ![Standart ilerleme çubuğu stilini](../mfc/media/vc4ruw1.gif "vc4ruw1")  
  
 İle `PBS_SMOOTH` ve `PBS_VERTICAL` stilleri:  
  
 ![İlerleme, kesintisiz ve stili dikey](../mfc/media/vc4ruw2.gif "vc4ruw2")  
  
 Daha fazla bilgi için bkz: [pencere stilleri](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) içinde *MFC başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)

