---
title: Bir araç çubuğu denetiminin görünümünü özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBSTYLE_
dev_langs:
- C++
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54c512bd727b7ef36ee94eb5ccaf3018be692d14
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197701"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminin Görünümünü Özelleştirme
Sınıf `CToolBarCtrl` görünümü (ve bazen davranışı) araç nesnesinin etkileyen birçok stiller sağlar. Araç çubuğu nesnesi ayarlayarak değiştirme `dwCtrlStyle` parametresinin `CToolBarCtrl::Create` (veya `CToolBar::CreateEx`) araç çubuğu denetimi ilk oluşturduğunuzda üye işlevi.  
  
 Aşağıdaki stilleri araç çubuğu düğmeleri "3B" yönünü ve düğme metnini yerleşimini etkiler:  
  
-   **TBSTYLE_FLAT** hem araç hem de düğmeleri nerede saydam bir düz araç çubuğu oluşturur. Düğme metni düğme bit eşlemler altında görünür. Bu stil kullanıldığında, düğmenin imleç altında otomatik olarak vurgulanır.  
  
-   **TBSTYLE_TRANSPARENT** saydam bir araç çubuğu oluşturur. Saydam araç çubuğundaki araç saydamdır ancak düğmeler değildir. Düğme metni düğme bit eşlemler altında görünür.  
  
-   **TBSTYLE_LIST** yerler metni sağa düğme bit eşlem düğmesi.  
  
> [!NOTE]
>  Yeniden çizmeyi sorunları önlemek için **TBSTYLE_FLAT** ve **TBSTYLE_TRANSPARENT** stilleri araç çubuğu görünür olup önce ayarlanmalıdır.  
  
 Araç düğmelerin Sürükle kullanan bir araç çubuğu nesnesi içinde yeniden konumlandırma ve bırakma açmasına olanak sağlar, aşağıdaki stilleri belirler:  
  
-   **TBSTYLE_ALTDRAG** kullanıcıların ALT tuşunu basılı tutarak sürükleyerek bir araç çubuğu düğmesinin konumu değiştirmesine izin verir. Bu stil belirtilmezse, kullanıcı bir düğmeyi sürüklerken SHIFT tuşunu basılı tutun gerekir.  
  
    > [!NOTE]
    >  **CCS_ADJUSTABLE** stili araç çubuğu düğmeleri sürüklenmesi etkinleştirmek için belirtilmesi gerekir.  
  
-   **TBSTYLE_REGISTERDROP** oluşturur **TBN_GETOBJECT** bildirim iletileri istemek için fare imlecini araç çubuğu düğmeleri geçerken hedef nesneleri bırakın.  
  
 Kalan stilleri araç çubuğu nesnesi yönlerini görsel ve görsel olmayan etkiler:  
  
-   **TBSTYLE_WRAPABLE** düğmeleri birden fazla satır içeren bir araç çubuğu oluşturur. "Araç çubuğu düğmeleri araç aynı satırdaki tüm düğmeler eklemek için çok dar olduğunda sonraki satıra kayabilir". Kaydırma nongroup sınırları ve ayrılması gerçekleşir.  
  
-   **TBSTYLE_CUSTOMERASE** oluşturur **NM_CUSTOMDRAW** bildirim iletilerini işlerken, **WM_ERASEBKGND** iletileri.  
  
-   **TBSTYLE_TOOLTIPS** uygulama araç çubuğunda düğme için açıklayıcı metni görüntülemek için kullanabileceğiniz bir araç ipucu denetimi oluşturur.  
  
 Toolbar stilleri ve genişletilmiş stiller tam bir listesi için bkz. [araç çubuğu denetimi ve düğme stilleri](/windows/desktop/Controls/toolbar-control-and-button-styles) ve [araç genişletilmiş stiller](/windows/desktop/Controls/toolbar-extended-styles) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

