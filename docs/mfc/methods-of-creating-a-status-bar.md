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
ms.openlocfilehash: 9bdaa76dc68467dce1021d9b5f54eaafa248c529
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624267"
---
# <a name="methods-of-creating-a-status-bar"></a>Durum Çubuğu Oluşturma Yöntemleri

MFC durum çubukları oluşturmak için iki sınıf sağlar: [CStatusBar](reference/cstatusbar-class.md) ve [CStatusBarCtrl](reference/cstatusbarctrl-class.md) (Windows ortak denetim API 'sini sarmalayan). `CStatusBar`durum çubuğu ortak denetimindeki tüm işlevleri sağlar, menüler ve araç çubuklarıyla otomatik olarak etkileşime girer ve sizin için gerekli ortak denetim ayarlarının ve yapıların çoğunu işler; Ancak, elde edilen yürütülebilir dosya genellikle kullanılarak oluşturulanlar daha büyük olur `CStatusBarCtrl` .

`CStatusBarCtrl`genellikle daha küçük bir yürütülebilirle sonuçlanır ve `CStatusBarCtrl` durum çubuğunu MFC mimarisine tümleştirmeyi düşünmüyorsanız kullanmayı tercih edebilirsiniz. `CStatusBarCtrl`Durum çubuğunu MFC mimarisine göre kullanmayı ve tümleştirmeyi planlıyorsanız, durum çubuğu denetimi işlemelerini MFC 'ye iletmede ek dikkatli olmanız gerekir. Bu iletişim zor değildir; Ancak, kullandığınızda gereksiz olan ek çalışmadır `CStatusBar` .

Visual C++, durum çubuğu ortak denetiminden faydalanmak için iki yol sağlar.

- Kullanarak durum çubuğunu oluşturun `CStatusBar` ve sonra da üye işlevlerine erişim sağlamak Için [CStatusBar:: GetStatusBarCtrl](reference/cstatusbar-class.md#getstatusbarctrl) öğesini çağırın `CStatusBarCtrl` .

- [CStatusBarCtrl](reference/cstatusbarctrl-class.md)'in oluşturucusunu kullanarak durum çubuğunu oluşturun.

Her iki yöntem de durum çubuğu denetiminin üye işlevlerine erişmenizi sağlar. `CStatusBar::GetStatusBarCtrl`' İ çağırdığınızda, `CStatusBarCtrl` herhangi bir üye işlevi kümesini kullanabilmeniz için bir nesnesine bir başvuru döndürür. Kullanarak durum çubuğu oluşturma ve oluşturma hakkında bilgi için bkz. [CStatusBar](reference/cstatusbar-class.md) `CStatusBar` .

## <a name="see-also"></a>Ayrıca bkz.

[CStatusBarCtrl Kullanma](using-cstatusbarctrl.md)<br/>
[Denetimler](controls-mfc.md)
