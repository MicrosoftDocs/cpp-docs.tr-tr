---
title: Bir Araç Çubuğu Denetiminin Görünümünü Özelleştirme
ms.date: 11/04/2016
f1_keywords:
- TBSTYLE_
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
ms.openlocfilehash: 9f4f9d90113d5074555d1b0cc411f854abc67fe5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377472"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminin Görünümünü Özelleştirme

Sınıf, `CToolBarCtrl` araç çubuğu nesnesinin görünümünü (ve bazen de davranışı) etkileyen birçok stil sağlar. Araç çubuğu denetimini `dwCtrlStyle` ilk oluşturduğunuzda `CToolBarCtrl::Create` `CToolBar::CreateEx`(veya) üye işlevin parametresini ayarlayarak araç çubuğu nesnesini değiştirin.

Aşağıdaki stiller araç çubuğu düğmelerinin "3B" yönünü ve düğme metninin yerleşimini etkiler:

- **TBSTYLE_FLAT** Hem araç çubuğunun hem de düğmelerin saydam olduğu düz bir araç çubuğu oluşturur. Düğme metni düğme bit eşlemlerinin altında görüntülenir. Bu stil kullanıldığında, imlecin altındaki düğme otomatik olarak vurgulanır.

- **TBSTYLE_TRANSPARENT** Saydam bir araç çubuğu oluşturur. Saydam bir araç çubuğunda araç çubuğu saydamdır, ancak düğmeler saydam değildir. Düğme metni düğme bit eşlemlerinin altında görüntülenir.

- **TBSTYLE_LIST** Düğme bit eşlemlerinin sağına düğme metni yerleştirir.

> [!NOTE]
> Yeniden boyama sorunlarını önlemek için, araç çubuğu nesnesi görünmeden önce **TBSTYLE_FLAT** ve **TBSTYLE_TRANSPARENT** stilleri ayarlanmalıdır.

Aşağıdaki stiller, araç çubuğunun kullanıcının sürükle ve bırak'ı kullanarak araç çubuğu nesnesi içindeki tek tek düğmeleri yeniden konumlandırmasına izin verilip verilip verilemeyiş verdiğini belirler:

- **TBSTYLE_ALTDRAG** Kullanıcıların ALT basılı tutarken sürükleyerek bir araç çubuğu düğmesinin konumunu değiştirmesini sağlar. Bu stil belirtilmemişse, kullanıcı bir düğmeyi sürüklerken SHIFT'i basılı tutmalıdır.

    > [!NOTE]
    >  Araç çubuğu düğmelerinin sürüklenmesini sağlamak için **CCS_ADJUSTABLE** stili belirtilmelidir.

- **TBSTYLE_REGISTERDROP** Fare işaretçisi araç çubuğu düğmelerinin üzerinden geçtiğinde hedef nesneleri bırakma isteğinde **TBN_GETOBJECT** bildirim iletileri oluşturur.

Kalan stiller araç çubuğu nesnesinin görsel ve görsel olmayan yönlerini etkiler:

- **TBSTYLE_WRAPABLE** Birden çok düğme satırı na sahip olabilecek bir araç çubuğu oluşturur. Araç çubuğu, araç çubuğu aynı satırdaki tüm düğmeleri içerecek kadar daraldığında araç çubuğu düğmeleri bir sonraki satıra "kaydırabilir". Sarma ayırma ve grup dışı sınırlarda gerçekleşir.

- **TBSTYLE_CUSTOMERASE** İletileri işlerken **NM_CUSTOMDRAW** bildirim iletileri oluşturur **WM_ERASEBKGND.**

- **TBSTYLE_TOOLTIPS** Araç çubuğundaki düğmeler için açıklayıcı metin görüntülemek için bir uygulamanın kullanabileceği bir araç ipucu denetimi oluşturur.

Araç çubuğu stillerinin ve genişletilmiş stillerin tam bir listesi için Windows SDK'daki [Araç Çubuğu Denetimi ve Düğme Stilleri](/windows/win32/Controls/toolbar-control-and-button-styles) ve Araç Çubuğu Genişletilmiş [Stilleri'ne](/windows/win32/Controls/toolbar-extended-styles) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
