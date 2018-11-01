---
title: Bir Ortak Denetimi Alt Pencere Olarak Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 690b48cf50e95265aaf5bdd454e2881b8f5fab3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655136"
---
# <a name="using-a-common-control-as-a-child-window"></a>Bir Ortak Denetimi Alt Pencere Olarak Kullanma

Windows ortak denetimleri başka bir pencere bir alt pencere olarak kullanılabilir. Aşağıdaki yordam, ortak bir denetimi dinamik olarak oluşturmak ve onunla çalışan açıklar.

### <a name="to-use-a-common-control-as-a-child-window"></a>Bir ortak denetimi alt pencere olarak kullanmak için

1. Denetim, ilgili sınıf veya işleyici tanımlayın.

1. Denetimin geçersiz kılmasını kullanın [CWnd::Create](../mfc/reference/cwnd-class.md#create) Windows denetimi oluşturmak için yöntemi.

1. Denetim oluşturulduktan sonra (olarak erken `OnCreate` işleyicisi, denetimin alt), üye işlevleri kullanarak denetimi işleyebilirsiniz. Tek denetimleri açıklamaları görmek [denetimleri](../mfc/controls-mfc.md) yöntemleri hakkında ayrıntılı bilgi için.

1. Denetim ile işiniz bittiğinde, kullanın [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) kontrol edilecek.

## <a name="see-also"></a>Ayrıca Bkz.

[Denetimleri Yapma ve Kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

