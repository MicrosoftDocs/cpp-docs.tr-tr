---
title: CSpinButtonCtrl Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
ms.openlocfilehash: 6f72601d3813f36e4a99b9ab04f2e9383c58df94
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366478"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl Kullanma

*Döndürme düğmesi* denetimi *(yukarı-aşağı* denetim olarak da bilinir) bir kullanıcının bir değeri ayarlamak için tıklatabileceği bir çift ok sağlar. Bu değer geçerli *konum*olarak bilinir. Konum, döndürme düğmesinin aralığında kalır. Kullanıcı yukarı ok'u tıklattığında, konum maksimuma doğru hareket eder; ve kullanıcı aşağı ok'u tıklattığında, konum minimuma doğru hareket eder.

Spin düğmesi denetimi MFC'de [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) sınıfı tarafından temsil edilir.

> [!NOTE]
> Varsayılan olarak, döndürme düğmesinin aralığı en fazla sıfır (0) ve minimum küme 100'e sahiptir. En büyük değer minimum değerden daha az olduğundan, yukarı ok tıklatıldığında konumu azaltır ve aşağı ok atamama artar. Bu değerleri ayarlamak için [CSpinButtonCtrl::SetRange'i](../mfc/reference/cspinbuttonctrl-class.md#setrange) kullanın.

Genellikle, geçerli konum bir yardımcı denetim görüntülenir. Refakatçi *denetimi, arkadaş penceresi*olarak bilinir. Döndürme düğmesi denetiminin bir örneği için Windows SDK'daki [Yukarı-Aşağı Denetimler Hakkında'ya](/windows/win32/Controls/up-down-controls) bakın.

Visual Studio'da bir döndürme denetimi ve bir denetim arkadaşı penceresi oluşturmak için önce bir denetim denetimini iletişim kutusuna veya penceresine sürükleyin ve ardından bir döndürme denetimini sürükleyin. Spin denetimini seçin ve **Auto Buddy** ve Set **Buddy Integer** özelliklerini **True**olarak ayarlayın. Ayrıca **Hizalama** özelliğini de ayarlayın; **Sağ Hizalama** en tipiktir. Bu ayarlarla, sekme düzenindeki düzen denetiminden doğrudan önce geldiği için düzen denetimi ahbap penceresi olarak ayarlanır. Denetim degerleri görüntüler ve döndürme denetimi, edit denetiminin sağ tarafına gömülür. İsteğe bağlı olarak, [CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) yöntemini kullanarak spin denetiminin geçerli aralığını ayarlayabilirsiniz. Veri alışverişi doğrudan çünkü hiçbir olay işleyicileri spin denetimi ve dostum penceresi arasında iletişim kurmak için gerekli değildir. Örneğin, bir pencere veya iletişim kutusu dizisi aracılığıyla sayfa lamak için başka bir amaç için bir döndürme denetimi kullanıyorsanız, UDN_DELTAPOS iletiiçin bir işleyici ekleyin ve özel eyleminizi burada gerçekleştirin.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Spin Düğmesi Stilleri](../mfc/spin-button-styles.md)

- [Spin Düğmesi Üye Fonksiyonları](../mfc/spin-button-member-functions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Denetimler](../mfc/controls-mfc.md)
