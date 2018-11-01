---
title: Karakter Karşılaştırma
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 206910d4b76f93a92ee5230a227d6f0346a85e61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615416"
---
# <a name="character-comparison"></a>Karakter Karşılaştırma

Aşağıdaki ipuçlarını kullanın:

- ASCII karakterleriyle ile bilinen bir ön bayt karşılaştırma düzgün şekilde çalışır:

    ```cpp
    if( *sz1 == 'A' )
    ```

- İki bilinmeyen karakterleri karşılaştırma Mbstring.h içinde tanımlanan makroları birini gerektirir:

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   Bu, her iki baytlık bir çift baytlı karakter eşitlik için karşılaştırılması, sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)<br/>
[Arabellek Taşması](../text/buffer-overflow.md)