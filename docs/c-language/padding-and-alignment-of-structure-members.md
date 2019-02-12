---
title: Yapı Üyelerini Doldurma Hizalama
ms.date: 10/18/2018
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
ms.openlocfilehash: 0f9c70ed074a11800b707aa48ec8e0e2f8b4f999
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148120"
---
# <a name="padding-and-alignment-of-structure-members"></a>Yapı Üyelerini Doldurma Hizalama

**ANSI 3.5.2.1** yapıları ve bir bit alanı, bir depolama birimi sınırı olup çekimi üyelerinin hizalamasını ve doldurma

Yapı üyeleri, bildirildikleri sıraya göre depolanır: İlk üye en düşük, son üye en yüksek bellek adresine sahiptir.

Her veri nesnesinin bir hizalama gereksinimi vardır. Nesnenin boyutu veya geçerli paketleme boyutu için yapılar, birleşimler ve diziler hariç tüm verileri hizalama gereksinimi olan (ya da/ZP belirtilen veya `pack` pragması, küçüktür). Yapılar, birleşimler ve diziler için en büyük hizalama gereksinimi, üyeleri hizalama gereksinimi olan. Her nesne bir uzaklık ayrılır. böylece

*uzaklık* **%** *hizalama gereksinimi* **== 0**

İntegral türleri aynı boyuttaysa ve sonraki bit alanları bit alanlarının yaygın hizalama gereksinimlerinin zorunlu kıldığı sınırı aşmadan geçerli ayırma birimine sığıyorsa, bitişik bit alanları aynı 1, 2 veya 4 baytlık ayırma birimine paketlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)
