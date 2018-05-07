---
title: Araç çubuğu oluşturma yöntemleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 052f1578386746f9a4d9892576f09b3b61547289
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="methods-of-creating-a-toolbar"></a>Araç Çubuğu Oluşturma Yöntemleri
MFC araç çubukları oluşturmak için iki sınıflar sağlar: [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (hangi sarmalar Windows ortak denetim API'si). `CToolBar` Tüm araç ortak denetim işlevselliğini sağlar ve, gerekli ortak denetim ayarlarını ve yapıları birçoğu sizin için; işleme Ancak, sonuçta elde edilen yürütülebilir dosyanın genellikle kullanılarak oluşturulan büyük olacaktır `CToolBarCtrl`.  
  
 `CToolBarCtrl` genellikle daha küçük bir yürütülebilir dosya ve sonuçları kullanmayı tercih edebilirsiniz `CToolBarCtrl` MFC mimariye araç çubuğunun bütünleştirmek düşünmüyorsanız. Kullanmayı planlıyorsanız, `CToolBarCtrl` ve MFC mimariye araç tümleştirmek, MFC araç çubuğu denetimi işlemeleri iletişim kurmak için ek dikkat edin gerekir. Bu iletişim zor değil; Ancak, kullandığınızda, gereksiz ek iş olduğu `CToolBar`.  
  
 Visual C++ araç yaygın bir denetim yararlanmak için iki yöntem sunar.  
  
-   Araç çubuğunu kullanarak oluşturmak `CToolBar`ve ardından arama [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl) erişmek için `CToolBarCtrl` üye işlevleri.  
  
-   Araç çubuğunu kullanarak oluşturmak [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)'s Oluşturucusu.  
  
 Her iki yöntem araç çubuğu denetimi üye işlevleri için erişim sahibi olursunuz. Çağırdığınızda `CToolBar::GetToolBarCtrl`, bir başvuru döndürür bir `CToolBarCtrl` ya da kümesi üye işlevlerini kullanabilmeniz için nesne. Bkz: [CToolBar](../mfc/reference/ctoolbar-class.md) oluşturma ve bir araç kullanarak oluşturma hakkında bilgi için `CToolBar`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

