---
title: Son bir dizedeki karakter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e207ec1d5489a629b765d398e26ac7c07771d0da
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384994"
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