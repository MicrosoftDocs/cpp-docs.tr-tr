---
title: Araç çubuğu denetiminin görünümünü özelleştirme | Microsoft Docs
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
ms.openlocfilehash: 96ec459e1c956c805991f2e37d22b8260f0ffdf2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343700"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>Bir Araç Çubuğu Denetiminin Görünümünü Özelleştirme
Sınıf `CToolBarCtrl` görünümü (ve bazen davranışı) araç nesnesinin etkileyen birçok stil sağlar. Araç çubuğu nesnesi ayarlayarak değiştirme `dwCtrlStyle` parametresinin `CToolBarCtrl::Create` (veya `CToolBar::CreateEx`) araç çubuğu denetimi ilk oluşturduğunuzda üye işlevi.  
  
 Aşağıdaki stiller araç çubuğu düğmelerini "3B" yönünü ve düğme metni yerleşimini etkiler:  
  
-   **TBSTYLE_FLAT** hem araç hem de düğmeleri nerede saydam düz bir araç çubuğu oluşturur. Düğme metni düğme bit eşlemler altında görüntülenir. İmleç altındaki düğmesi, otomatik olarak bu stili kullanıldığında, vurgulanır.  
  
-   **TBSTYLE_TRANSPARENT** saydam bir araç çubuğu oluşturur. Saydam araç çubuğu araç saydamdır ancak düğmeleri değildir. Düğme metni düğme bit eşlemler altında görüntülenir.  
  
-   **TBSTYLE_LIST** yerler düğmesini düğmesi bit eşlemler sağındaki metin.  
  
> [!NOTE]
>  Yeniden çizmeyi sorunları önlemek için **TBSTYLE_FLAT** ve **TBSTYLE_TRANSPARENT** stilleri araç çubuğu nesnesi görünür hale gelmeden önce ayarlanmalıdır.  
  
 Araç, kullanıcının düğmelerin Sürükle kullanan bir araç çubuğu nesnesi içinde yeniden konumlandırma ve bırakma izin verir, aşağıdaki stiller belirler:  
  
-   **TBSTYLE_ALTDRAG** kullanıcıların ALT tuşunu basılı tutarak sürükleyerek araç düğmenin konumu değiştirmesine izin verir. Bu stili belirtilmezse, kullanıcı bir düğme sürükleme sırasında SHIFT tuşunu basılı gerekir.  
  
    > [!NOTE]
    >  `CCS_ADJUSTABLE` Stili sürüklenen araç çubuğu düğmeleri etkinleştirmek için belirtilmesi gerekir.  
  
-   **TBSTYLE_REGISTERDROP** oluşturur **TBN_GETOBJECT** bildirim iletileri istemek için fare işaretçisini araç çubuğu düğmeleri geçerken hedef nesneler bırakın.  
  
 Kalan stilleri araç çubuğu nesnesi yönlerini görsel ve görsel olmayan etkiler:  
  
-   `TBSTYLE_WRAPABLE` Düğmeleri birden çok satırı olan bir araç çubuğu oluşturur. "Araç aynı satırdaki tüm düğmeleri dahil etmek için çok dar olduğunda araç çubuğu düğmeleri sonraki satıra kayabilir". Kaydırma ayırma ve nongroup sınırları oluşur.  
  
-   **TBSTYLE_CUSTOMERASE** oluşturur **NM_CUSTOMDRAW** bildirim iletileri bu işlerken `WM_ERASEBKGND` iletileri.  
  
-   `TBSTYLE_TOOLTIPS` Bir uygulama düğmelerinin açıklayıcı metin araç çubuğunda görüntülemek için kullanabileceğiniz bir araç ipucunu denetimini oluşturur.  
  
 Araç çubuğu stilleri ve genişletilmiş stilleri tam bir listesi için bkz: [araç çubuğu denetimi ve düğme stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760439) ve [araç genişletilmiş stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760430) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolBarCtrl kullanma](../mfc/using-ctoolbarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

