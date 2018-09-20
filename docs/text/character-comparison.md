---
title: Karakter karşılaştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3412939bac9dace6f3abaacda75ed73d6e60f21
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428076"
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