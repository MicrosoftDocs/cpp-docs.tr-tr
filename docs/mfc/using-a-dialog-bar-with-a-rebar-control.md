---
title: "Rebar denetimiyle birlikte bir iletişim çubuğu kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WM_EX_TRANSPARENT
dev_langs: C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 573e25a0750ab52da531f86e89094edc16288cdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Rebar Denetimiyle Birlikte Bir İletişim Çubuğu Kullanma
Bölümünde belirtildiği gibi [Rebar denetimleri ve bantları](../mfc/rebar-controls-and-bands.md), her bant yalnızca bir alt pencere (veya Denetim) içerebilir. Bant başına birden fazla alt pencere sahip olmak istiyorsanız bu bir sınırlama olabilir. Bir iletişim çubuğu kaynak sahip birden çok denetim oluşturma ve rebar denetimi (iletişim kutusu çubuğunu içeren) bir rebar bant eklemek için kullanışlı bir geçici bir çözüm değildir.  
  
 Saydam görünmesini iletişim çubuğu bant istediyseniz, normal olarak ayarlamalısınız **WS_EX_TRANSPARENT** genişletilmiş Stili iletişim çubuğu nesnesi. Ancak, çünkü **WS_EX_TRANSPARENT** düzgün bir iletişim çubuğu arka plan boyama bazı sorunlar varsa, istenilen efekti elde etmek için biraz ek iş yapmanız gerekir.  
  
 Aşağıdaki yordam kullanmadan saydamlık elde etmek için gerekli adımları ayrıntıları **WS_EX_TRANSPARENT** genişletilmiş stili.  
  
### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Bir rebar bant saydam iletişim çubuğu uygulamak için  
  
1.  Kullanarak [Sınıf Ekle iletişim kutusu](../mfc/reference/adding-an-mfc-class.md), yeni bir sınıf ekleyin (örneğin, `CMyDlgBar`) iletişim çubuğu nesnenizin uygular.  
  
2.  İçin bir işleyici ekleyin `WM_ERASEBKGND` ileti.  
  
3.  Yeni işleyicisinde aşağıdaki örnekle eşleşmesi için var olan kodu değiştirin:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  İçin bir işleyici ekleyin `WM_MOVE` ileti.  
  
5.  Yeni işleyicisinde aşağıdaki örnekle eşleşmesi için var olan kodu değiştirin:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 Yeni işleyicileri iletişim çubuğu saydamlığını yoluyla iletme benzetimini `WM_ERASEBKGND` üst penceresine ileti ve iletişim çubuğu nesne taşındı her zaman yeniden çizmeyi zorlanıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

