---
description: 'Hakkında daha fazla bilgi edinin: CSpinButtonCtrl kullanma'
title: CSpinButtonCtrl Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
ms.openlocfilehash: ef596c4f194eb60fc8548231293d4570456d2f54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271596"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl Kullanma

*Döndürme düğmesi* denetimi ( *Yukarı açılan* denetim olarak da bilinir), kullanıcının bir değeri ayarlamak için tıklabileceği bir çift ok sağlar. Bu değer *geçerli konum* olarak bilinir. Konum, döndürme düğmesinin aralığı içinde kalır. Kullanıcı yukarı oka tıkladığında, konum en büyük değere doğru hareket eder; Kullanıcı aşağı oka tıkladığında, konum en küçük değere doğru hareket eder.

Döndürme düğmesi denetimi, MFC 'de [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) sınıfı tarafından temsil edilir.

> [!NOTE]
> Varsayılan olarak, döndürme düğmesine yönelik Aralık sıfıra (0), minimum ise 100 olarak ayarlanmıştır. En büyük değer en küçük değerden daha az olduğu için, yukarı oka tıklamak konumu düşürür ve aşağı oka tıklamak onu arttırır. Bu değerleri ayarlamak için [CSpinButtonCtrl:: SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) kullanın.

Genellikle, geçerli konum bir yardımcı denetimde görüntülenir. Yardımcı denetim *arkadaş penceresi* olarak bilinir. Bir döndürme düğmesi denetiminin bir çizimi için, bkz. Windows SDK [Up-Down denetimleri hakkında](/windows/win32/Controls/up-down-controls) .

Bir döndürme denetimi ve düzenleme denetimi arkadaş penceresi oluşturmak için, Visual Studio 'da, önce bir düzenleme denetimini iletişim kutusu veya pencereye sürükleyin ve sonra bir döndürme denetimini sürükleyin. Döndürme denetimini seçin ve kendi **Otomatik arkadaşları** ' nı ayarlayın ve **arkadaş tamsayı** özelliklerini **doğru** olarak ayarlayın. **Hizalama** özelliğini de ayarlayın; **Sağa Hizala** en normaldir. Bu ayarlarla düzenleme denetimi, doğrudan sekme düzeninde düzenleme denetiminden önce olduğu için arkadaş pencere olarak ayarlanır. Düzenleme denetimi tamsayılar görüntüler ve döndürme denetimi, düzenleme denetiminin sağ tarafına katıştırılır. İsteğe bağlı olarak, [CSpinButtonCtrl:: SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) yöntemini kullanarak, döndürme denetiminin geçerli aralığını ayarlayabilirsiniz. Verileri doğrudan değiş tokuş ettiğinden, döndürme denetimi ve arkadaş penceresi arasında iletişim kurmak için herhangi bir olay işleyicisi gerekmez. Örneğin, bir dizi Windows veya iletişim kutusu aracılığıyla sayfa yapmak için başka bir amaçla bir döndürme denetimi kullanıyorsanız, UDN_DELTAPOS ileti için bir işleyici ekleyin ve özel eyleminizi orada gerçekleştirin.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Döndürme düğmesi stilleri](../mfc/spin-button-styles.md)

- [Döndürme düğmesi üye Işlevleri](../mfc/spin-button-member-functions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Denetimler](../mfc/controls-mfc.md)
