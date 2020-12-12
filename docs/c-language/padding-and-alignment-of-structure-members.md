---
description: 'Daha fazla bilgi edinin: yapı üyelerinin dolgusu ve hizalaması'
title: Yapı Üyelerini Doldurma Hizalama
ms.date: 10/18/2018
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
ms.openlocfilehash: db2530ecb00e5a01f5d10ff45da55420a8139be0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137455"
---
# <a name="padding-and-alignment-of-structure-members"></a>Yapı Üyelerini Doldurma Hizalama

**ANSI 3.5.2.1 &** Yapıların üyelerini doldurma ve hizalama ve bir bit alanın bir depolama birimi sınırı Straddle sağlayabilir

Yapı üyeleri, bildirildikleri sıraya göre depolanır: İlk üye en düşük, son üye en yüksek bellek adresine sahiptir.

Her veri nesnesinin bir hizalama gerekliliği vardır. Hizalama-yapılar, birleşimler ve diziler hariç tüm veriler için, nesnenin boyutu ya da geçerli paketleme boyutu ( `pack` hangisi daha az olursa). Yapılar, birleşimler ve diziler için hizalama-gereksinim, üyelerinin en büyük hizalama gereksinimidir. Her nesneye bir konum ayrılır, böylece

*konum* **%** *hizalama-gereksinim* **= = 0**

İntegral türleri aynı boyuttaysa ve sonraki bit alanları bit alanlarının yaygın hizalama gereksinimlerinin zorunlu kıldığı sınırı aşmadan geçerli ayırma birimine sığıyorsa, bitişik bit alanları aynı 1, 2 veya 4 baytlık ayırma birimine paketlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, birleşimler, numaralandırmalar ve bit alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)
