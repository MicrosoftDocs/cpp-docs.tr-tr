---
title: İlerleme Denetimi için Stiller
ms.date: 11/19/2018
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
ms.openlocfilehash: 5d33e9306c1d70bb58ad628297360bc6e34e6ce2
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52174960"
---
# <a name="styles-for-the-progress-control"></a>İlerleme Denetimi için Stiller

Başlangıçta oluşturduğunuzda, ilerleme durumu denetimini ([CProgressCtrl::Create](../mfc/reference/cprogressctrl-class.md#create)), kullanın *dwStyle* ilerleme durumunu denetlemek için istenen pencere stilleri belirtmek için parametre. Aşağıdaki listede, geçerli pencere stilleri ayrıntıları. Denetim burada listelenenlerden dışındaki herhangi bir pencere stilini yok sayar. Her zaman denetim iletişim kutusunun üst öğesi, genellikle alt pencere olarak oluşturmanız gerekir.

|Pencere stili|Efekt|
|------------------|------------|
|WS_BORDER|Bir pencerenin kenarlık oluşturur.|
|WS_CHILD|Bir alt pencere oluşturur (her zaman için kullanılması gereken `CProgressCtrl`).|
|WS_CLIPCHILDREN|Ana pencerede çizerken alt pencerelerin kapladığı alanı dışarıda bırakır. Üst pencere oluşturulurken kullanılır.|
|WS_CLIPSIBLINGS|Alt pencereleri birbirine kırpar.|
|WS_DISABLED|Başlangıçta devre dışı olan bir pencere oluşturur.|
|WS_VISIBLE|Başlangıçta görünen bir pencere oluşturur.|
|WS_TABSTOP|Kullanıcı için taşımak için TAB tuşuna bastığında denetim odağı alabilecek belirtir.|

Ayrıca, yalnızca ilerleme denetimi için geçerli iki stilleri pbs_vertıcal ve PBS_SMOOTH belirtebilirsiniz.

Pbs_vertıcal denetimin dikey olarak yerine yatay olarak kullanın. PBS_SMOOTH denetim artımlı olarak doldurun ve sonuçları küçük kareler görüntüleme yerine denetimi tamamen doldurmak için kullanın.

PBS_SMOOTH stili:

![Standart bir ilerleme çubuğu stili](../mfc/media/vc4ruw1.gif "standart ilerleme çubuğu stili")

İle PBS_SMOOTH ve pbs_vertıcal stili:

![İlerleme stili, sorunsuz ve dikey](../mfc/media/vc4ruw2.gif "ilerleme stili, sorunsuz ve dikey")

Daha fazla bilgi için [pencere stilleri](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) içinde *MFC başvurusu*.

## <a name="see-also"></a>Ayrıca Bkz.

[CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)

