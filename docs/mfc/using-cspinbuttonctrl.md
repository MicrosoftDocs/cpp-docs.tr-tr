---
title: CSpinButtonCtrl Kullanma
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
ms.openlocfilehash: a2a12672f0e70248e135bdd177b76589b6197c75
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513472"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl Kullanma

*Döndürme düğmesi* denetimi ( *Yukarı açılan* denetim olarak da bilinir), kullanıcının bir değeri ayarlamak için tıklabileceği bir çift ok sağlar. Bu değer *geçerli konum*olarak bilinir. Konum, döndürme düğmesinin aralığı içinde kalır. Kullanıcı yukarı oka tıkladığında, konum en büyük değere doğru hareket eder; Kullanıcı aşağı oka tıkladığında, konum en küçük değere doğru hareket eder.

Döndürme düğmesi denetimi, MFC 'de [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) sınıfı tarafından temsil edilir.

> [!NOTE]
>  Varsayılan olarak, döndürme düğmesine yönelik Aralık sıfıra (0), minimum ise 100 olarak ayarlanmıştır. En büyük değer en küçük değerden daha az olduğu için, yukarı oka tıklamak konumu düşürür ve aşağı oka tıklamak onu arttırır. Bu değerleri ayarlamak için [CSpinButtonCtrl:: SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) kullanın.

Genellikle, geçerli konum bir yardımcı denetimde görüntülenir. Yardımcı denetim *arkadaş penceresi*olarak bilinir. Bir döndürme düğmesi denetiminin bir çizimi için bkz. Windows SDK [Yukarı açılan denetimler hakkında](/windows/win32/Controls/up-down-controls) .

Bir döndürme denetimi ve düzenleme denetimi arkadaş penceresi oluşturmak için, Visual Studio 'da, önce bir düzenleme denetimini iletişim kutusu veya pencereye sürükleyin ve sonra bir döndürme denetimini sürükleyin. Döndürme denetimini seçin ve kendi **Otomatik arkadaşları** ' nı ayarlayın ve **arkadaş tamsayı** özelliklerini **doğru**olarak ayarlayın. **Hizalama** özelliğini de ayarlayın; **Sağa Hizala** en normaldir. Bu ayarlarla düzenleme denetimi, doğrudan sekme düzeninde düzenleme denetiminden önce olduğu için arkadaş pencere olarak ayarlanır. Düzenleme denetimi tamsayılar görüntüler ve döndürme denetimi, düzenleme denetiminin sağ tarafına katıştırılır. İsteğe bağlı olarak, [CSpinButtonCtrl:: SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) yöntemini kullanarak, döndürme denetiminin geçerli aralığını ayarlayabilirsiniz. Verileri doğrudan değiş tokuş ettiğinden, döndürme denetimi ve arkadaş penceresi arasında iletişim kurmak için herhangi bir olay işleyicisi gerekmez. Örneğin, bir dizi Windows veya iletişim kutusu aracılığıyla sayfa için bir döndürme denetimi kullanırsanız, UDN_DELTAPOS iletisi için bir işleyici ekleyin ve özel eyleminizi orada gerçekleştirin.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Döndür Düğmesi Stilleri](../mfc/spin-button-styles.md)

- [Döndür Düğmesi Üye İşlevleri](../mfc/spin-button-member-functions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Denetimler](../mfc/controls-mfc.md)
