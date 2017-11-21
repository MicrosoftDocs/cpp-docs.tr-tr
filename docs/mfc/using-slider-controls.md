---
title: "Kaydırıcı denetimlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e45ba5422f1d1c458cfeffe65b91122158bbbcff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-slider-controls"></a>Kaydırıcı Denetimlerini Kullanma
Kaydırıcı denetimi tipik kullanım deseni izler:  
  
-   Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilirse, iletişim kutusu oluşturulurken oluşturma otomatik olarak yapılır. (Olması bir [CSliderCtrl](../mfc/reference/csliderctrl-class.md) üye iletişim sınıfınızda kaydırıcı denetimi karşılık gelir.) Alternatif olarak, kullanabileceğiniz [oluşturma](../mfc/reference/csliderctrl-class.md#create) denetimi penceresi alt pencere olarak oluşturmak için üye işlevi.  
  
-   Denetim değerlerini ayarlamak için çeşitli kümesi üye işlevleri çağırma. Yapabileceğiniz değişiklikleri kaydırıcıyı için minimum ve maksimum konumlarına ayarlama, değer çizgileri çizim, seçim aralığını ayarlama ve kaydırıcıyı yeniden konumlandırma içerir. Bir iletişim kutusu denetimleri için bunu yapmak için bir iletişim kutusunda 's zamanıdır [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.  
  
-   Kullanıcı denetimi ile etkileşim gibi çeşitli bildirim iletileri gönderir. Çağırarak denetimden kaydırıcı değeri ayıklayabilirsiniz [GetPos](../mfc/reference/csliderctrl-class.md#getpos) üye işlevi.  
  
-   Denetimle bittiğinde, düzgün bir şekilde yok emin olmanız gerekir. Kaydırıcı denetimi iletişim kutusunda, varsa onu ve `CSliderCtrl` nesne yok otomatik olarak. Her iki denetimi emin olmak ihtiyacınız olmayan, varsa ve `CSliderCtrl` nesne düzgün yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSliderCtrl kullanma](../mfc/using-csliderctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

