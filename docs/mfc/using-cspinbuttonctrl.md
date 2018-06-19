---
title: CSpinButtonCtrl kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03b1e83977c1d75070e8878dfdcc53c7afca7a86
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384406"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl Kullanma
*Değer değiştirme düğmesi* denetimi (olarak da bilinen bir *yukarı-aşağı* denetimi) bir kullanıcının bir değer ayarlamak için tıklatabileceği okları çifti sağlar. Bu değer olarak bilinen *geçerli konumu*. Konumu değer değiştirme düğmesi aralık içinde kalır. Kullanıcı yukarı ok tıkladığında, en doğru konuma taşır; ve kullanıcı aşağı oka tıkladığında, en düşük doğru konuma taşır.  
  
 Değer değiştirme düğmesi denetimi MFC tarafından temsil edilen [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) sınıfı.  
  
> [!NOTE]
>  Varsayılan olarak, sıfır (0) olarak ayarlayın en büyük ve 100'e ayarlayın en düşük değer değiştirme düğmesi aralığının sahiptir. En büyük değer en küçük değerden daha küçük olduğundan yukarı oka tıklayarak konumu azaltır ve aşağı oka tıklayarak artırır. Kullanım [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) bu değerleri ayarlamak için.  
  
 Genellikle, geçerli konumu Yardımcısı denetiminde görüntülenir. Yardımcı denetimi olarak bilinen *arkadaş penceresi*. Değer değiştirme düğmesi denetimi çizim için bkz: [hakkında yukarı-aşağı denetimleri](http://msdn.microsoft.com/library/windows/desktop/bb759889) Windows SDK.  
  
 Döndürme denetimi ve düzenleme denetimi arkadaş penceresi, Visual Studio'da oluşturmak için önce bir düzenleme denetimi iletişim kutusunu veya pencere sürükleyin ve döndürme denetimi sürükleyin. Döndürme denetimi seçin ve ayarlayın, **otomatik arkadaş** ve **ayarlamak arkadaş tamsayı** özelliklerine **doğru**. Ayrıca **hizalama** özelliği; **Sağa Hizala** en sık görülen bir durumdur. Doğrudan sekme sırasını düzenleme denetimi önündeki çünkü bu ayarlarla düzenleme denetimi arkadaş pencere olarak ayarlanır. Döngü denetimini düzenleme denetimi sağ tarafındaki katıştırılır ve düzenleme denetimi tamsayı görüntüler. İsteğe bağlı olarak, geçerli aralığın döndürme denetimi kullanarak ayarlayabileceğiniz [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) yöntemi. Olay işleyicileri için verileri doğrudan exchange döndürme denetimi ve arkadaş pencere arasında iletişim gereklidir. Döndürme denetimi başka bir amaç için kullanıyorsanız, örneğin, windows veya iletişim kutuları, bir dizi sayfasında sonra için bir işleyici ekleyin `UDN_DELTAPOS` ileti ve özel eylemi vardır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Döndür Düğmesi Stilleri](../mfc/spin-button-styles.md)  
  
-   [Döndür Düğmesi Üye İşlevleri](../mfc/spin-button-member-functions.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimler](../mfc/controls-mfc.md)

