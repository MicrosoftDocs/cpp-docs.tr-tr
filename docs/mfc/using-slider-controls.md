---
title: Kaydırıcı denetimlerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9180d792f38652b22f430e497ef0e42dc54f6d73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="using-slider-controls"></a>Kaydırıcı Denetimlerini Kullanma
Kaydırıcı denetimi tipik kullanım deseni izler:  
  
-   Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilirse, iletişim kutusu oluşturulurken oluşturma otomatik olarak yapılır. (Olması bir [CSliderCtrl](../mfc/reference/csliderctrl-class.md) üye iletişim sınıfınızda kaydırıcı denetimi karşılık gelir.) Alternatif olarak, kullanabileceğiniz [oluşturma](../mfc/reference/csliderctrl-class.md#create) denetimi penceresi alt pencere olarak oluşturmak için üye işlevi.  
  
-   Denetim değerlerini ayarlamak için çeşitli kümesi üye işlevleri çağırma. Yapabileceğiniz değişiklikleri kaydırıcıyı için minimum ve maksimum konumlarına ayarlama, değer çizgileri çizim, seçim aralığını ayarlama ve kaydırıcıyı yeniden konumlandırma içerir. Bir iletişim kutusu denetimleri için bunu yapmak için bir iletişim kutusunda 's zamanıdır [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.  
  
-   Kullanıcı denetimi ile etkileşim gibi çeşitli bildirim iletileri gönderir. Çağırarak denetimden kaydırıcı değeri ayıklayabilirsiniz [GetPos](../mfc/reference/csliderctrl-class.md#getpos) üye işlevi.  
  
-   Denetimle bittiğinde, düzgün bir şekilde yok emin olmanız gerekir. Kaydırıcı denetimi iletişim kutusunda, varsa onu ve `CSliderCtrl` nesne yok otomatik olarak. Her iki denetimi emin olmak ihtiyacınız olmayan, varsa ve `CSliderCtrl` nesne düzgün yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSliderCtrl kullanma](../mfc/using-csliderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

