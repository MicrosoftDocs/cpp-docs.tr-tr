---
title: Bayt Endeksleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11f7f78e87ddd40fd3cf85fc294e8fadac5dbe45
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423799"
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