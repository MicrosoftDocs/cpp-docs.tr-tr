---
title: Bayt Endeksleri
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 4e19868e5297e1c1615efabde2aee418bc53c51e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448821"
---
# <a name="byte-indices"></a>Bayt Endeksleri

Aşağıdaki ipuçlarını kullanın:

- Bir dizede dizini çalışmak bir dizeye işaretçi düzenlenmesiyle teşkil benzer sorunları gösterir. Bu örnekte, bir dize bir ters eğik çizgi karakteri tarar göz önünde bulundurun:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i++;
    ```

   Bu, bir bayt, bir ön bayt dizin ve bu nedenle onu işaret değil bir `character`.

- Kullanım [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) işlevi önceki sorunu çözmek için:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i += _mbclen ( rgch + i );
    ```

   Bu ön bayt için bu nedenle doğru dizinler için bir `character`. `_mbclen` İşlevi, bir karakter (1 veya 2 bayt) boyutunu belirler.

## <a name="see-also"></a>Ayrıca Bkz.

[MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)<br/>
[Dizedeki Son Karakter](../text/last-character-in-a-string.md)