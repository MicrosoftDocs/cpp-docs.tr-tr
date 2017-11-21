---
title: "Durum çubuğu oluşturma yöntemleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f077c54902f69d181adbdfc8788f826f00239230
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="methods-of-creating-a-status-bar"></a>Durum Çubuğu Oluşturma Yöntemleri
MFC durum çubukları oluşturmak için iki sınıflar sağlar: [CStatusBar](../mfc/reference/cstatusbar-class.md) ve [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (hangi sarmalar Windows ortak denetim API'si). `CStatusBar`tüm işlevleri sağlayan ortak denetim çubuğu durumunu, otomatik olarak menüleri ve araç çubuklarını ile etkileşim kurar ve, gerekli ortak denetim ayarlarını ve yapıları birçoğu sizin için; işleme Ancak, sonuçta elde edilen yürütülebilir dosyanın genellikle kullanılarak oluşturulan büyük olacaktır `CStatusBarCtrl`.  
  
 `CStatusBarCtrl`genellikle daha küçük bir yürütülebilir dosya ve sonuçları kullanmayı tercih edebilirsiniz `CStatusBarCtrl` MFC mimariye durum çubuğunun bütünleştirmek düşünmüyorsanız. Kullanmayı planlıyorsanız, `CStatusBarCtrl` ve durum çubuğu MFC mimariye tümleştirmek, durum çubuğu denetim işlemeleri MFC iletişim kurmak için ek dikkat edin gerekir. Bu iletişim zor değil; Ancak, kullandığınızda, gereksiz ek iş olduğu `CStatusBar`.  
  
 Visual C++ durum çubuğu ortak denetimi yararlanmak için iki yöntem sunar.  
  
-   Durum çubuğunda kullanarak oluşturmak `CStatusBar`ve ardından arama [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) erişmek için `CStatusBarCtrl` üye işlevleri.  
  
-   Durum çubuğunda kullanarak oluşturmak [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)'s Oluşturucusu.  
  
 Her iki yöntem durum çubuğu denetimi üye işlevleri için erişim sahibi olursunuz. Çağırdığınızda `CStatusBar::GetStatusBarCtrl`, bir başvuru döndürür bir `CStatusBarCtrl` ya da kümesi üye işlevlerini kullanabilmeniz için nesne. Bkz: [CStatusBar](../mfc/reference/cstatusbar-class.md) oluşturma ve bir durum kullanarak çubuğunda oluşturma hakkında bilgi için `CStatusBar`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

