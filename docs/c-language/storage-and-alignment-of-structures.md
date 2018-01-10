---
title: "Depolama ve yapıların hizalaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- alignment of structures
- structure storage
- storing structures
- packing structures
ms.assetid: 60ff292f-2595-4f37-ae00-4c4b4f047196
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0cb5ec55ed3125ac86b0042812ba7fc25388a155
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="storage-and-alignment-of-structures"></a>Yapıların Depolanması ve Hizalanması
**Microsoft özel**  
  
 Yapı üyeleri, bildirildikleri sıraya göre depolanır: İlk üye en düşük, son üye en yüksek bellek adresine sahiptir.  
  
 Her veri nesnesi bir *hizalama gereksinim*. Yapılar için gereksinim üyelerinin en büyüğüdür. Her nesne ayrılmış bir *uzaklık* böylece  
  
 *uzaklık* `%` *hizalama gereksinim* `==` 0  
  
 İntegral türleri aynı boyuttaysa ve sonraki bit alanları bit alanlarının yaygın hizalama gereksinimlerinin zorunlu kıldığı sınırı aşmadan geçerli ayırma birimine sığıyorsa, bitişik bit alanları aynı 1, 2 veya 4 baytlık ayırma birimine paketlenir.  
  
 Alandan tasarruf etmek veya varolan veri yapılarına uymak için, yapıları daha fazla veya daha az sıkı bir şekilde depolamak isteyebilirsiniz. [/Zp](../build/reference/zp-struct-member-alignment.md)[*n*] derleyici seçeneği ve [#pragma paketi](../preprocessor/pack.md) nasıl yapısı veri "dolu" belleğe denetim. /Zp kullandığınızda [*n*] seçeneği, burada  *n*  1, 2, 4, 8 ya da 16, ilk hizalama gereksinimi olan bayt sınırları depolandıktan sonra her yapısı üyesi alanın veya paket boyutu (*n*), hangisi daha küçüktür. Formül olarak ifade edildiğinde, bayt sınırları:  
  
```  
min( n, sizeof( item ) )  
```  
  
 Burada  *n*  ile /Zp ifade paketleme boyutudur [*n*] seçeneği ve *öğesi* yapısı üyesidir. Varsayılan paketleme boyutu /Zp8'dir.  
  
 Belirli bir yapı için komut satırında belirtilen paketlemeden başka bir paketlemeyi belirtmek üzere `pack` pragmasını kullanmak için, yapıdan önce, paketleme boyutu 1, 2, 4, 8 veya 16 olan `pack` pragmasını verin. Komut satırında belirtilen paketlemeyi yeniden başlatmak için, `pack` pragmasını bağımsız değişken olmadan belirtin.  
  
 Bit alanları varsayılan boyutuna **uzun** için Microsoft C derleyicisi. Yapı üyeleri türü veya /Zp boyutuna hizalı [*n*] boyut, hangisi daha küçüktür. Varsayılan boyut 4'tür.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapı Bildirimleri](../c-language/structure-declarations.md)