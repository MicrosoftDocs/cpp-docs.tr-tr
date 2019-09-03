---
title: Belge kuralları
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- preprocessor, conventions
ms.assetid: 469ce448-dc6c-4d0e-ba2b-e2e7a10155e1
ms.openlocfilehash: bb826b879b71edd3631c11a717320cee51c87175
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220364"
---
# <a name="document-conventions"></a>Belge kuralları

Kurallar, sözdiziminin farklı bileşenleri için farklı yazı tipi öznitelikleri kullanır. Simgeler ve yazı tipleri aşağıdaki gibidir:

| Öznitelik | Açıklama |
|---------------|-----------------|
| *& gt* | İtalik tür terminal olmayanları gösterir. |
| **#include** | Kalın türdeki terminaller, gösterildiği gibi girilmesi gereken sabit ayrılmış sözcükler ve simgelerdir. Bu bağlamdaki karakterler, her zaman büyük/küçük harfe duyarlıdır. |
| <sub>et</sub> | Terminal olmayan ve <sub>opt</sub> tarafından izlenen, her zaman isteğe bağlıdır.|
| varsayılan yazı tipi | Bu yazı tipinde açıklanan veya listelenen kümedeki karakterler, deyimlerde terminaller olarak kullanılabilir. |

Terminalden sonraki bir iki nokta üst üste ( **:** ) tanımı tanıtılmıştır. Alternatif tanımlar, ayrı satırlarda listelenmiştir.

Kod sözdizimi blokları ' nda, varsayılan yazı tipindeki bu simgelerin özel bir anlamı vardır:

| Sembol | Açıklama |
|---|---|
| \[] | Köşeli ayraçlar isteğe bağlı bir öğe. |
| { \| } | Küme ayraçları dikey çubuklarla ayrılmış alternatif öğeleri. |
| ... | Önceki öğe deseninin tekrarlanabilir olduğunu gösterir. |

Kod sözdizimi`,`blokları, virgüller (), noktalar (`.`), noktalı virgül`:`(`;`), iki nokta üst üste (), parantez`( )`(), çift tırnak (`"`) ve tek tırnak (`'`) değişmez değerleri.

## <a name="see-also"></a>Ayrıca bkz.

[Dilbilgisi özeti (C/C++)](../preprocessor/grammar-summary-c-cpp.md)
