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
ms.openlocfilehash: b70e6f4dc15023b878bb58d6b7d0739eeb173d53
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624258"
---
# <a name="methods-of-creating-a-toolbar"></a>Araç Çubuğu Oluşturma Yöntemleri

MFC araç çubukları oluşturmak için iki sınıf sağlar: [CToolBar](reference/ctoolbar-class.md) ve [CToolBarCtrl](reference/ctoolbarctrl-class.md) (Windows ortak denetim API 'sini sarmalayan). `CToolBar`araç çubuğu ortak denetiminin tüm işlevlerini sağlar ve sizin için gerekli ortak denetim ayarlarının ve yapıların çoğunu işler; Ancak, elde edilen yürütülebilir dosya genellikle kullanılarak oluşturulanlar daha büyük olur `CToolBarCtrl` .

`CToolBarCtrl`genellikle daha küçük bir yürütülebilirle sonuçlanır ve `CToolBarCtrl` araç çubuğunu MFC mimarisine tümleştirmeyi düşünmüyorsanız kullanmayı tercih edebilirsiniz. `CToolBarCtrl`Araç çubuğunu MFC mimarisine göre kullanmayı ve tümleştirmeyi planlıyorsanız, araç çubuğu denetimi IŞLEMELERINI MFC 'ye iletmek için ek dikkatli olmanız gerekir. Bu iletişim zor değildir; Ancak, kullandığınızda gereksiz olan ek çalışmadır `CToolBar` .

Visual C++ araç çubuğu ortak denetiminden faydalanmak için iki yol sağlar.

- Kullanarak araç çubuğunu oluşturun `CToolBar` ve ardından [CToolBar:: GetToolBarCtrl](reference/ctoolbar-class.md#gettoolbarctrl) ' i çağırıp `CToolBarCtrl` üye işlevlerine erişin.

- [CToolBarCtrl](reference/ctoolbarctrl-class.md)' in oluşturucusunu kullanarak araç çubuğunu oluşturun.

Her iki yöntem de Toolbar denetiminin üye işlevlerine erişmenizi sağlar. `CToolBar::GetToolBarCtrl`' İ çağırdığınızda, `CToolBarCtrl` herhangi bir üye işlevi kümesini kullanabilmeniz için bir nesnesine bir başvuru döndürür. Kullanarak bir araç çubuğu oluşturma ve oluşturma hakkında bilgi için bkz. [CToolBar](reference/ctoolbar-class.md) `CToolBar` .

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](using-ctoolbarctrl.md)<br/>
[Denetimler](controls-mfc.md)
