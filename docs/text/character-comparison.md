---
description: 'Daha fazla bilgi: karakter karşılaştırması'
title: Karakter Karşılaştırma
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 0e00e087074a70145f1a73694293edc3c522d69f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297011"
---
# <a name="character-comparison"></a>Karakter Karşılaştırma

Aşağıdaki ipuçlarını kullanın:

- Bilinen bir ön baytı ASCII karakteriyle karşılaştırmak doğru şekilde geçerlidir:

    ```cpp
    if( *sz1 == 'A' )
    ```

- İki bilinmeyen karakteri karşılaştıran mbstring. h içinde tanımlanan makrolardan birinin kullanılması gerekir:

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   Bu, çift baytlık bir karakter için her iki baytın de eşitlik için karşılaştırılmasını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[MBCS programlama Ipuçları](../text/mbcs-programming-tips.md)<br/>
[Arabellek taşması](../text/buffer-overflow.md)
