---
title: / DISASM | Microsoft Docs
ms.date: 1/17/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /disasm
dev_langs:
- C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a5a4d930c47d2a3c2808cbd0a343c5c68de4ac9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707193"
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
