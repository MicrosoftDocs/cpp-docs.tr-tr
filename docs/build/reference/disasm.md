---
title: /DISASM
ms.date: 01/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: fb394b2266470e77c50ce5398aea961c37ac34fb
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927716"
---
# <a name="disasm"></a>/DISASM

Kod bölümlerinin ayrıştırılmış derlemesini DUMPBIN çıktısında yazdırın.

## <a name="syntax"></a>Sözdizimi

> **/DİSASM** { **:** \[**BAYT**NOBYTES]}|

### <a name="arguments"></a>Arguments

**SAYACININ**<br/>
Açıklama baytlarını, yorumlanan işlem kodları ve bağımsız değişkenlerle birlikte, ayırt derleme çıktısında içerir. Bu varsayılan seçenektir.

**YANIT SAYISI**<br/>
, Deassembly çıktısına yönerge baytlarını içermez.

## <a name="remarks"></a>Açıklamalar

**/Disasm** seçeneği, dosyadaki kod bölümlerinin ayrıştırılmış derlemesini görüntüler. Dosyada varsa hata ayıklama sembolleri kullanır.

**/Disasm** yalnızca yerel, yönetilmeyen ve görüntülerde kullanılmalıdır. Yönetilen kod için eşdeğer araç [ıldadsm](/dotnet/framework/tools/ildasm-exe-il-disassembler)' dir.

Yalnızca [/Headers](headers.md) dumpbin seçeneği [/GL (tüm program iyileştirmesi)](gl-whole-program-optimization.md) derleyici seçeneği tarafından oluşturulan dosyalarda kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
