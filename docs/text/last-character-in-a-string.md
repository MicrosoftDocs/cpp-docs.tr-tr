---
title: Dizedeki Son Karakter
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 535c2e58edab49e0e2a9dbc3fce9821d5909f1c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456270"
---
# <a name="last-character-in-a-string"></a>Dizedeki Son Karakter

Aşağıdaki ipuçlarını kullanın:

- ASCII karakter kümesini çoğu durumda izi bayt aralıkları çakışıyor. Bu gibi durumlarda, dizede taramalar güvenli bir şekilde, denetim karakterlerini (32 den küçük) için kullanabilirsiniz.

- Bir dizedeki son karakter bir ters eğik çizgi karakteri olup olmadığını görmek için denetimi yapıyor olabilir kod, aşağıdaki satırı göz önünde bulundurun:

    ```cpp
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?
        // . . .
    ```

   Çünkü `strlen` MBCS tanımayan çok baytlı bir dize karakter sayısını değil bayt sayısını döndürür. Ayrıca, bazı kod sayfalarında (örneğin, 932), Not '\\' (0x5c) olan geçerli bir bayt (`sz` C dizesi).

   Bu şekilde, yeniden kod yazmak için olası bir çözüm şöyledir:

    ```cpp
    char *pLast;
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )
        // . . .
    ```

   Bu kod MBCS işlevlerini kullanır `_mbsrchr` ve `_mbsinc`. Bu işlevler MBCS kullanan olduğundan, bunlar arasında ayrım yapabilme kolaylığı bir '\\'karakteri ve sondaki baytı'\\'. Dizedeki son karakter ('\0') null ise kod bazı eylemleri gerçekleştirir.

## <a name="see-also"></a>Ayrıca Bkz.

[MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)<br/>
[Karakter Atama](../text/character-assignment.md)