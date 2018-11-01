---
title: Araç Çubuğu Oluşturma Yöntemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CToolBarCtrl class [MFC], and CToolBar class [MFC]
- CToolBar class [MFC], creating toolbars
- MFC toolbars
- toolbar controls [MFC]
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
ms.openlocfilehash: 5296c0454e035770e196c3d6a4d15291d0c4ca6c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612465"
---
# <a name="methods-of-creating-a-toolbar"></a>Araç Çubuğu Oluşturma Yöntemleri

MFC araç çubukları oluşturmak için iki sınıflar sağlar: [CToolBar](../mfc/reference/ctoolbar-class.md) ve [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) (hangi sarmalar Windows ortak denetim API'si). `CToolBar` Tüm araç çubuğu ortak denetim işlevlerini sağlar ve sizin için; birçok gerekli ortak denetim ayarları ve yapıları işlediği Ancak, elde edilen çalıştırılabilir dosyayı genellikle kullanılarak oluşturulan büyük olacaktır `CToolBarCtrl`.

`CToolBarCtrl` genellikle daha küçük bir yürütülebilir dosyayı ve sonuçları kullanmayı tercih edebilirsiniz `CToolBarCtrl` MFC mimarisine araç tümleştirmek düşünmüyorsanız. Kullanmayı planlıyorsanız `CToolBarCtrl` ve MFC mimarisine araç tümleştirme, MFC araç çubuğu denetimi işlemeleri iletişim kurmak için daha da dikkatli göz önüne almanız gerekir. Bu iletişim zor değildir; Ancak, kullandığınızda, gereksiz ek çalışma gerekir `CToolBar`.

Visual C++ araç çubuğu ortak denetim yararlanmak için iki yol sunar.

- Araç çubuğunu kullanarak oluşturma `CToolBar`ve sonra çağrı [CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl) erişim elde etmek için `CToolBarCtrl` üye işlevleri.

- Araç çubuğunu kullanarak oluşturma [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)'s Oluşturucusu.

Her iki yöntem araç çubuğu denetimi üye işlevleri için sürümlere erişmenizi sağlayacaktır. Çağırdığınızda `CToolBar::GetToolBarCtrl`, bir başvuru döndürür bir `CToolBarCtrl` ayarlayın ya da üye işlevleri kullanabilmeniz için nesne. Bkz: [CToolBar](../mfc/reference/ctoolbar-class.md) oluşturmak ve bir araç kullanarak oluşturma hakkında bilgi `CToolBar`.

## <a name="see-also"></a>Ayrıca Bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

