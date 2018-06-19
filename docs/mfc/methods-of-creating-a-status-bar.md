---
title: Durum çubuğu oluşturma yöntemleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0428bfc906ba6e8a1ecc7bd7c198327e8c31505
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346935"
---
# <a name="methods-of-creating-a-status-bar"></a>Durum Çubuğu Oluşturma Yöntemleri
MFC durum çubukları oluşturmak için iki sınıflar sağlar: [CStatusBar](../mfc/reference/cstatusbar-class.md) ve [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (hangi sarmalar Windows ortak denetim API'si). `CStatusBar` tüm işlevleri sağlayan ortak denetim çubuğu durumunu, otomatik olarak menüleri ve araç çubuklarını ile etkileşim kurar ve, gerekli ortak denetim ayarlarını ve yapıları birçoğu sizin için; işleme Ancak, sonuçta elde edilen yürütülebilir dosyanın genellikle kullanılarak oluşturulan büyük olacaktır `CStatusBarCtrl`.  
  
 `CStatusBarCtrl` genellikle daha küçük bir yürütülebilir dosya ve sonuçları kullanmayı tercih edebilirsiniz `CStatusBarCtrl` MFC mimariye durum çubuğunun bütünleştirmek düşünmüyorsanız. Kullanmayı planlıyorsanız, `CStatusBarCtrl` ve durum çubuğu MFC mimariye tümleştirmek, durum çubuğu denetim işlemeleri MFC iletişim kurmak için ek dikkat edin gerekir. Bu iletişim zor değil; Ancak, kullandığınızda, gereksiz ek iş olduğu `CStatusBar`.  
  
 Visual C++ durum çubuğu ortak denetimi yararlanmak için iki yöntem sunar.  
  
-   Durum çubuğunda kullanarak oluşturmak `CStatusBar`ve ardından arama [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) erişmek için `CStatusBarCtrl` üye işlevleri.  
  
-   Durum çubuğunda kullanarak oluşturmak [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)'s Oluşturucusu.  
  
 Her iki yöntem durum çubuğu denetimi üye işlevleri için erişim sahibi olursunuz. Çağırdığınızda `CStatusBar::GetStatusBarCtrl`, bir başvuru döndürür bir `CStatusBarCtrl` ya da kümesi üye işlevlerini kullanabilmeniz için nesne. Bkz: [CStatusBar](../mfc/reference/cstatusbar-class.md) oluşturma ve bir durum kullanarak çubuğunda oluşturma hakkında bilgi için `CStatusBar`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStatusBarCtrl kullanma](../mfc/using-cstatusbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

