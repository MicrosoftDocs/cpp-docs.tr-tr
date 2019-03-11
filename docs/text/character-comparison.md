---
title: Karakter Karşılaştırma
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 075a22634f254c2ea634a1171ee157971fe5918e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749340"
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

## <a name="see-also"></a>Ayrıca bkz.

[MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)<br/>
[Arabellek Taşması](../text/buffer-overflow.md)
