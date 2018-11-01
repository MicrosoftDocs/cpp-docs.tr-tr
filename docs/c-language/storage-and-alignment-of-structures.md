---
title: Yapıların Depolanması ve Hizalanması
ms.date: 11/04/2016
helpviewer_keywords:
- alignment of structures
- structure storage
- storing structures
- packing structures
ms.assetid: 60ff292f-2595-4f37-ae00-4c4b4f047196
ms.openlocfilehash: 4dc04eda222b4fed4fb24f8d9ef138f9503093ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460625"
---
# <a name="storage-and-alignment-of-structures"></a>Yapıların Depolanması ve Hizalanması

**Microsoft'a özgü**

Yapı üyeleri, bildirildikleri sıraya göre depolanır: İlk üye en düşük, son üye en yüksek bellek adresine sahiptir.

Her veri nesnesinin bir *hizalama gereksinimi*. Yapılar için gereksinim üyelerinin en büyüğüdür. Her nesne ayrılmış bir *uzaklığı* böylece

*uzaklık* `%` *hizalama gereksinimi* `==` 0

İntegral türleri aynı boyuttaysa ve sonraki bit alanları bit alanlarının yaygın hizalama gereksinimlerinin zorunlu kıldığı sınırı aşmadan geçerli ayırma birimine sığıyorsa, bitişik bit alanları aynı 1, 2 veya 4 baytlık ayırma birimine paketlenir.

Alandan tasarruf etmek veya varolan veri yapılarına uymak için, yapıları daha fazla veya daha az sıkı bir şekilde depolamak isteyebilirsiniz. [/ZP](../build/reference/zp-struct-member-alignment.md)[*n*] derleyici seçeneği ve [#pragma paketini](../preprocessor/pack.md) nasıl veri yapısı "paketleneceğini" belleğe denetimi. Kullandığınızda/ZP [*n*] seçeneği, burada *n* 1, 2, 4, 8 veya 16, ilk bayt üzerinde depolandıktan sonra her yapı üyesi olan sınırları, alanın hizalama gereksinimi veya paketleme boyutu ( *n*), hangisi daha küçükse. Formül olarak ifade edildiğinde, bayt sınırları:

```
min( n, sizeof( item ) )
```

Burada *n* /ZP ifade edilen paketleme boyutudur [*n*] seçeneği ve *öğesi* ise yapı üyesidir. Varsayılan paketleme boyutu /Zp8'dir.

Belirli bir yapı için komut satırında belirtilen paketlemeden başka bir paketlemeyi belirtmek üzere `pack` pragmasını kullanmak için, yapıdan önce, paketleme boyutu 1, 2, 4, 8 veya 16 olan `pack` pragmasını verin. Komut satırında belirtilen paketlemeyi yeniden başlatmak için, `pack` pragmasını bağımsız değişken olmadan belirtin.

Bit alanları varsayılan olarak **uzun** Microsoft C derleyicisi için. Yapı üyeleri türün veya/ZP boyutuna hizalanır [*n*] boyut, hangisi daha küçükse. Varsayılan boyut 4'tür.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Yapı Bildirimleri](../c-language/structure-declarations.md)