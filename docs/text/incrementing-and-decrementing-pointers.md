---
title: İşaretçileri Artırma ve Azaltma
ms.date: 11/04/2016
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
ms.openlocfilehash: cdaee3d13a8ceab47f62100953a0eb6e51bfc255
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410661"
---
# <a name="incrementing-and-decrementing-pointers"></a>İşaretçileri Artırma ve Azaltma

Aşağıdaki ipuçlarını kullanın:

- İşaret baytlara değil, ön baytlar. Sondaki baytı işaretçiniz güvenli değil. Genellikle ileri yerine ters bir dizesini tara daha güvenlidir.

- İşaretçi artırma/azaltma işlevleri ve tam bir karakter üzerinden taşınan makroları vardır:

    ```cpp
    sz1++;
    ```

   olur:

    ```cpp
    sz1 = _mbsinc( sz1 );
    ```

   `_mbsinc` Ve `_mbsdec` işlevleri doğru bir şekilde artırın ve içinde azaltma `character` birimi, karakter boyutundan bağımsız olarak.

- Azaltır için bir işaretçi olduğu aşağıdaki gibi dize karşılaştırması gerekir:

    ```cpp
    sz2--;
    ```

   olur:

    ```cpp
    sz2 = _mbsdec( sz2Head, sz2 );
    ```

   Alternatif olarak, geçerli bir karakter dizesi, baş işaretçinizi olabilir gibi:

    ```cpp
    sz2Head < sz2
    ```

   Bilinen geçerli baytı için bir işaretçi olması gerekir.

- Daha hızlı çağrılar için önceki karaktere bir işaretçi korumak isteyebileceğiniz `_mbsdec`.

## <a name="see-also"></a>Ayrıca bkz.

[MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)<br/>
[Bayt Endeksleri](../text/byte-indices.md)
