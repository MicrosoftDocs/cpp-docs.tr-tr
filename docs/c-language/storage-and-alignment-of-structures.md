---
title: Yapıların Depolanması ve Hizalanması
ms.date: 11/04/2016
helpviewer_keywords:
- alignment of structures
- structure storage
- storing structures
- packing structures
ms.assetid: 60ff292f-2595-4f37-ae00-4c4b4f047196
ms.openlocfilehash: 81f5b640585ec3b55e4e3d65b37ea0929a757473
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229486"
---
# <a name="storage-and-alignment-of-structures"></a>Yapıların Depolanması ve Hizalanması

**Microsoft'a Özgü**

Yapı üyeleri, bildirildikleri sıraya göre depolanır: İlk üye en düşük, son üye en yüksek bellek adresine sahiptir.

Her veri nesnesinin bir *Hizalama gerekliliği*vardır. Yapılar için gereksinim üyelerinin en büyüğüdür. Her nesneye bir *konum* ayrılır, böylece

*konum* `%` *hizalama-gereksinim* `==` 0

İntegral türleri aynı boyuttaysa ve sonraki bit alanları bit alanlarının yaygın hizalama gereksinimlerinin zorunlu kıldığı sınırı aşmadan geçerli ayırma birimine sığıyorsa, bitişik bit alanları aynı 1, 2 veya 4 baytlık ayırma birimine paketlenir.

Alandan tasarruf etmek veya varolan veri yapılarına uymak için, yapıları daha fazla veya daha az sıkı bir şekilde depolamak isteyebilirsiniz. [/ZP](../build/reference/zp-struct-member-alignment.md)[*n*] derleyici seçeneği ve [#pragma paketi](../preprocessor/pack.md) , yapı verilerinin belleğe nasıl "paketlenme" olduğunu denetler. *N* , 1, 2, 4, 8 veya 16 olduğu/ZP [*n*] seçeneğini kullandığınızda, ilki her yapı üyesi alanın hizalama gereksinimi olan (hangisi daha küçükse) veya paketleme boyutu (*n*) olan bayt sınırları üzerinde depolanır. Formül olarak ifade edildiğinde, bayt sınırları:

```
min( n, sizeof( item ) )
```

Burada *n* ,/ZP [*n*] seçeneğiyle ifade edilen paketleme boyutudur ve *öğesi* yapı üyesidir. Varsayılan paketleme boyutu /Zp8'dir.

Belirli bir yapı için komut satırında belirtilen paketlemeden başka bir paketlemeyi belirtmek üzere `pack` pragmasını kullanmak için, yapıdan önce, paketleme boyutu 1, 2, 4, 8 veya 16 olan `pack` pragmasını verin. Komut satırında belirtilen paketlemeyi yeniden başlatmak için, `pack` pragmasını bağımsız değişken olmadan belirtin.

Bit alanları **`long`** , Microsoft C derleyicisi için varsayılan boyuta sahiptir. Yapı üyeleri türün boyutuna veya/ZP [*n*] boyutuna göre hizalanır, hangisi daha küçüktür. Varsayılan boyut 4'tür.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Yapı bildirimleri](../c-language/structure-declarations.md)
