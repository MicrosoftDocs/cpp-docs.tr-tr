---
title: /DISASM
ms.date: 1/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 77f6f05029ec4480afb2180eab0bb57838d643a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462952"
---
# <a name="disasm"></a>/DISASM

Ayrıştırılmış kod bölümlerinin DUMPBIN çıktıda yazdırın.

## <a name="syntax"></a>Sözdizimi

> **/ DISASM**{**:**\[**BAYT**|**NOBYTES**]}

### <a name="arguments"></a>Arguments

**BAYT**<br/>
Bağımsız değişkenler, yorumlanan bir işlem yönergesi bayt ayrıştırılmış kodu çıktıyı içerir. Varsayılan seçenek budur.

**NOBYTES**<br/>
Yönerge bayt ayrıştırılmış kodu çıktısında içermez.

## <a name="remarks"></a>Açıklamalar

**/DISASM** seçeneği dosyasında Ayrıştırılmış kod bölümlerinin görüntüler. Dosyasında mevcut değilse hata ayıklama sembolleri kullanır.

**/ DISASM** yalnızca yerel, yönetilen, görüntüleri üzerinde kullanılmalıdır. Yönetilen kod için eşdeğer bir araçtır [ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler).

Yalnızca [OPTIONAL](../../build/reference/headers.md) DUMPBIN seçeneği tarafından üretilen dosyalar kullanıma [/GL (bütün program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)
