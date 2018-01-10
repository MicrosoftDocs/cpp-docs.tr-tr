---
title: Bir ortak denetimi alt pencere olarak kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 475c769bf09c0693c04780712b85884ae7c48862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-common-control-as-a-child-window"></a>Bir Ortak Denetimi Alt Pencere Olarak Kullanma
Windows ortak denetimleri herhangi bir başka bir pencere alt pencere olarak kullanılabilir. Aşağıdaki yordam, bir ortak denetimi dinamik olarak oluşturabilir ve sonra çalışma açıklar.  
  
### <a name="to-use-a-common-control-as-a-child-window"></a>Bir ortak denetimi alt pencere olarak kullanmak için  
  
1.  Denetim ilgili sınıf veya işleyici tanımlayın.  
  
2.  Denetimin geçersiz kılmasını kullanın [CWnd::Create](../mfc/reference/cwnd-class.md#create) Windows denetimi oluşturmak için yöntemi.  
  
3.  Denetim oluşturulduktan sonra (olarak erken `OnCreate` işleyici durumunda denetimi alt), kendi üye işlevleri kullanarak denetimi değiştirebilirsiniz. Tek tek denetimleri açıklamalarına bakın [denetimleri](../mfc/controls-mfc.md) yöntemleri hakkında ayrıntılı bilgi için.  
  
4.  Denetimi ile işiniz bittiğinde, kullanın [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) denetimi yok etmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)   
 [Denetimler](../mfc/controls-mfc.md)

