---
title: "Doldurma ve hizalama yapı üyelerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: structure members, padding and alignment
ms.assetid: c999820b-dd47-41fc-b923-e4c7ebbcd30f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6c3a87f1277abb9d5cf3b9d87c6713104ba8e108
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="padding-and-alignment-of-structure-members"></a>Yapı Üyelerini Doldurma Hizalama
**ANSI 3.5.2.1** yapılar ve bit alan bir depolama birimi sınır olup yayınımda üyeleri hizalamasını ve doldurma  
  
 Yapı üyeleri, bildirildikleri sıraya göre depolanır: İlk üye en düşük, son üye en yüksek bellek adresine sahiptir.  
  
 Her veri nesnesi bir hizalama gereksinimi vardır. Yapılar, birleşimler ve diziler hariç tüm verileri hizalama gereksinimini nesnenin boyutu veya geçerli paket boyutu olduğundan (ya da /Zp ile belirtilen veya `pack` pragma, hangisi daha az ise). Yapılar, birleşimler ve diziler için hizalama-büyük hizalama gereksinim üyeleri gereksinimdir. Her nesne bir uzaklık ayrılmış şekilde  
  
 *uzaklık* `%` *hizalama gereksinim* `==` 0    
  
 İntegral türleri aynı boyuttaysa ve sonraki bit alanları bit alanlarının yaygın hizalama gereksinimlerinin zorunlu kıldığı sınırı aşmadan geçerli ayırma birimine sığıyorsa, bitişik bit alanları aynı 1, 2 veya 4 baytlık ayırma birimine paketlenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, birleşimler, numaralandırmalar ve Bit alanları](../c-language/structures-unions-enumerations-and-bit-fields.md)