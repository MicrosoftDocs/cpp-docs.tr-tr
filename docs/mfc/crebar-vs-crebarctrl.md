---
title: CReBar vs. CReBarCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CReBar
- CReBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c98b2fd9baf97d351c812f2c442d408ff6221d82
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932266"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar vs. CReBarCtrl
MFC rebars oluşturmak için iki sınıflar sağlar: [CReBar](../mfc/reference/crebar-class.md) ve [CReBarCtrl](../mfc/reference/crebarctrl-class.md) (hangi sarmalar Windows ortak denetim API'si). `CReBar` Tüm rebar ortak denetim işlevselliğini sağlar ve bu gerekli ortak denetim ayarlarını ve yapıları birçoğu sizin için işler.  
  
 `CReBarCtrl` Win32 rebar denetimi için sarmalayıcı sınıftır ve bu nedenle MFC mimariye rebar tümleştirmek düşünmüyorsanız uygulamak daha kolay olabilir. Kullanmayı planlıyorsanız, `CReBarCtrl` ve MFC mimariye rebar tümleştirmek, MFC rebar denetimi işlemeleri iletişim kurmak için ek dikkat edin gerekir. Bu iletişim zor değil; Ancak, kullandığınızda, gereksiz ek iş olduğu `CReBar`.  
  
 Visual C++ rebar ortak denetimi yararlanmak için iki yöntem sunar.  
  
-   Rebar kullanarak oluşturduğunuz `CReBar`ve ardından arama [CReBar::GetReBarCtrl](../mfc/reference/crebar-class.md#getrebarctrl) erişmek için `CReBarCtrl` üye işlevleri.  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl` çevirir satır içi üye işlevi **bu** rebar nesne işaretçisi. Bu, çalışma zamanında işlev çağrısı olmamasıdır vermiş olursunuz.  
  
-   Rebar kullanarak oluşturduğunuz [CReBarCtrl](../mfc/reference/crebarctrl-class.md)'s Oluşturucusu.  
  
 Her iki yöntem rebar denetimi üye işlevleri için erişim sahibi olursunuz. Çağırdığınızda `CReBar::GetReBarCtrl`, bir başvuru döndürür bir `CReBarCtrl` ya da kümesi üye işlevlerini kullanabilmeniz için nesne. Bkz: [CReBar](../mfc/reference/crebar-class.md) oluşturma ve kullanma rebar oluşturma hakkında bilgi için `CReBar`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

