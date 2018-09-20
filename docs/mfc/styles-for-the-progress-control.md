---
title: İlerleme denetimi için stiller | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce520991b078f01e0551661516bfe7f24c53cf46
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442922"
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

![Standart bir ilerleme çubuğu stili](../mfc/media/vc4ruw1.gif "vc4ruw1")

İle PBS_SMOOTH ve pbs_vertıcal stili:

![İlerleme stili, sorunsuz ve dikey](../mfc/media/vc4ruw2.gif "vc4ruw2")

Daha fazla bilgi için [pencere stilleri](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) içinde *MFC başvurusu*.

## <a name="see-also"></a>Ayrıca Bkz.

[CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)

