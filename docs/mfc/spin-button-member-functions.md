---
description: 'Daha fazla bilgi edinin: döndürme düğmesi üye Işlevleri'
title: Döndür Düğmesi Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
ms.openlocfilehash: 6a03ab33d29634ed85d807eb5b51edfdef310d65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216840"
---
# <a name="spin-button-member-functions"></a>Döndür Düğmesi Üye İşlevleri

Döndürme denetimi için kullanılabilecek birkaç üye işlevi vardır ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Bu işlevleri, döndürme düğmesinin aşağıdaki özniteliklerini değiştirmek için kullanın.

- **Hızlandırma** Kullanıcı ok düğmesini tuttuğunda konumun değiştiği oranı ayarlayabilirsiniz. Hızlandırma ile çalışmak için [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) ve [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) üye işlevlerini kullanın.

- **Taban** Konumu arkadaş penceresinin açıklamalı alt başlığında göstermek için kullanılan temeli (10 veya 16) değiştirebilirsiniz. Taban ile çalışmak için [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) ve [setbase](../mfc/reference/cspinbuttonctrl-class.md#setbase) üye işlevlerini kullanın.

- **Arkadaş penceresi** Arkadaş penceresini dinamik olarak ayarlayabilirsiniz. Arkadaş penceresi olan denetimi sorgulamak veya değiştirmek için [getarkadaş](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) ve [setarkadaş](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) üye işlevlerini kullanın.

- **Konum** Konumu sorgulayabilir ve değiştirebilirsiniz. Doğrudan konum ile çalışmak için [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) ve [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) üye işlevlerini kullanın. Arkadaş denetiminin resim yazısı değişmiş olabileceğinden (örneğin, arkadaş bir düzenleme denetimi olduğu durumda), `GetPos` geçerli başlığı alır ve konumu uygun şekilde ayarlar.

- **Aralık** Döndürme düğmesi için en yüksek ve en düşük pozisyonları değiştirebilirsiniz. Varsayılan olarak, en fazla 0 olarak ayarlanır ve en az 100 olarak ayarlanır. Varsayılan en yüksek değer varsayılan en düşük değerden düşük olduğundan, ok düğmelerinin eylemleri sayaç sezgisel olarak belirlenir. Genellikle, [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) üye işlevini kullanarak aralığı ayarlayacaksınız. Aralığı sorgulamak için [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CSpinButtonCtrl Kullanma](../mfc/using-cspinbuttonctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
