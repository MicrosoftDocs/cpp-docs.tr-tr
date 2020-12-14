---
description: 'Daha fazla bilgi edinin: Ilerleme denetimi için stiller'
title: İlerleme Denetimi için Stiller
ms.date: 11/19/2018
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
ms.openlocfilehash: cd6ce1093f8bd2e3271a386e894d1e8dcd1a4fd7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216502"
---
# <a name="styles-for-the-progress-control"></a>İlerleme Denetimi için Stiller

İlerleme denetimini ilk oluşturduğunuzda ([CProgressCtrl:: Create](../mfc/reference/cprogressctrl-class.md#create)), ilerleme denetiminiz için istenen pencere stillerini belirtmek üzere *dwStyle* parametresini kullanın. Aşağıdaki listede, ilgili pencere stillerinin ayrıntıları verilmiştir. Denetim, burada listelenenlerden farklı pencere stilini yoksayar. Genellikle bir iletişim kutusu üst öğesi olmak üzere, denetimi her zaman bir alt pencere olarak oluşturmanız gerekir.

|Pencere stili|Etki|
|------------------|------------|
|WS_BORDER|Pencerenin etrafında bir kenarlık oluşturur.|
|WS_CHILD|Bir alt pencere oluşturur (için her zaman kullanılmalıdır `CProgressCtrl` ).|
|WS_CLIPCHILDREN|Üst pencere içinde çizim yaparken alt pencerelerin kapladığı alanı dışlar. Üst pencereyi oluşturduğunuzda kullanılır.|
|WS_CLIPSIBLINGS|Alt pencereleri birbirlerine göre kırpar.|
|WS_DISABLED|Başlangıçta devre dışı bırakılmış bir pencere oluşturur.|
|WS_VISIBLE|Başlangıçta görünür olan bir pencere oluşturur.|
|WS_TABSTOP|Kullanıcı sekmeye geçmek için SEKME tuşuna bastığında denetimin odağı alabileceğini belirtir.|

Ayrıca, yalnızca ilerleme denetimi, PBS_VERTICAL ve PBS_SMOOTH için uygulanan iki stil belirtebilirsiniz.

Denetimi yatay yerine dikey olarak yönlendirmek için PBS_VERTICAL kullanın. Denetimi artımlı olarak dolduran küçük bir ayırıcı kare görüntülemek yerine, denetimi tamamen göstermek için PBS_SMOOTH kullanın.

PBS_SMOOTH stili olmadan:

![Standart ilerleme çubuğu stili](../mfc/media/vc4ruw1.gif "Standart ilerleme çubuğu stili")

PBS_SMOOTH ve PBS_VERTICAL stilleriyle:

![İlerleme çubuğu stili, düz ve dikey](../mfc/media/vc4ruw2.gif "İlerleme çubuğu stili, düz ve dikey")

Daha fazla bilgi için bkz. *MFC başvurusunda* [pencere stilleri](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) .

## <a name="see-also"></a>Ayrıca bkz.

[CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)
