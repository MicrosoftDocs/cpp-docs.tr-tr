---
description: 'Daha fazla bilgi edinin: dizedeki son karakter'
title: Dizedeki Son Karakter
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 10ab90614509508b9667c29ccf166ddaf784a92e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207247"
---
# <a name="last-character-in-a-string"></a>Dizedeki Son Karakter

Aşağıdaki ipuçlarını kullanın:

- Sondaki bayt aralıkları birçok durumda ASCII karakter kümesi ile çakışıyor. Herhangi bir denetim karakteri (32 'den az) için, bytewise taramaları güvenle kullanabilirsiniz.

- Bir dizedeki son karakterin ters eğik çizgi karakteri olup olmadığını denetlemek için aşağıdaki kod satırını göz önünde bulundurun:

    ```cpp
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?
        // . . .
    ```

   , `strlen` MBCS 'nin farkında olmadığından, çok baytlı bir dizedeki karakter sayısını değil, bayt sayısını döndürür. Ayrıca, bazı kod sayfalarında 932 (örneğin,), ' \\ ' (0x5c) geçerli bir izleme baytı ( `sz` C dizesi) olduğunu unutmayın.

   Olası bir çözüm, kodu şu şekilde yeniden yazmaktır:

    ```cpp
    char *pLast;
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )
        // . . .
    ```

   Bu kod, MBCS işlevlerini `_mbsrchr` ve kullanır `_mbsinc` . Bu işlevler MBCS ile uyumlu olduğundan, ' ' \\ karakteri ve ' ' iz baytı arasında ayrım yapabilir \\ . Dizedeki son karakter null (' \ 0 ') ise kod bazı eylemler gerçekleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[MBCS programlama Ipuçları](../text/mbcs-programming-tips.md)<br/>
[Karakter atama](../text/character-assignment.md)
