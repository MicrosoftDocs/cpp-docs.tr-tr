---
description: 'Daha fazla bilgi edinin: bayt dizinleri'
title: Bayt Endeksleri
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 5ee4b2cb8611893c71f5c6597e619cc73e2848ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187565"
---
# <a name="byte-indices"></a>Bayt Endeksleri

Aşağıdaki ipuçlarını kullanın:

- Bir dizede bytewise diziniyle çalışmak, işaretçi düzenlemesi ile ortaya çıkan sorunlara benzer sorunlar sunar. Bir ters eğik çizgi karakteri için dizeyi tarayan bu örneği göz önünde bulundurun:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i++;
    ```

   Bu, bir ön bayt değil, bir iz baytı dizinleyecek ve bu nedenle bir işaret edemeyebilir `character` .

- Önceki sorunu çözmek için [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) işlevini kullanın:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i += _mbclen ( rgch + i );
    ```

   Bu, için bir ön bayta doğru şekilde dizin oluşturur `character` . `_mbclen`İşlev, bir karakterin boyutunu (1 veya 2 bayt) belirler.

## <a name="see-also"></a>Ayrıca bkz.

[MBCS programlama Ipuçları](../text/mbcs-programming-tips.md)<br/>
[Dizedeki son karakter](../text/last-character-in-a-string.md)
