---
title: "Sık kullanılan tuş denetimi kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 016243de093ced7483506068e6e6478c024b07d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-a-hot-key-control"></a>Bir Sık Kullanılan Tuş Denetimi Kullanma
Sık kullanılan tuş denetimi tipik kullanımını deseni izler:  
  
-   Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilirse, iletişim kutusu oluşturulurken oluşturma otomatik olarak yapılır. (Olması bir [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) üye iletişim sınıfınızda sık kullanılan tuş denetimi karşılık gelir.) Alternatif olarak, kullanabileceğiniz [oluşturma](../mfc/reference/chotkeyctrl-class.md#create) denetimi penceresi alt pencere olarak oluşturmak için üye işlevi.  
  
-   Denetim için varsayılan bir değer ayarlamak istiyorsanız, çağrı [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) üye işlevi. Belirli shift durumları engellemek istiyorsanız, çağrı [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules). Bir iletişim kutusu denetimleri için bunu yapmak için iletişim kutusunun zamanıdır [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.  
  
-   Kullanıcı, sık kullanılan tuş denetimi odağa sahip olduğunda bir sık kullanılan tuş bileşimini tuşlarına basarak denetimi ile etkileşime girer. Kullanıcı ardından şekilde bu görevi belki de iletişim kutusunda bir düğmeye tıklayarak tam, olduğunu gösterir.  
  
-   Programınızı sık kullanılan tuş seçilen kullanıcı bildirildiğinde üye fonksiyonu kullanmalısınız [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) sık kullanılan tuş denetimi sanal anahtar ve shift durum değerleri almak için.  
  
-   Ne seçili kullanıcı anahtar öğrendikten sonra açıklanan yöntemlerden birini kullanarak sık kullanılan tuş ayarlayabilirsiniz [sık kullanılan tuş ayarlama](../mfc/setting-a-hot-key.md).  
  
-   Sık kullanılan tuş denetimi iletişim kutusunda, varsa onu ve `CHotKeyCtrl` nesne yok otomatik olarak. Her iki denetimi emin olmak ihtiyacınız olmayan, varsa ve `CHotKeyCtrl` nesne düzgün yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CHotKeyCtrl kullanma](../mfc/using-chotkeyctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

