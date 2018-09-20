---
title: Döndür düğmesi üye işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88f00aedcf269996277c154f9dd051534a9c5e49
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431543"
---
# <a name="spin-button-member-functions"></a>Döndür Düğmesi Üye İşlevleri

Döndürme denetimi için kullanılabilen çeşitli üye işlevleri vardır ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Değer değiştirme düğmesi aşağıdaki özniteliklerini değiştirmek için bu işlevleri kullanın.

- **Hızlandırma** başlangıçtan konumu değiştiren kullanıcı ok düğmesini basılı tuttuğunda oranı ayarlayabilirsiniz. Hızlandırma ile çalışmak üzere kullanma [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) ve [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) üye işlevleri.

- **Temel** buddy penceresinin başlık konumda görüntülemek için kullanılan base (10 veya 16) değiştirebilirsiniz. Temel ile çalışmak üzere kullanma [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) ve [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) üye işlevleri.

- **Pencere dost** buddy penceresindeki dinamik olarak ayarlayabilirsiniz. Sorgu veya buddy penceresindeki denetleyen değiştirmek için kullanın [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) ve [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) üye işlevleri.

- **Konum** sorgulamak ve konumunu değiştirir. Doğrudan konumu ile çalışmak üzere kullanma [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) ve [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) üye işlevleri. Arkadaş denetimi altyazısı (arkadaş bir düzenleme denetimi olduğunu gibi durumlarda) değişmiş olabilir beri `GetPos` geçerli resim yazısını alır ve buna göre konumunu ayarlar.

- **Aralık** değer değiştirme düğmesi için maksimum ve minimum konumları değiştirebilirsiniz. Varsayılan olarak, en fazla 0 olarak ayarlanır ve en az 100'e ayarlayın. Varsayılan üst sınır varsayılan en düşük değer daha az olduğundan, ok düğmelerini eylemlerini counter-intuitive değerindedir. Genellikle, aralığı kullanarak ayarlayacak [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) üye işlevi. Sorgu aralığı kullanımı [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange).

## <a name="see-also"></a>Ayrıca Bkz.

[CSpinButtonCtrl Kullanma](../mfc/using-cspinbuttonctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

