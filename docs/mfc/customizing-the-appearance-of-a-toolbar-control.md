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
ms.openlocfilehash: ddccb5f05152d95377b430d7492ede3c86926e37
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619289"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminin Görünümünü Özelleştirme

Sınıfı, `CToolBarCtrl` araç çubuğu nesnesinin görünümünü (ve bazen davranışını) etkileyen birçok stil sağlar. Araç çubuğu `dwCtrlStyle` `CToolBarCtrl::Create` `CToolBar::CreateEx` denetimini ilk oluşturduğunuzda (veya) üye işlevinin parametresini ayarlayarak araç çubuğu nesnesini değiştirin.

Aşağıdaki stiller araç çubuğu düğmelerinin "3B" yönlerini ve düğme metninin yerleşimini etkiler:

- **tbstyle_flat** Hem araç çubuğunun hem de düğmelerin saydam olduğu düz bir araç çubuğu oluşturur. Düğme metni, düğme bit eşlemler altında görünür. Bu stil kullanıldığında, imlecin altındaki düğme otomatik olarak vurgulanır.

- **tbstyle_transparent** Saydam bir araç çubuğu oluşturur. Saydam bir araç çubuğunda araç çubuğu saydamdır, ancak düğmeler değildir. Düğme metni, düğme bit eşlemler altında görünür.

- **TBSTYLE_LIST** Düğme metnini düğme bit eşlemlerinin sağına koyar.

> [!NOTE]
> Yeniden çizilecek sorunları engellemek için, **tbstyle_flat** ve **tbstyle_transparent** stillerinin araç çubuğu nesnesi görünür olmadan önce ayarlanması gerekir.

Aşağıdaki stiller, Toolbar 'ın sürükle ve bırak kullanarak bir araç çubuğu nesnesi içindeki düğmeleri bir kullanıcının yeniden konumlandırmasına izin verdiğini belirleme:

- **TBSTYLE_ALTDRAG** Kullanıcıların bir araç çubuğu düğmesinin konumunu, ALT tuşunu basılı tutarken sürükleyerek değiştirmesini sağlar. Bu stil belirtilmemişse, Kullanıcı bir düğmeyi sürüklerken SHIFT tuşunu basılı tutmalıdır.

    > [!NOTE]
    >  Araç çubuğu düğmelerinin sürüklenip olmasını sağlamak için **CCS_ADJUSTABLE** stili belirtilmelidir.

- **TBSTYLE_REGISTERDROP** Fare işaretçisi araç çubuğu düğmelerinden geçtiğinde bırakma hedefi nesneleri istemek için **tbn_getobject** bildirim iletileri oluşturur.

Kalan stiller, araç çubuğu nesnesinin görsel ve görsel olmayan yönlerini etkiler:

- **TBSTYLE_WRAPABLE** Birden çok düğme satırı olabilir bir araç çubuğu oluşturur. Araç çubuğu düğmeleri aynı satırdaki tüm düğmeleri içermek için çok dar hale geldiğinde, araç çubuğu düğmeleri sonraki satıra "kaydıramaz". Sarmalama, ayırma ve Grup dışı sınırlar üzerinde gerçekleşir.

- **tbstyle_customerase** **WM_ERASEBKGND** iletileri işlerken **nm_customdraw** bildirim iletileri oluşturur.

- **TBSTYLE_TOOLTIPS** Bir uygulamanın, araç çubuğundaki düğmeler için açıklayıcı metin göstermek üzere kullanabileceği bir araç ipucu denetimi oluşturur.

Araç çubuğu stillerinin ve genişletilmiş stillerin tüm listesi için, Windows SDK [araç çubuğu denetimi ve düğme stilleri](/windows/win32/Controls/toolbar-control-and-button-styles) ve [araç çubuğu Genişletilmiş stilleri](/windows/win32/Controls/toolbar-extended-styles) ' ne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](using-ctoolbarctrl.md)<br/>
[Denetimler](controls-mfc.md)
