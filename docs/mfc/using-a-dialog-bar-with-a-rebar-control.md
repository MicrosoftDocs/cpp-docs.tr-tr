---
title: Rebar denetimiyle birlikte bir iletişim çubuğu kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa2628df5f446105e6b7881709a0c72c19fe230e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950496"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Rebar Denetimiyle Birlikte Bir İletişim Çubuğu Kullanma
Bölümünde belirtildiği gibi [Rebar denetimleri ve bantları](../mfc/rebar-controls-and-bands.md), her bant yalnızca bir alt pencere (veya Denetim) içerebilir. Bant başına birden fazla alt pencere sahip olmak istiyorsanız bu bir sınırlama olabilir. Bir iletişim çubuğu kaynak sahip birden çok denetim oluşturma ve rebar denetimi (iletişim kutusu çubuğunu içeren) bir rebar bant eklemek için kullanışlı bir geçici bir çözüm değildir.  
  
 Normalde, saydam görünmesini iletişim çubuğu bant istediyseniz, genişletilmiş Stili iletişim çubuğu nesnesinin WS_EX_TRANSPARENT ayarlamanız gerekir. Ancak, WS_EX_TRANSPARENT düzgün bir iletişim çubuğu arka plan boyama bazı sorunlar olduğundan, istenen etkiyi elde etmek için biraz ek iş yapmanız gerekir.  
  
 Aşağıdaki yordam ayrıntıları WS_EX_TRANSPARENT kullanmadan saydamlık elde etmek için gerekli adımları genişletilmiş stili.  
  
### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Bir rebar bant saydam iletişim çubuğu uygulamak için  
  
1.  Kullanarak [Sınıf Ekle iletişim kutusu](../mfc/reference/adding-an-mfc-class.md), yeni bir sınıf ekleyin (örneğin, `CMyDlgBar`) iletişim çubuğu nesnenizin uygular.  
  
2.  WM_ERASEBKGND iletisi için bir işleyici ekleyin.  
  
3.  Yeni işleyicisinde aşağıdaki örnekle eşleşmesi için var olan kodu değiştirin:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  WM_MOVE iletisi için bir işleyici ekleyin.  
  
5.  Yeni işleyicisinde aşağıdaki örnekle eşleşmesi için var olan kodu değiştirin:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 Yeni işleyicileri iletişim çubuğu saydamlığını üst pencere WM_ERASEBKGND iletiyi iletme ve iletişim çubuğu nesne taşındı her zaman yeniden çizmeyi zorlama benzetimini yapma.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

