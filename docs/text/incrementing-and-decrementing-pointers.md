---
description: 'Daha fazla bilgi edinin: Işaretçileri artırma ve azaltma'
title: İşaretçileri Artırma ve Azaltma
ms.date: 11/04/2016
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
ms.openlocfilehash: 3c333c11c5a0b68bf013dbd374eb1cc4e5f00abc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207325"
---
# <a name="incrementing-and-decrementing-pointers"></a>İşaretçileri Artırma ve Azaltma

Aşağıdaki ipuçlarını kullanın:

- Ön baytlar değil, ön bayt sayısını işaret edin. Genellikle bir iz baytı işaretçisi olması güvenli değildir. Genellikle bir dizeyi geri doğru bir şekilde taramak yerine daha güvenlidir.

- Bütün bir karakter üzerinde hareket eden işaretçi artışı/azaltma işlevleri ve makroları mevcuttur:

    ```cpp
    sz1++;
    ```

    şöyle olur:

    ```cpp
    sz1 = _mbsinc( sz1 );
    ```

   `_mbsinc`Ve `_mbsdec` işlevleri, `character` karakter boyutundan bağımsız olarak birimleri doğru şekilde artırır ve azaltır.

- Azaltır için, aşağıdaki gibi, dizenin baş bir işaretçisine ihtiyacınız vardır:

    ```cpp
    sz2--;
    ```

    şöyle olur:

    ```cpp
    sz2 = _mbsdec( sz2Head, sz2 );
    ```

   Alternatif olarak, baş işaretçiniz dizedeki geçerli bir karakter olabilir, örneğin:

    ```cpp
    sz2Head < sz2
    ```

   Bilinen geçerli bir ön bayta yönelik bir işaretçiniz olması gerekir.

- Daha hızlı çağrılar için önceki karaktere bir işaretçi tutmak isteyebilirsiniz `_mbsdec` .

## <a name="see-also"></a>Ayrıca bkz.

[MBCS programlama Ipuçları](../text/mbcs-programming-tips.md)<br/>
[Bayt dizinleri](../text/byte-indices.md)
