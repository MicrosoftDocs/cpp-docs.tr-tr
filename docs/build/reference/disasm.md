---
title: /DISASM
ms.date: 1/17/2018
f1_keywords:
- /disasm
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
ms.openlocfilehash: 10e8187e896b3922438a8cf2dafa0aec4c91f904
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272067"
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

Yalnızca [OPTIONAL](headers.md) DUMPBIN seçeneği tarafından üretilen dosyalar kullanıma [/GL (bütün program iyileştirmesi)](gl-whole-program-optimization.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
