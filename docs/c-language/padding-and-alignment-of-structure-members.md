---
title: Doldurma ve hizalama yapı üyelerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 959d6296c563958a0c8bdd1ecca660680941755f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074857"
---
# <a name="padding-and-alignment-of-structure-members"></a>Yapı Üyelerini Doldurma Hizalama

**ANSI 3.5.2.1** yapıları ve bir bit alanı, bir depolama birimi sınırı olup çekimi üyelerinin hizalamasını ve doldurma

Yapı üyeleri, bildirildikleri sıraya göre depolanır: İlk üye en düşük, son üye en yüksek bellek adresine sahiptir.

Her veri nesnesinin bir hizalama gereksinimi vardır. Nesnenin boyutu veya geçerli paketleme boyutu için yapılar, birleşimler ve diziler hariç tüm verileri hizalama gereksinimi olan (ya da/ZP belirtilen veya `pack` pragması, küçüktür). Yapılar, birleşimler ve diziler için en büyük hizalama gereksinimi, üyeleri hizalama gereksinimi olan. Her nesne bir uzaklık ayrılır. böylece

*uzaklık* `%` *hizalama gereksinimi* `==` 0  

İntegral türleri aynı boyuttaysa ve sonraki bit alanları bit alanlarının yaygın hizalama gereksinimlerinin zorunlu kıldığı sınırı aşmadan geçerli ayırma birimine sığıyorsa, bitişik bit alanları aynı 1, 2 veya 4 baytlık ayırma birimine paketlenir.

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Birleşimler, Numaralandırmalar ve Bit Alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)