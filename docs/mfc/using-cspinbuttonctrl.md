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
ms.openlocfilehash: 3768cda94eb0adda8562c46124be8e9b2d4a2501
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215098"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl Kullanma
*Değer değiştirme düğmesi* denetimi (olarak da bilinen bir *yukarı-aşağı* denetimi), bir kullanıcının bir değer ayarlamak için tıklayabileceği oklar çifti sağlar. Bu değer olarak da bilinen *geçerli konumu*. Konumu değer değiştirme düğmesi aralığı içinde kalır. Kullanıcı Yukarı Oka tıkladığında en doğru konuma taşır; ve kullanıcı aşağı oka tıkladığında, en doğru konuma taşır.  
  
 Değer değiştirme düğmesi denetimi, MFC tarafından temsil edilen [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) sınıfı.  
  
> [!NOTE]
>  Varsayılan olarak, değer değiştirme düğmesi aralığının üst sınırı sıfır (0) olarak ayarlayın ve en az 100'e ayarlayın vardır. Maksimum değer minimum değerden daha az olduğundan, konumu yukarı oka tıklayarak azaltır ve aşağı oka tıklayarak artırır. Kullanım [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) bu değerleri ayarlamak için.  
  
 Genellikle, geçerli konum bir yardımcı denetiminde görüntülenir. Özel denetim olarak bilinir *buddy penceresindeki*. Değer değiştirme düğmesi denetimi bir çizim için bkz [yukarı-aşağı denetimleri hakkında](/windows/desktop/Controls/up-down-controls) Windows SDK.  
  
 Döndürme denetimi ve bir düzenleme denetiminin buddy penceresindeki Visual Studio'da oluşturmak için önce bir düzenleme denetimi iletişim kutusunu veya penceresine sürükleyin ve ardından bir döndürme denetimi sürükleyin. Döndürme denetimi seçin ve ayarlayın, **otomatik Buddy** ve **ayarlamak arkadaş tamsayı** özelliklerine **True**. Ayrıca **hizalama** özelliği; **Sağa Hizala** en sık görülen bir durumdur. Doğrudan düzenleme denetiminin sekme sırasının kendisinden çünkü bu ayarlarla düzenleme denetiminin buddy penceresindeki gibi ayarlanır. Düzenleme denetimi tamsayı görüntüler ve döndürme denetimi düzenleme denetiminin sağ tarafında bulunan katıştırılır. İsteğe bağlı olarak, döndürme denetimi geçerli aralığı kullanarak ayarlayabileceğiniz [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) yöntemi. Hiçbir olay işleyicileri, çünkü onlar doğrudan veri değişimi döndürme denetimi ve buddy penceresindeki arasında iletişim kurmak için gereklidir. Döndürme denetimi başka bir amaç için kullanıyorsanız, örneğin, windows veya iletişim kutularında, bir dizi sayfasında UDN_DELTAPOS ileti işleyicisi eklersiniz ve vardır, özel eylem gerçekleştirme.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Döndür Düğmesi Stilleri](../mfc/spin-button-styles.md)  
  
-   [Döndür Düğmesi Üye İşlevleri](../mfc/spin-button-member-functions.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimler](../mfc/controls-mfc.md)

