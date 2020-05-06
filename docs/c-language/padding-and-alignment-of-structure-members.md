---
title: Yapı Üyelerini Doldurma Hizalama
ms.date: 10/18/2018
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
ms.openlocfilehash: 0f9c70ed074a11800b707aa48ec8e0e2f8b4f999
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325370"
---
# <a name="padding-and-alignment-of-structure-members"></a>Yapı Üyelerini Doldurma Hizalama

**ANSI 3.5.2.1 &** Yapıların üyelerini doldurma ve hizalama ve bir bit alanın bir depolama birimi sınırı Straddle sağlayabilir

Yapı üyeleri, bildirildikleri sıraya göre depolanır: İlk üye en düşük, son üye en yüksek bellek adresine sahiptir.

Her veri nesnesinin bir hizalama gerekliliği vardır. Hizalama-yapılar, birleşimler ve diziler hariç tüm veriler için, nesnenin boyutu ya da geçerli paketleme boyutu ( `pack` hangisi daha az olursa). Yapılar, birleşimler ve diziler için hizalama-gereksinim, üyelerinin en büyük hizalama gereksinimidir. Her nesneye bir konum ayrılır, böylece

*konum* **%** *hizalaması-gereksinim* **= = 0**

İntegral türleri aynı boyuttaysa ve sonraki bit alanları bit alanlarının yaygın hizalama gereksinimlerinin zorunlu kıldığı sınırı aşmadan geçerli ayırma birimine sığıyorsa, bitişik bit alanları aynı 1, 2 veya 4 baytlık ayırma birimine paketlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)
