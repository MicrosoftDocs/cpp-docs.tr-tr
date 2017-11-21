---
title: "Sık kullanılan tuş ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d0e801e19329b712feeeff945d382beb6025b2d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setting-a-hot-key"></a>Sık Kullanılan Tuş Ayarlama
Uygulamanızı bir kısayol tuşu tarafından sağlanan bilgileri kullanabilirsiniz ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) iki yoldan biriyle denetimi:  
  
-   Bir nonchild penceresi göndererek etkinleştirmek için genel sık kullanılan tuş ayarlama bir [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) etkinleştirilmesi için pencere ileti.  
  
-   Windows işlevini çağırarak iş parçacığına özgü sık kullanılan tuş ayarlamak [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHotKeyCtrl kullanma](../mfc/using-chotkeyctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

