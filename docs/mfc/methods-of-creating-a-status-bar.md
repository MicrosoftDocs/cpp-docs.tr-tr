---
title: Durum Çubuğu Oluşturma Yöntemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
ms.openlocfilehash: 1156f8bdeafb71dc9e6dbd9fc5b85607542918f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587986"
---
# <a name="methods-of-creating-a-status-bar"></a>Durum Çubuğu Oluşturma Yöntemleri

MFC durum çubukları oluşturmak için iki sınıflar sağlar: [CStatusBar](../mfc/reference/cstatusbar-class.md) ve [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (hangi sarmalar Windows ortak denetim API'si). `CStatusBar` tüm işlevleri sağlayan ortak denetim çubuğunun durumunu, otomatik olarak menüleri ve araç çubuklarını ile etkileşim kurar ve sizin için; birçok gerekli ortak denetim ayarları ve yapıları işlediği Ancak, elde edilen çalıştırılabilir dosyayı genellikle kullanılarak oluşturulan büyük olacaktır `CStatusBarCtrl`.

`CStatusBarCtrl` genellikle daha küçük bir yürütülebilir dosyayı ve sonuçları kullanmayı tercih edebilirsiniz `CStatusBarCtrl` durum çubuğunda bir MFC mimari olarak tümleştirmek düşünmüyorsanız. Kullanmayı planlıyorsanız `CStatusBarCtrl` ve durum çubuğunda bir MFC mimari olarak tümleştirin, durum çubuğu denetimi işlemeleri MFC iletişim kurmak için daha da dikkatli göz önüne almanız gerekir. Bu iletişim zor değildir; Ancak, kullandığınızda, gereksiz ek çalışma gerekir `CStatusBar`.

Visual C++, durum çubuğu ortak denetim yararlanmak için iki yol sunar.

- Durum çubuğunda kullanarak oluşturma `CStatusBar`ve sonra çağrı [CStatusBar::GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) erişim elde etmek için `CStatusBarCtrl` üye işlevleri.

- Durum çubuğunda kullanarak oluşturma [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)'s Oluşturucusu.

Her iki yöntem için durum çubuğu denetimi üye işlevleri sürümlere erişmenizi sağlayacaktır. Çağırdığınızda `CStatusBar::GetStatusBarCtrl`, bir başvuru döndürür bir `CStatusBarCtrl` ayarlayın ya da üye işlevleri kullanabilmeniz için nesne. Bkz: [CStatusBar](../mfc/reference/cstatusbar-class.md) oluşturmak ve bir durum çubuğu kullanarak oluşturma hakkında bilgi `CStatusBar`.

## <a name="see-also"></a>Ayrıca Bkz.

[CStatusBarCtrl Kullanma](../mfc/using-cstatusbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

