---
title: İlerleme denetimi için stiller | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b29d0df8342ce00a2ddb0d46970d9504a06edd8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956687"
---
# <a name="styles-for-the-progress-control"></a>İlerleme Denetimi için Stiller
Başlangıçta oluşturduğunuzda ilerleme durumu denetimini ([CProgressCtrl::Create](../mfc/reference/cprogressctrl-class.md#create)), kullanın *dwStyle* ilerleme durumunu denetlemek için istenen pencere stilleri belirtmek için parametre. Aşağıdaki listede, geçerli pencere stilleri Ayrıntılar verilmiştir. Burada listelenen dışındaki herhangi bir pencere stili denetimi yoksayar. Her zaman denetim iletişim kutusunun üst öğesi, genellikle alt pencere olarak oluşturmanız gerekir.  
  
|Pencere stili|Efekt|  
|------------------|------------|  
|WS_BORDER|Pencerenin çevresinde kenarlık oluşturur.|  
|WS_CHILD|Alt pencere oluşturur (her zaman için kullanılması gereken `CProgressCtrl`).|  
|WS_CLIPCHILDREN|Üst pencereye çizerken alt windows tarafından kapladığı alanı dışlar. Üst pencere oluşturduğunuzda kullanılır.|  
|WS_CLIPSIBLINGS|Alt pencereler birbirine kırpar.|  
|WS_DISABLED|Başlangıçta devre dışı bir pencere oluşturur.|  
|WS_VISIBLE|Başlangıçta görünür bir pencere oluşturur.|  
|WS_TABSTOP|Kullanıcı için taşımak için SEKME tuşuna bastığında denetimi odağı alabilir belirtir.|  
  
 Ayrıca, yalnızca ilerleme denetimi için geçerli iki stili pbs_vertıcal ve PBS_SMOOTH belirtebilirsiniz.  
  
 Pbs_vertıcal denetimi dikey yerine yatay olarak yönlendirmek için kullanın. Denetim artımlı olarak doldurun küçük sonuçları kareler görüntüleme yerine denetimi tamamen doldurmak için PBS_SMOOTH kullanın.  
  
 PBS_SMOOTH stili:  
  
 ![Standart ilerleme çubuğu stilini](../mfc/media/vc4ruw1.gif "vc4ruw1")  
  
 PBS_SMOOTH ve pbs_vertıcal stili ile:  
  
 ![İlerleme, kesintisiz ve stili dikey](../mfc/media/vc4ruw2.gif "vc4ruw2")  
  
 Daha fazla bilgi için bkz: [pencere stilleri](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) içinde *MFC başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)

